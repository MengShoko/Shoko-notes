[ 深度学习中Epoch、Batch以及Batch size的设定 - 知乎](https://zhuanlan.zhihu.com/p/390341772)
Epoch(时期):
一个完整的数据集通过神经网路一次并且返回一次的过程,通俗而言,就是将所有训练样本训练一次的过程
然而,一个Epoch的样本数量可能过于庞大,就需要把它分成多个小块(即batch)
Batch(批/一批样本)
Batch Size(批大小)
Iteration(一次迭代):
训练一个Batch就是一次Iteration

为什么要使用多于一个epoch?
数据集是有限的,训练太少会欠拟合,训练太多会过拟合

