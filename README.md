# t2v_exp
experiment results:  
|baseline|indexname|index|valuename|aggregation|F1 score|  
|-|-|-|-|-|-|
|CART|0.694|	0.775|	0.573|	0.600|	0.946|  
|random forest|	0.728|	0.790|	0.704|	0.676|	0.947|  
|svm_rbf|	0.689|	0.706|	0.633	|0.684|	0.935|  
|gbdt|	0.692|	0.805|	0.636	|0.617	|0.951|  
|xgboost|	0.726|	0.79|	0.677|	0.664|	0.948|  

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
3>给nni report关注的指标(testset上的)
```py
nni.report_final_result(accuracy_score(y_test, pred))
```
同时可以在每个epoch里报告即时的指标情况,
```py
nni.report_intermediate_result(metrics)
```
4.启动NNI
```
nnictl create --config xxx.yaml --port 12345
```

然后可在命令行弹出的网页地址中查看结果;如果是服务器端训练则url为 服务器ip:port
