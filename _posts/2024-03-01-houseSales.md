---
title: 房价预测~
date: 2024-03-01
categories: [lstm]
tags: [me]     # TAG names should always be lowercase
---


基于kaggle数据集：

[House Property Sales Time Series](https://www.kaggle.com/datasets/htagholdings/property-sales/discussion)

数据集raw_data将近3w条，且波动巨大，resample至季度、月度数据，图例如下：

![alt text](quarterly.png)

![alt text](monthly.png)

如果直接对原数据进行操作将产生巨大的噪声，且预测结果几乎为一条直线，调整为月度、季度后产生了不错的拟合效果。

单分类上的拟合效果（归一化后的结果），50w次迭代效果：

![alt text](single.png)

多分类上的拟合效果（未添加attention机制），黑色为预测，其他为真实数值，10w次迭代效果（最后一部分可看作测试集，整体来看在测试集上的效果不算特别好）：

![alt text](multi.png)

另，如果针对多分类上的预测，使用月度数据产生了梯度爆炸问题....尚不确定添加注意力机制后是否能解决问题。

补，基于注意力机制的预测结果：

![alt text](attention.png)
