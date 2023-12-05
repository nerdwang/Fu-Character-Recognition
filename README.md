# Fu-Character-Recognition
This repository is used to store our ML final homework, a model to identify Fu character. 

## 总览

本模型使用了6种特征分别判断输入的一张图片是否是汉字“福”，进行交叉对比

## 使用

使用者可以根据数据集的特点，在preprocessing.ipynb文件中选取适合的函数进行运行，对数据进行预处理.

再运行feature.ipynb中的makeFeature函数，并给出特征类型名称可以从已处理好的数据集中提取需要的参数.

如果需要进行模型训练与对比，则再运行model.ipynb中的函数即可.

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


## 项目成员：王珩琨，张波睿，李沛峰，谢冰洁，马正驰



## 备注

### 数据采集需要注意

对于福字，采集时要注意我们所采集的不同字体、形态的福字中要有与最终测试集中福字类型相近的数据，并且采集的图像尽可能的要不受水印或其他噪音的影响.

对于非福字，采集的过程也要尽可能的保证数据的干净，即图像中的噪音影响要尽可能的小.


### 数据预处理参考流程：

  三通道转单通道  $\downarrow$

  图像二值化(即像素非0即255） $\downarrow$ 

  图像0-1化（即像素非0即1） $\downarrow$ 

  使用均值滤波器去除明显的异常点（可选） $\downarrow$ 

  还原为二值化图片方便手动筛选 $\downarrow$ 

  图片裁剪（将图片裁剪为500*500大小的图片，注意其中要使用投票式插值，避免像素点出现非0非255的点）



### 提取特征方法可以参考：

·



### 分类模型可以参考：

