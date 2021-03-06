# Deep-Learning-Approach-for-Surface-Defect-Detection
  A Tensorflow implementation of "**Segmentation-Based Deep-Learning Approach for Surface-Defect Detection**"
  （***秒杀 DeepLabV3+ 和 Unet 的 缺陷检测网络***）
   The author submitted the paper to cvpr2019 but it was not accepted. 
# The test environment
```
python 3.6
cuda 9.0
cudnn 7.1.4
Tensorflow 1.12
```
# You should know

  I used the Dataset used in the papar, you can download [KolektorSDD](https://www.vicos.si/Downloads/KolektorSDD) here.
  If you train you own datset ,you should change the dataset interfence for you dataset.

  You can refer to the [paper](https://arxiv.org/pdf/1903.08536v1.pdf) for details of the experiment.
 


# my experimental results on KolektorSDD
  **Notes:**  the first 30 subfolders are used as training sets, the remaining 20 for testing.    Although, I did not strictly follow the   params of the papar , I still got a good result.
```
2019-05-21 09:20:54,634 - utils - INFO -  total number of testing samples = 160
2019-05-21 09:20:54,634 - utils - INFO - positive = 22
2019-05-21 09:20:54,634 - utils - INFO - negative = 138
2019-05-21 09:20:54,634 - utils - INFO - TP = 21
2019-05-21 09:20:54,634 - utils - INFO - NP = 0
2019-05-21 09:20:54,634 - utils - INFO - TN = 138
2019-05-21 09:20:54,635 - utils - INFO - FN = 1
2019-05-21 09:20:54,635 - utils - INFO - accuracy(准确率) = 0.9938
2019-05-21 09:20:54,635 - utils - INFO - prescision（查准率） = 1.0000
2019-05-21 09:20:54,635 - utils - INFO - recall（查全率） = 0.9545
```
**visualization:**
![kos49_Part4.jpg](/visualization/test/kos48_Part5.jpg)

# testing the KolektorSDD
  After downloading the KolektorSDD and changing the param[data_dir]
  ```
  python run.py --test
  ```
  Then you can find the result in the "/visulaiation/test" and  "Log/*.txt"
  
 # training the KolektorSDD
 
 **First, only the segmentation network is independently trained, then the weights for the segmentation network are frozen and only the decision network layers are trained.**
 
   training the segment network
   ```
   python run.py --trian_segment
   ```
   training the  decision network
   ```
   python run.py  --train_decison
   ```
   training the total network( not good）
   ```
   python run.py  --train_total
   ```
 
