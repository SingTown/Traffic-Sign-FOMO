# Traffic-Sign-FOMO

A neural network model for actual road traffic sign target detection on OpenMV Cam.
[中文README](https://github.com/SingTown/Traffic-Sign-FOMO/blob/main/README-CN.md)


This model I trained with edgeimpulse, tutorial:
[https://docs.edgeimpulse.com/docs/openmv-cam-h7-plus](https://docs.edgeimpulse.com/docs/tutorials/detect-objects-using-fomo)


A total of two models were trained.

The first model: The resolution of training is 128*128, using MobilNetV2 0.35 transfer learning, S1 Score 92%, running FPS is about 9 frames, and can only run on OpenMV4 H7 Plus. (Not enough memory for OpenMV4 H7)

The second model: The resolution of training is 96*96, using MobilNetV2 0.35 transfer learning, S1 Score 91%, running FPS is about 12 frames, peak RAM usage is 244KB, can run on both OpenMV4 H7 and OpenMV4 H7 Plus.


## Note:

1. There are two models in total. If it is OpenMV4 H7, it can only use the small model trained with 96*96 resolution. Plus both models are available.
2. There are five folders in the dataset: No Parking x, No Horn n, Speed Limit 80, No Driving -, and Test Images. For this result model and tutorial, we only use the data sets of No Parking x, No Horn n, Speed Limit 80, and Test Pictures. There is no labeling and training of No Driving -. You can choose whether to label and train No Driving-.
3. I only marked the three goals of No Parking x, No Horn n, and Speed Limit 80. I did not mark and train other signs that appeared in the data set (such as Speed Limit 60, Speed Limit 30, No Driving - etc.), Signs that are too similar, such as Speed Limit 80 and Speed Limit 60, may be misidentified. You can also add labels to train new targets such as Speed Limit 60.
4. Acknowledgments - Source of China's actual road environment traffic sign dataset (Institute of Automation, Chinese Academy of Sciences): http://www.nlpr.ia.ac.cn/pal/trafficdata/detection.html

## To use:
1. drag labels.txt and trained.tflite to OpenMV.
2. run ei_object_detection.py with OpenMV IDE.
3. you can see result in terminal.

## result
![test_128x128_0.35](https://github.com/SingTown/Traffic-Sign-FOMO/blob/main/result/128x128.png)
![test_128x128_0.35](https://github.com/SingTown/Traffic-Sign-FOMO/blob/main/result/128x128-2.png)
![test_96x96_0.35](https://github.com/SingTown/Traffic-Sign-FOMO/blob/main/result/96x96.png)
![test_96x96_0.35](https://github.com/SingTown/Traffic-Sign-FOMO/blob/main/result/96x96-2.png)
