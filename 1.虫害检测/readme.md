# 基于室内无人机航拍图像的绿叶菜虫害检测
This is the official implementation of the paper **Pest disease detection of Brassica chinensis
through UAV-imagery and deep learning**.

Code is under preparation, please be patient.

> **Abstract:** *Pest disease is considered to be among the greatestthreats to Brassica chinensis. The 
physical invasion caused by pests will form wormholes, which seriously affect the yield and quality of 
Brassica chinensis. Timely and effective detection is important for modern facility agriculture. To 
tackle this problem, an efficient method is to use images taken from Unmanned Aerial
Vehicle (UAV) which may replace the traditional visual detection in fields. However, pest disease detection through UAV-imagery
faces many challenges, such as image blur and small object size. Therefore, we propose a strategy for pest disease detection of
Brassica chinensis in aerial images based on deep learning. At first, we employed an image tiling module to preprocess the aerial
images. Then, an image restoration module is adopted to deblur the image. Thirdly, an advanced method of disease object
detection based on improved CenterNet that combines attention mechanism and DIoU loss is proposed. In addition, a
dataset of aerial images of Brassica chinensis bitten by flea beetle was built and annotated, containing 42,452 wormhole
annotations. Extensive comparative experimental results show that the detection performance of the proposed method is
superior to the existing detection methods. And we achieved an overall accuracy of 87.2% AP50 and 94.7% R-squared for
pest disease detection of Brassica chinensis.*  

## Main problems 
+ Object scale varies violently
+ Objects with high density
+ Motion blur

## Results

### Wormhole detection task

| Model     |  AP(%) | AP50(%) | AP75(%)| Running Time(s)|
|-----------|--------|---------|--------|----------------|
| CenterNet |  45.1  |   80.7  |  44.1  |   0.071        |
| Ours      |  48.4  |   87.2  |  48.4  |   0.079        |

| Conf-thresh| Precision| Recall| F1-score| TP | FP | FN |
|------------|----------|-------|---------|----|----|----|
| 0.25| 66.6| 90.9| 76.8| 7253| 3642| 730|
| 0.30| 73.6| 89.6| 80.8| 7152 |2567| 831|
|0.35| 78.8 |87.9 |83.1| 7015| 1885 |968|
|0.40 |84.9| 85.0 |84.9 |6789| 1206 |1194|
|0.45 |90.1 |80.0 |84.8 |6389| 702 |1594|
|0.50 |93.4 |71.1| 80.7 |5673| 396 |2310|
|0.55 |95.6| 56.9| 71.3| 4541 |211 |3442|

### Wormhole counting task
| Conf-thresh| RMSE| MAE| MAPE (%)| R-squared(%) |
|------------|-----|----|---------|--------------|
| 0.25 |12.91 |10.54 |50.8 |58.2|
|0.30 |8.47| 6.68| 32.1 |82.0|
|0.35 |6.11| 4.48 |21.6 |90.6|
|0.40 |4.58| 3.10 |14.6 |94.7|
|0.45 |5.93 |3.75 |13.9 |91.2|
|0.50 |9.69 |6.77 |23.9 |76.5|
|0.55| 14.87 |11.34 |39.8 |44.6|

 ### Comparative Analysis with Other Methods
 | Model     |  AP(%) | AP50(%) | AP75(%)| Running Time(s)|
|-----------|--------|---------|--------|----------------|
| DETR |21.3 |59.4| 8.7 |0.280|
|YOLOv5 |35.3| 83.4 |30.8| 0.027|
|YOLOX |40.8| 80.7 |36.2 |0.024|
|CenterNet2 |43.3| 84.0| 37.5 |0.187|
|CenterNet |45.1 |80.7| 41.9 |0.071|
|Ours| 48.4 |87.2| 48.4| 0.075|
 
|Model| Conf-thresh| RMSE| MAE| MAPE (%)| R-squared(%) |
|-----|------------|-----|----|---------|--------------|
| DETR |0.90 |6.10 |3.85| 16.3 |90.7|
|YOLOv5 |0.30 |5.39 |3.65 |16.2| 92.7|
|YOLOX |0.25 |7.64 |4.67 |18.9 |85.4|
|CenterNet2| 0.55 |5.38| 3.64| 16.6 |92.7|
|CenterNet| 0.40 |5.29 |3.59| 16.6 |93.0|
|Ours| 0.40 |4.58| 3.10| 14.6| 94.7|
 
 
 
 
 
 
 