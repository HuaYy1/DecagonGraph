#十边形：多模图上的表示学习

##用法：多药治疗
十进位用于解决药理学中一个紧迫的问题，即预测
[药物组合的安全性](http://stanford.edu/~marinka/slides/decagon-ismb18.pdf）。
我们构建了蛋白质-蛋白质相互作用、药物-蛋白质-靶标相互作用的多模式图，以及
多药副作用，表现为药物-药物相互作用，其中每个副作用都是
不同类型。
<p align=“center”>
<img src=“https://github.com/marinkaz/decagon/blob/master/images/polypharmacy-graph.png“width=”600“align=”center“>
</p>
Decagon使用图卷积将多模式图嵌入到紧凑向量空间中，然后使用
用于预测药物组合副作用的学习嵌入。
<p align=“center”>
<img src=“https://github.com/marinkaz/decagon/blob/master/images/decagon-architecture-1.png“width=”800“align=”center“>
</p>


###运行代码
合成数据集上多药问题的设置在“main.py”中概述。它使用了一个小的合成
具有五种边缘类型的网络示例。按以下方式运行代码：
$python main_real_data.py

完整的多药数据集（如论文所述）可在
【项目网站】(http://snap.stanford.edu/decagon). 要在完整的数据集上运行代码，请首先下载所有数据文件
来自[项目网站](http://snap.stanford.edu/decagon). 多药数据集已经过预处理，可以使用了。
克隆项目后，将“main.py”中的合成示例替换为多药数据集并运行模型。

###数据集
您可以在[项目网站]上下载真实的数据集(http://snap.stanford.edu/decagon). 创建一个数据文件夹。放入数据
并解压缩数据。数据文件夹上应该有六个.csv文件。

##引用
如果你觉得十边形对你的研究有用，请考虑引用[本文](https://academic.oup.com/bioinformatics/article/34/13/i457/5045770):
@article{Zitnik2018,
      title     = {Modeling polypharmacy side effects with graph convolutional networks.},
      author    = {Zitnik, Marinka and Agrawal, Monica and Leskovec, Jure},
      journal   = {Bioinformatics},
      volume    = {34},
      number    = {13},
      pages     = {457–466},
      year      = {2018}
    }
    
##其他
请发送您可能对代码和/或算法到<marinka@cs.stanford.edu>.
这段代码实现了几个不同的边缘解码器（innerproduct、distmult、，
双线性，dedicom）和损失函数（铰链损失，交叉熵）。许多深层变异是可能的，什么有效
最好的可能取决于具体的用例。



##要求
Decagon经过测试可以在Python 2和Python 3下工作。
需要最新版本的Tensorflow、sklearn、networkx、numpy和scipy。可以使用以下命令安装所有必需的软件包：
$pip install -r requirements.txt

##许可证
Decagon根据麻省理工学院许可证获得许可。
