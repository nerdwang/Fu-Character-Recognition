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


## 项目成员：
王珩琨，张波睿，李沛峰，谢冰洁，马正驰



## 备注

### 数据采集需要注意

对于福字，采集时要注意我们所采集的不同字体、形态的福字中要有与最终测试集中福字类型相近的数据，并且采集的图像尽可能的要不受水印或其他噪音的影响.

对于非福字，采集的过程也要尽可能的保证数据的干净，即图像中的噪音影响要尽可能的小.


### 数据预处理参考流程：

- 三通道转单通道  $\downarrow$

- 图像二值化(即像素非0即255） $\downarrow$ 

- 图像0-1化（即像素非0即1） $\downarrow$ 

- 使用均值滤波器去除明显的异常点（可选） $\downarrow$ 

- 还原为二值化图片方便手动筛选 $\downarrow$ 

- 图片裁剪（将图片裁剪为500*500大小的图片，注意其中要使用投票式插值，避免像素点出现非0非255的点）



### 提取特征方法可以参考：

- Sub-Sroke: 子笔画特征，将每个汉字图像按照行竖撇捺分为4个子笔画图像并利用横竖弹性网络提取每个子笔画的特征
- IECF-Hog: Internal and External Contour Features，提取汉字图像的内外轮廓以及Hog特征合并在一起的特征
- Hough: Hough特征，详情见参考文献
- Gabor: Gabor滤波器提取的特征
- GaborDEM: Gabor Double Elastic Mesh，Gabor双弹性网络特征，先将汉字图像进行子笔画提取，然后对每个子笔画提取Gabor特征并融合
- Character-SIFT: Character-SIFT特征，详情见参考文献


### 分类模型可以参考：

- SVC: 一种通过构建一个能够最大化分类间隔的超平面来将不同类别的样本分开的有监督学习算法。
- OneClassSVM: 一个通过构建一个能够最大化将正例样本与原点分开的超平面，来检测异常或离群样本的无监督学习算法。
- AdaBoost: 通过迭代训练一系列弱分类器，最终组合它们以获取更高的分类准确度的集成学习算法。
- AdaCostClassifier: 在AdaBoost基础上进行改进的算法，通过考虑样本类别不平衡和不同类别的代价差异来提高分类性能。


### 参考文献

[1] 刘妍. 基于Gabor双弹性网格特征提取的手写体汉字识别的研究[D].河北工业大学,2016.
 
 [2] 张亚俊. 自由手写体汉字脱机识别融合特征的研究[D].西华大学,2017.
 
 [3] 何浩智,朱宁波,刘伟.基于霍夫变换和弹性网格的手写汉字识别方法[J].计算机仿真,2008(01):240-243.
 
 [4] 赵健,冯乔生,何娟娟.面向汉字识别的新特征及其提取方法[J].软件,2015,36(03):31-36.
 
 [5] 张亚俊. 自由手写体汉字脱机识别融合特征的研究[D].西华大学,2017.
 
 [6] 高学,金连文,尹俊勋.一种基于笔画密度的弹性网格特征提取方法[J].模式识别与人工智能,2002,15(03):351-354.
 
 [7] 肖斌,黄襄念.基于SVM的几种汉字特征提取法比较研究[J].西华大学学报(自然科学版),2009,28(05):70-74.
 
 [8] 廖晨阳. 基于光学字符识别的多模态任务技术研究[D].北京邮电大学,2022.DOI:10.26969/d.cnki.gbydu.2022.000608.
 
 [9] 顾刚. 汉字识别关键算法研究与应用[D].浙江大学,2018.
 
 [10] 金贞. 汉字特征提取及识别技术的研究[D].上海交通大学,2010.
 
 [11] 王岩. 离线手写体汉字鉴别及识别算法研究[D].河北工业大学,2015.
 
 [12] 樊月娇. 手写汉字的识别算法研究及系统实现[D].内蒙古大学,2018.
 
 [13] Zhen Jin,Kaiyue Qi,Yi Zhou,Kai Chen,Jianbo Chen,Haibing Guan.SSIFT: An Improved SIFT Descriptor for Chinese Character Recognition in Complex Images[D].Shanghai Jiao Tong University ,2002.
 
 [14] Zhiyi Zhang,Lianwen Jin,Kai Ding,Xue Gao.Character-SIFT: A Novel Feature for Offline Handwritten Chinese Character Recognition[J].10th International Conference on Document Analysis and Recognition, ICDAR 2009, Barcelona, Spain, 26-29 July 2009


