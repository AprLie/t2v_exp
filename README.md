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


