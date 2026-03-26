# CNN-CIFAR10
这是一个基于 PyTorch 的 CIFAR-10 图像分类练习项目。  
在 conda 环境下，使用 VSCode 的 Jupyter Notebook 完成了卷积神经网络（CNN）的搭建、训练、模型保存与测试预测。
## 模型结构

本项目构建了一个简单的卷积神经网络（CNN），用于 CIFAR-10 图像分类任务。网络结构如下：

- 卷积层 1：`nn.Conv2d(3, 6, 5)`
  - 输入通道数：3（RGB 彩色图像）
  - 输出通道数：6
  - 卷积核大小：5×5

- 池化层：`nn.MaxPool2d(2, 2)`
  - 使用 2×2 最大池化进行下采样

- 卷积层 2：`nn.Conv2d(6, 16, 5)`
  - 输入通道数：6
  - 输出通道数：16
  - 卷积核大小：5×5

- 全连接层 1：`nn.Linear(16*5*5, 120)`

- 全连接层 2：`nn.Linear(120, 84)`

- 输出层：`nn.Linear(84, 10)`
  - 对应 CIFAR-10 的 10 个类别

前向传播过程中，卷积层后使用 ReLU 激活函数，卷积结果经过池化后展平，再输入全连接层完成分类。
模型进行了2轮训练

## 运行结果

**模型预测准确率：53%**

**10个类预测准确率分别为：**

```
Accuracy for class: plane is 70.4 %
Accuracy for class: car   is 72.0 %
Accuracy for class: bird  is 40.0 %
Accuracy for class: cat   is 33.3 %
Accuracy for class: deer  is 38.4 %
Accuracy for class: dog   is 38.8 %
Accuracy for class: frog  is 65.8 %
Accuracy for class: horse is 51.0 %
Accuracy for class: ship  is 60.8 %
Accuracy for class: truck is 69.4 %
```

**一组测试集的打印结果以及预测结果如图**

<img width="1042" height="1236" alt="image" src="https://github.com/user-attachments/assets/efda4c2f-d73a-410b-8a32-09447aee44d1" />
