# Pytorch-NLP
[DeepLearningForNLPInPytorch.ipynb](https://colab.research.google.com/github/JaniceWuo/Pytorch-NLP/blob/master/DeepLearningForNLPInPytorch.ipynb) 为nlp-pytorch教程中文简译(自学用)    
[NNLM_Torch.ipynb](https://colab.research.google.com/github/JaniceWuo/Pytorch-NLP/blob/master/NNLM_Torch.ipynb) 为预测句子的下一个单词的传统神经网络算法实现版    
[TextRNN_Torch.ipynb](https://colab.research.google.com/github/JaniceWuo/Pytorch-NLP/blob/master/TextRNN_Torch.ipynb) 为预测句子的下一个单词的RNN算法实现版

## Python & Pytorch 学习笔记    
1. enumerate()函数用于将一个可遍历的数据对象组合为一个索引序列，同时列出数据下标和数据,常用于for循环<br/>
example:<br/>
```python
    for i, word in enumerate(vocab)
```
2. 定义一个linear层的时候，写法为nn.Linear(in_features,out_features)<br/>
3. format是%的一个替代，一般用于 print('epoch: {}'.format(epoch+1))<br/>
4. 当网络中的某一个tensor不需要梯度时，可以使用torch.no_grad()来处理<br/>    
5. view的作用是reshape张量形状，torch.mm()是乘，torch.cat()是连接    
6. numpy.transpose 函数用于对换数组的维度  一般效果相当于`转置`<br/>
7. torch.squeeze()是对数据的维度进行压缩，去掉维数为1的的维度，相反的，torch.unsqueeze()是对数据维度进行扩充，给指定位置加上维数为一的维度。 a.squeeze(0)是当第0维为1时去掉，比如`a.shape=[1,2,3]`,那a.squeeze(0)之后变为`[2,3]`。其实就是当张量的维数为1时，那一维就没啥意义，可以去除。

## Tensorflow 学习笔记    
1. tf.argmax(input, axis=None, name=None, dimension=None)  axis = 0的时候返回每一列最大值的位置索引  axis = 1的时候返回每一行最大值的位置索引<br/>
2. tf.cast()：用于改变某个张量的数据类型<br/>
3. tf.placeholder(dtype, shape=None, name=None) 可以理解为占位，形参，后面再赋值  [None,3]是列为3但是行数不定<br/>
4. tf.get_variable()的机制跟tf.Variable()有很大不同，如果指定的变量名已经存在（即先前已经用同一个变量名通过get_variable()函数实例化了变量），那么get_variable()只会返回之前的变量，否则才创造新的变量。<br/>
5. 想要共享变量用scope.reuse_variables()。<br/>





# 机器学习    
1. Cross-Validation（交叉验证)    
  如果只是一次划分训练集和测试集，可能导致测试准确率受到划分的影响。所以要采取交叉验证，最好是K-fold Cross Validation。<br/>
  如果k=5，则把数据集分成5份，一共进行5次实验，每次取其中一份做测试集。之后取5次的平均值。