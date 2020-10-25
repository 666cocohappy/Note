<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

## 张量分解_1:矩阵分解（matrix decomposition/factorization）

在我们常见的推荐系统（如商品推荐系统、电影推荐系统等）中，给定一个大小为m*n的评分矩阵R，元素rij表示用户（user）i对项（item，如电影、商品等）j的评分值。当矩阵R的秩为

$$
k=\operatorname{rank}(R) \ll \min (m, n)
$$

$$
R=UV^{T}
$$



[返回首页](https://666cocohappy.github.io/note/)
