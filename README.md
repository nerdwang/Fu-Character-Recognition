# Fu-Character-Recognition
This repository is used to store our ML final homework, a model to identify Fu character. 

## 总览

本模型使用了6种特征分别判断输入的一张图片是否是汉字“福”，进行交叉对比

## 使用

使用者可以根据数据集的特点，在preprocessing.ibynb文件中选取适合的函数进行运行，对数据进行预处理.
再运行feature.ibynb中的makeFeature函数，并给出特征类型名称可以从已处理好的数据集中提取需要的参数.
如果需要进行模型训练与对比，则再运行model.ibynb中的函数即可.

## 安装需求
`feature.ipynb`requires following dependencies:

- [Python](https://www.python.org/) (=3.9.13)
- [numpy](https://numpy.org/) (=1.24.3)
- [pandas](https://pandas.pydata.org/) (>=1.1.3)
- [opencv-python](https://pypi.org/project/opencv-python/)(=4.8.1.78)
- [scipy](https://www.scipy.org/) (>=1.9.1)
- [joblib](https://pypi.org/project/joblib/) (>=0.11)
- [scikit-learn](https://scikit-learn.org/stable/) (>=1.2.0)
- [matplotlib](https://matplotlib.org/) (>=3.3.2)
- [seaborn](https://seaborn.pydata.org/) (>=0.11.0)
- [tqdm](https://tqdm.github.io/) (>=4.50.2)

## 分工



## 备注

### 数据采集需要注意

尽可能多采集不同字体、形态等等的福字图片。尽可能不要包含不是福字的内容，参考老师测试集的样例。同时注意也要采集一些**非福字**的汉字图片，用于测试模型效果。

### 数据预处理注意：

将搜集到的图片转化成500*500像素的黑白numpy数组，以与测试集格式相匹配。注意许多图片可能携带水印，从彩色图片转化可能包含噪声，记得去除噪声。

### 提取特征方法可以参考：



### 特征选择注意：



### 分类模型可以参考：

