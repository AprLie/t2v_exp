# t2v_exp
## final ver
### table cell
|baseline       |indexname|index|valuename|aggregation|other|F1 score|macro-F1|
|-|-|-|-|-|-|-|-|
|CART           |0.422|	0.827|	0.524|	0.375|	0.985|  0.956|  0.627|
|random forest  |0.559|	0.847|	0.628|	0.581|	0.985|  0.962|  0.720|
|svm_rbf        |0.407|	0.748|	0.545|  0.597|	0.972|  0.939|  0.654|
|gbdt           |0.499|	0.884|	0.612|  0.521|  0.990|  0.970|  0.701|
|xgboost        |0.618|	0.885|	0.612|	0.551|	0.990|  0.971|  0.731|
|pixel-cnn      |0.585| 0.754|  0.584|  0.572|  0.971|  0.934|  0.693|
|fcn            |0.636| 0.784|  0.652|  0.585|  0.978|  0.947|  0.727|
|ICDM_all_test  |0.616| 0.782|  0.696|  0.681|  0.977|  0.950|  0.750|

### table region:col
|baseline|header|not|F1 score|macro-F1|
|-|-|-|-|-|
|CART           |0.881|	0.983|	0.970|	0.932|	
|random forest  |0.922|	0.989|	0.981|	0.955|	
|svm_rbf        |0.860|	0.980|	0.965|  0.920|	
|gbdt           |0.898|	0.985|	0.974|  0.942| 
|xgboost        |0.890|	0.984|	0.972|	0.937|	
|pixel-cnn      |0.848| 0.978|  0.962|  0.913|
|cnn            |0.887| 0.984|  0.972|  0.935|

### table region:row
|baseline|header|not|F1 score|macro-F1|
|-|-|-|-|-|
|CART           |0.874|	0.994|	0.989|	0.934|	
|random forest  |0.902|	0.996|	0.992|	0.949|
|svm_rbf        |0.850|	0.994|	0.988|  0.922|
|gbdt           |0.914|	0.996|	0.993|  0.955| 
|xgboost        |0.883| 0.995|	0.990|	0.939|
|pixel-cnn      |0.793| 0.991|  0.983|  0.892|
|cnn            |0.894| 0.995|  0.991|  0.944|



## table region: row    
default params:
|baseline|header|not|F1 score|macro-F1|
|-|-|-|-|-|
|CART           |0.777|	0.991|	0.983|	0.884|	
|random forest  |0.807|	0.993|	0.987|	0.900|
|svm_rbf        |0.777|	0.992|	0.985|  0.885|
|gbdt           |0.862|	0.995|	0.990|  0.928| 
|xgboost        |0.849|	0.995|	0.990|	0.922|
## table region: col
default params:
|baseline|header|not|F1 score|macro-F1|
|-|-|-|-|-|
|CART           |0.797|	0.974|	0.954|	0.886|	
|random forest  |0.845|	0.981|	0.967|	0.913|	
|svm_rbf        |0.808|	0.977|	0.959|  0.893|	
|gbdt           |0.856|	0.982|	0.967|  0.919| 
|xgboost        |0.859|	0.982|	0.968|	0.920|	
## table cell  
default params:  
|baseline|indexname|index|valuename|aggregation|F1 score|macro-F1|
|-|-|-|-|-|-|-|
|CART           |0.493|	0.705|	0.530|	0.338|	0.925|  0.606|
|random forest  |0.596|	0.786|	0.641|	0.542|	0.945|  0.708|
|svm_rbf        |0.432|	0.746|	0.494|  0.531|	0.933|  0.634|
|gbdt           |0.456|	0.789|	0.590|  0.470|  0.945|  0.656|
|xgboost        |0.624|	0.793|	0.621|	0.509|	0.947|  0.705|
|pixel-cnn      |0.468| 0.747|  0.613|  0.570|  0.939|  0.674|
|fcn            |0.534| 0.773|  0.644|  0.584|  0.946|  0.702|
|ICDM_bert+fe   |0.598| 0.714|  0.566|  0.560|  0.930|  0.681|
|ICDM_all       |0.601| 0.804|  0.689|  0.630|  0.949|  0.740|
|ICDM_all_test  |0.617| 0.789|  0.662|  0.553|  0.942|  0.719|





## delete

update(small300):  
default params:  
|baseline|indexname|index|valuename|aggregation|F1 score|macro-F1|  
|-|-|-|-|-|-|-|
|CART           |0.504|	0.907|	0.593|	0.467|	0.973|  0.700| 
|random forest  |0.568|	0.879|	0.600|	0.596|	0.967|  0.736|
|svm_rbf        |0.449|	0.844|	0.543|  0.582|	0.956|  0.680|
|gbdt           |0.526|	0.934|	0.673|  0.549|  0.981|  0.736|
|xgboost        |0.644|	0.932|	0.670|	0.574|	0.981|  0.766|  
|icdm           |0.554|	0.744|	0.605|	0.340|	0.943|  0.644|  



(new dataset split method):  
default params:  
|baseline|indexname|index|valuename|aggregation|F1 score|macro-F1|
|-|-|-|-|-|-|-|
|CART           |0.493|	0.705|	0.530|	0.338|	0.925| 0.606|
|random forest  |0.576|	0.802|	0.560|	0.543|	0.960|  |
|svm_rbf        |0.416|	0.737|	0.529|  0.535|	0.942|  |
|gbdt           |0.511|	0.766|	0.593|  0.507|  0.956|  |
|xgboost        |0.632|	0.835|	0.602|	0.545|	0.966|  |
|NN             |0.000|	0.506|	0.000|	0.036|	0.889| |
|ICDM_bert+fe   |0.598| 0.714|  0.566|  0.560|  0.930|  0.681|

nni:  
|baseline|indexname|index|valuename|aggregation|F1 score|path|  
|-|-|-|-|-|-|-|
|CART           |0.489|	0.755|	0.551|	0.345|	0.951|  /home/ludu/nni/experiments/Nx1uaOG8/trials/xXqDI
|random forest  |0.618|	0.823|	0.637|	0.577|	0.965|  /home/ludu/nni/experiments/Ewz2q23k/trials/AVPk9
|svm_rbf        |0.689|	0.706|	0.633|  0.684|	0.935|  
|gbdt           |0.606|	0.826|	0.650|  0.574|  0.966|  /home/ludu/nni/experiments/aCxlK9e9/trials/EhZzf
|xgboost        |0.649|	0.836|	0.645|	0.576|	0.967|  /home/ludu/nni/experiments/Bnc0ZVql/trials/VsAY4

experiment results:  
|baseline|indexname|index|valuename|aggregation|F1 score|  
|-|-|-|-|-|-|
|CART           |0.694|	0.775|	0.573|	0.600|	0.946|  
|random forest  |0.728|	0.790|	0.704|	0.676|	0.947|  
|svm_rbf        |0.689|	0.706|	0.633|  0.684|	0.935|  
|gbdt           |0.692|	0.805|	0.636|  0.617|  0.951|  
|xgboost        |0.726|	0.790|	0.677|	0.664|	0.948|  

default params:
|baseline|indexname|index|valuename|aggregation|F1 score|  
|-|-|-|-|-|-|
|CART           |   0.422|	0.744|	0.533|	0.288|	0.928|  
|random forest  |	0.668|	0.742|	0.629|	0.635|	0.937|  
|svm_rbf        |	0.639|  0.714|  0.635|  0.680|  0.933|	  
|gbdt           |	0.420|	0.789|	0.639|  0.516|  0.945|  
|xgboost        |	0.705|	0.780|	0.640|	0.664|	0.944|  

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


