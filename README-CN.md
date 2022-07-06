# Traffic-Sign-FOMO
OpenMV自行训练神经网络进行实际道路交通标志目标点检测。README-CN
[English README](https://github.com/SingTown/Traffic-Sign-FOMO/blob/main/README.md)


这个模型是使用edgeimpulse训练的，教程：
https://docs.edgeimpulse.com/docs/tutorials/detect-objects-using-fomo


一共训练得到两个模型

第一个模型：训练时分辨率128*128，使用MobilNetV2 0.35迁移学习，S1 Score 92%，运行帧率9帧左右，只能运行于OpenMV4 Plus。（OpenMV4内存不够）

第二个模型：训练时分辨率96*96，使用MobilNetV2 0.35迁移学习，S1 Score 91%，运行帧率12帧左右，峰值RAM占用244KB，在OpenMV4以及OpenMV4 Plus上都可以运行。


## 注意:

1. 一共有两个模型，如果是OpenMV4的话，只能使用96*96分辨率训练出来的这个小模型。Plus两个模型都可以用。
2. 数据集里面有 禁止停车x、禁止鸣笛n、限速80、禁止驶入-、测试图片，一共五个文件夹。 实际模型以及教程我们只使用了 禁止停车x、禁止鸣笛n、限速80、测试图片 这些，没有标注以及训练 禁止驶入- 的数据集，你可以自己选择是否标注以及训练 禁止驶入-。
3. 我只标注了 禁止停车x、禁止鸣笛n、限速80 这三个目标，数据集中出现的其他标志我都没有标注以及训练（比如 限速60 限速30 禁止驶入- 等）， 太相似的标志 比如 限速80 和 限速60 可能会误识别，你也可以自己增加标注训练新的目标 比如 限速60 等。
4. 致谢 —— 中国实际道路环境交通标志数据集的来源（中国科学院自动化研究所）： http://www.nlpr.ia.ac.cn/pal/trafficdata/detection.html

## 使用:
1. 把 labels.txt 和 trained.tflite 拖到OpenMV自带的U盘中。
2. 使用OpenMV IDE运行 ei_image_classification.py。
3. 你可以在终端中看到结果.

## 结果
![test_128x128_0.35](https://github.com/SingTown/Traffic-Sign-FOMO/blob/main/result/128x128.png)
![test_128x128_0.35](https://github.com/SingTown/Traffic-Sign-FOMO/blob/main/result/128x128-2.png)
![test_96x96_0.35](https://github.com/SingTown/Traffic-Sign-FOMO/blob/main/result/96x96.png)
![test_96x96_0.35](https://github.com/SingTown/Traffic-Sign-FOMO/blob/main/result/96x96-2.png)
