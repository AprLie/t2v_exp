
## NNI使用
详细可参阅https://nni.readthedocs.io/zh/latest/Tutorial/QuickStart.html
### 安装(python>=3.5)
```
python3 -m pip install --upgrade nni
```

### 使用方式
1.定义搜索空间 search_space.json  
2.定义配置文件 config.yaml  
3.修改python代码  
4.启动NNI  

#### 1.定义搜索空间
json中元素的形式为 "params_name":{"_type":"","_value":[]}
常用_type为:choice,randint,uniform等,详见https://nni.readthedocs.io/zh/latest/Tutorial/SearchSpaceSpec.html
```json
{
    "kernel":{"_type":"choice","_value":["rbf"]},
    "C":{"_type":"uniform", "_value":[0,2]}, 
    "class_weight":{"_type":"choice","_value":["balanced","null"]},
    "max_iter":{"_type":"choice","_value":[-1]},
    "gpu":{"_type":"choice","_value":[0,1,2,3]}
}
```  
注:搜索空间可以是嵌套的,即"value"内可以依旧是子搜索空间
#### 2.定义配置文件
https://nni.readthedocs.io/zh/latest/Tutorial/ExperimentConfig.html 中有内置的模板,注意
trial中的gpuNum表示跑一个trial需要多少个gpu,而不是gpuid,设置错误容易变为单trial  
例:(主要修改searchSpacePath和trial的command)
```yaml
authorName: xu
experimentName: svm
trialConcurrency: 4
maxExecDuration: 5h
maxTrialNum: 100
trainingServicePlatform: local
# 搜索空间文件
searchSpacePath: svm.json
useAnnotation: false
multiThread: True
# nni的log的存放地址,建议放在较大的盘内,避免占满硬盘空间后,web上会有两类报错:1.直接显示disk full error; 2.web 加载不出,显示 request failed xxx, code 500
logDir: /users/xu/nni
tuner:
  builtinTunerName: TPE
  classArgs:
    optimize_mode: maximize
    # 使用单显卡时使用方式为"0",所有出现gpuIndices的地方需要统一
  gpuIndices: 0,1,2,3

# 运行的命令，以及 Trial 代码的路径
trial:
  command: python3 ../src/svm_emsemble.py
  codeDir: .
  gpuNum: 1
localConfig:
# gpuIndices为允许调度的gpu的编号(nvidia-smi后显示的gpu id);
# maxTrialNumPerGpu为每块gpu最多同时跑多少个trial;注意,当trialConcurrency>maxTrialNumPerGpu时,其分配方式为按照gpuindices的顺序依次把maxTrialNumPerGpu个trial跑满,而不是平均分配到len(gpuindices)个gpu上;
# useActiveGpu:当gpu已经有任务在跑的时候,是否允许开新的trial
  gpuIndices: 0,1,2,3
  maxTrialNumPerGpu: 24
  useActiveGpu: True
```

#### 3.修改python代码
3-4行可解决  
1>引入NNI
```python
import nni
```
2>通过nni来传递参数
```python
params = nni.get_next_parameter()
run(params)
```
3>给nni report关注的指标(test set上)
```py
nni.report_final_result(accuracy_score(y_test, pred))
```
(可选)可以在每个epoch里报告即时的指标情况
```py
nni.report_intermediate_result(metrics)
```
#### 4.启动NNI
```
nnictl create --config xxx.yaml --port 12345
```

之后可在命令行弹出的网页地址中查看结果;如果是服务器端训练则url为 服务器ip:port  


注:  
1.在保证原有代码可正确运行的情况下再进行NNI调参,否则NNI中报错较难查看.  
2.在获取trial的Logpath(单击trial即可见)后,查看logpath下的strerr文件可获取报错信息,在trial.log可获取python输出信息,在parameter.cfg可获取参数信息(在web url有效时直接点击更便捷)  
3.在trial状态多数为失败时(或其他场景),需要停止实验,当有多个nni同时运行时,可通过  
```
nnictl stop --port portvalue
```
停止运行,这比复制粘贴experiment id更快.  
4.在实验中可以修改搜索空间,concurrency等,详见https://nni.readthedocs.io/zh/latest/Tutorial/Nnictl.html#update    
建议在跑一定数量的trial,在web上根据top 20%下hyper-parameter的分布来调整自己的搜索空间,然后可以直接
```
nnictl update searchspace [expid] -f filepath
```  
而不必新开一个nni实验,这样旧实验可以继承原有的调参经验,在新的更小的空间内搜索  
同时,不确定哪些参数后期会不会变动时候,可以把他们也写到搜索空间内,只是choice变为只有一个,不影响代码结果;这样要把定参数变为可调参数时只需要重新定义搜索空间即可  

5.暂不支持改变环境后继续resume原实验,有需求可以用docker.  
6.TPE tuner前20个点是随机的,因此trial数要＞20.  
7.一直在waiting:可以无视gpu上正在运行的进程而运行trial,避免等待;
```yaml
trainingServicePlatform: local
localConfig:
    maxTrialNumPerGpu:20
    useActiveGpu:True
```
实现一卡多trial.
8.utilization不高且显存充足的情况下,单卡并行跑多trial一般会有收益.
