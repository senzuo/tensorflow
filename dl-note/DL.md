# 深度学习

> 参考 3Blue1Brown 深度学习视频 https://space.bilibili.com/88461692?from=search&seid=11456663158615250737#/

## 1.神经网络的结构

什么是神经网络 ？\
神经网络的结构是怎样的？ \
神经网络的工作机制是怎样的？ \

变种 CNN RNN ...
此处为经典的原版 MLP Multilayer perceptron 多层感知机

神经(元)：装有数字的容器 eg 每一个像素点数值 => 	激活值
update：a function
		input all values from last layer
		output a value between 0 to 1

网络：σ(上一次激活值 * 权重 + bias) == 下一层激活值

权重：决定关注什么样子的图案
偏置：加权后的和

激活值落在0-1处 -> 激活函数 eg sigmoid


第一层：28 * 28 = 784 个神经元
最后一层：输出结果 0~9十个神经元
中间层：自定义层数、神经元个数

一层激活值影响下一层激活值



