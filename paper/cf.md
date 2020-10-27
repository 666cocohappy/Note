<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# Note-Item-Based Collaborative Filtering Recommendation Algorithms

## ITEM-BASED COLLABORATIVE FILTERING ALGORITHM
计算物品i和j的相似性的基本的方法是，先分离同时对这两个物品进行过评价的用户，然后应用不同的评估方法。我们讨论三个方法：基于cos的方法，基于相关性的方法和调整后cos方法（cosine-based similarity, correlation-based similarity and adjusted-cosine similarity）。

### Cosine-based Similarity
属于物品集n中的两个物品i，j分别被视作2个m维向量，对应m个用户。

$$
\operatorname{sim}(i, j)=\cos (\vec{i}, \vec{j})=\frac{\vec{i} \cdot \vec{j}}{\|\vec{i}\|_{2} *\|\vec{j}\|_{2}} 
$$

### Correlation-based Similarity
令所有评估过i和j的用户为U，另外计算两个物品的平均评估值（rating）

$$
\operatorname{sim}(i, j)=\frac{\sum_{u \in U}\left(R_{u, i}-\bar{R}_{i}\right)\left(R_{u, j}-\bar{R}_{j}\right)}{\sqrt{\sum_{u \in U}\left(R_{u, i}-\bar{R}_{i}\right)^{2}} \sqrt{\sum_{u \in U}\left(R_{u, j}-\bar{R}_{j}\right)^{2}}}
$$

### Adjusted Cosine Similarity
基于用户和物品的CF区别在于对评估矩阵中的行和列的计算。基于cos的CF缺点是不同用户的评估比例不同。所以我们减去第u个用户的平均估值
$$
\operatorname{sim}(i, j)=\frac{\sum_{u \in U}\left(R_{u, i}-\bar{R}_{u}\right)\left(R_{u, j}-\bar{R}_{u}\right)}{\sqrt{\sum_{u \in U}\left(R_{u, i}-\bar{R}_{u}\right)^{2}} \sqrt{\sum_{u \in U}\left(R_{u, j}-\bar{R}_{u}\right)^{2}}}
$$

## Prediction Computation

### Weighted Sum
将用户u对于所有与物品i相似的物品N的估值的根据相似性加权的和，除以物品的数量以正则化。
$$
P_{u, i}=\frac{\sum_{\text {all similar items, } \mathrm{N}}\left(s_{i, N} * R_{u, N}\right)}{\sum_{\text {all similar items }, \mathrm{N}}\left(\left|s_{i, N}\right|\right)}
$$

### Regression
与加权平均相似，但是是用回归近似估值。用cosine和相关性评估出的相似性，容易导致欧式距离较远的两个物品却实际上有较大的相似性。将用户u对于所有与物品i相似的物品N的估值的平均值用线性回归计算出来。
$$
\overline{R_{N}^{\prime}}=\alpha \bar{R}_{i}+\beta+\epsilon
$$


[返回首页](https://666cocohappy.github.io/note/)
