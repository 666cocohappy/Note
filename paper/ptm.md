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



[返回首页](https://666cocohappy.github.io/note/)
