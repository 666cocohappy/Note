<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

## Note-Item-Based Collaborative Filtering Recommendation Algorithms

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

$$
\operatorname{sim}(i, j)=\frac{\sum_{u \in U}\left(R_{u, i}-\bar{R}_{u}\right)\left(R_{u, j}-\bar{R}_{u}\right)}{\sqrt{\sum_{u \in U}\left(R_{u, i}-\bar{R}_{u}\right)^{2}} \sqrt{\sum_{u \in U}\left(R_{u, j}-\bar{R}_{u}\right)^{2}}}
$$

$$
P_{u, i}=\frac{\sum_{\text {all similar items, } \mathrm{N}}\left(s_{i, N} * R_{u, N}\right)}{\sum_{\text {all similar items }, \mathrm{N}}\left(\left|s_{i, N}\right|\right)}
$$

$$
\overline{R_{N}^{\prime}}=\alpha \bar{R}_{i}+\beta+\epsilon
$$


[返回首页](https://666cocohappy.github.io/note/)
