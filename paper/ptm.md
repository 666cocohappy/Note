<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# 概率主题模型：潜在狄立克雷分配（Probabilistic Topic Models：Latent Dirichlet Allocation）

## 潜在狄立克雷分配

<img src="http://images.cnitblog.com/blog/401489/201301/30080332-dd3fabd59925417eaf349c6732931bf5.png"/>

假设所有的主题在文档产生之前就已经产生且指定。生成文档（或者说生成文档中的词）可以看成是如下两个过程：

随机产生一个主题直方图（或者说分布）；
对文档中的每个词：
(a) 从第一步产生的直方图里随机选择一个主题；
(b) 从主题对应的词语的概率分布中随机选择一个词。

### LDA和概率模型
LDA和其它主题模型都属于概率建模这一更大领域。数据被看作是经过包括隐藏变量在内的生成过程得到的。生成过程定义了观测随机变量和隐藏随机变量的联合概率分布。通过使用联合分布来计算在给定观测变量下隐藏变量的条件分布（后验分布）来进行数据分析。对于LDA来说，观测变量就是文档中的词；隐藏变量就是主题结构；生成过程如之前所述。那么推测从文档中隐藏的主题结构的问题其实就是计算在给定文档下隐藏变量的条件分布（后验分布）。

<img src="https://images0.cnblogs.com/blog/401489/201301/30080525-a2e8a8fdf5a1498ea3555d111d381b59.png"/>
图4:LDA的图模型。每个结点表示一个随机变量，并且根据其在生成过程中的角色予以标记（见图1）。隐藏变量对应的结点是白色的，观测变量wd,n对应的结点是灰色的。在图模型中，矩形表示变量的重复。

theta是某哥文章可能存在的主题分布的分布，采样其中一种主题分布，其为某些主题根据不同比例组成，即Z。然后从Z中采样某一主题，与相应主题中词语分布（gamma）联合生成一个单词。

LDA的生成过程对应的观测变量和隐藏变量的联合分布如下

$$
p\left(\beta_{1: K}, \theta_{1: D,} z_{1: D}, w_{1: D}\right)=\prod_{i=1}^{K} p(\beta) \prod_{d=1}^{D} p\left(\theta_{d}\right)\left(\prod_{n=1}^{N} p\left(z_{d, n} \mid \theta_{d}\right) p\left(w_{d, n} \mid \beta_{1: K}, z_{d, n}\right)\right)
$$

### LDA后验概率的计算
LDA后验概率的公式为

$$
p\left(\beta_{1: K}, \theta_{1: D}, z_{1: D} \mid w_{1: D}\right)=\frac{p\left(\beta_{1: K}, \theta_{1: D}, z_{1: D}, w_{1: D}\right)}{p\left(w_{1: D}\right)}
$$

分子为随机变量的联合分布。对于隐藏变量的任何值来说，联合分布是容易计算的。分母是观测变量的边际概率，是通过观察可见的语料库得到的概率。理论上，可以通过将联合分布对隐藏变量的所有可能值进行累加得到。但其计算量在实际操作中是异常庞大的（对于一个主题，这种累加包括了将每个词的所有可能的主题配置，而且文档集合通常有数量级达百万的词）。就像众多现代概率模型（包括贝叶斯统计）那样，后验概率的分母（即先验概率）往往是无法计算得到的。故而现代概率建模的一个核心研究目标就是尽一切可能接近之。如前图1和图3所述的那样，主题建模算法其实是求得近似后验分布的常用方法的一种变种。 主题建模算法主要有两类：基于采样的算法和变分算法。基于采样的算法通过收集后验分布的样本，以样本的分布求得后验分布的近似。主题建模中最常用的采样算法是吉布斯采样（Gibbs sampling），通过吉布斯采样构造马尔可夫链（Markov chain），而马尔可夫链的极限分布就是后验分布。马尔可夫链是由独立于前一个随机变量的随机变量组成的串。对主题模型来说，随机变量就是定义在一个特定的语料库上的隐藏主题。采样算法从马尔可夫链的极限分布上收集样本，再用这些样本来近似后验分布。通常，只有概率最高的样本会被收集以作为主题结构的近似。文献[33]详细描述了LDA的吉布斯采样，开源社区里有R语言的快速开源实现（http://cran.r-project.org/web/packages/lda/index.html）。 变分算法的确定性要比基于采样算法高上不少。变分算法先假定一族在隐藏结构之上的参数化的分布，再寻找与后验分布最接近的分布（概率分布之间的距离使用信息论的Kullback-Leibler散度度量，）。也就说，推断问题转换为了最优化问题。变分算法的创新之处也正在于此，它将最优化引入了概率建模中。文献[8]介绍了协调上升的变分推断算法；文献[20]介绍了一个更为快速的在线算法（以及开源软件），它能轻松处理上百万文档并能适应文本流的集合。

[8] D. Blei, A. Ng, and M. Jordan. Latent Dirichlet allocation. Journal of Machine Learning Research, 3:993–1022, January 2003.
[20] M. Hoffman, D. Blei, and F. Bach. On-line learning for latent Dirichlet allocation. In Neural Information Processing Systems, 2010.
[33] M. Steyvers and T. Griffths. Probabilistic topic models. In T. Landauer, D. McNamara, S. Dennis, and W. Kintsch, editors, Latent Semantic Analysis: A Road to Meaning. Laurence Erlbaum, 2006.





[返回首页](https://666cocohappy.github.io/note/)
