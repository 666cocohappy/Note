<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

## 张量分解_1:矩阵分解（matrix decomposition/factorization）

在我们常见的推荐系统（如商品推荐系统、电影推荐系统等）中，给定一个大小为m*n的评分矩阵R，元素rij表示用户（user）i对项（item，如电影、商品等）j的评分值。当矩阵R的秩为

$$
k=\operatorname{rank}(R) \ll \min (m, n)
$$

能够写成如下形式

$$
R=UV^{T}
$$

U是大小为m*k的矩阵（用户因子矩阵，user-factor matrix）,V是大小为n*k的矩阵（项因子矩阵，item-factor matrix）。
用矩阵F-范数的平方，即矩阵中所有元素的平方和，来表示整体误差。目标是使其达到最小

$$
\min J=\frac{1}{2}\left\|R-U V^{T}\right\|^{2}
$$

对于矩阵中每一个估计出的评分，表示为

$$
\hat{r}_{i j}=\left(U V^{T}\right)_{i j}=\sum_{q=1}^{k} u_{i q} \cdot v_{j q}
$$

所以原问题变成

$$
\min J=\frac{1}{2} \sum_{(i, j) \in S} e_{i j}^{2}=\frac{1}{2} \sum_{(i, j) \in S}\left(r_{i j}-\sum_{q=1}^{k} u_{i q} \cdot v_{j q}\right)^{2}
$$

对u和v分别求偏导

$$
\begin{aligned}
\frac{\partial J}{\partial u_{i q}} &=\sum_{j:(i, j) \in S}\left(r_{i j}-\sum_{q=1}^{k} u_{i q} v_{j q}\right)\left(-v_{j q}\right) \\
\frac{\partial J}{\partial v_{j q}} &=\sum_{i:(i, j) \in S}\left(r_{i j}-\sum_{q=1}^{k} u_{i q} v_{j q}\right)\left(-u_{i q}\right)
\end{aligned}
$$

这里，可以将两个偏导数分别简写为 

$$
\frac{\partial J}{\partial u_{i q}}=-\sum_{j:(i, j) \in S} e_{i j} v_{j q} \\
\frac{\partial J}{\partial v_{j q}}=-\sum_{i:(i, j) \in S} e_{i j} u_{i q}
$$

其中,
i为1～m，j为1～n，q为1～k
根据梯度下降（gradient descent）方法, u和v在每次迭代过程中的更新公式为

$$
u_{i q} \Leftarrow u_{i q}+\alpha \sum_{j:(i, j) \in S} e_{i j} v_{j q} ; v_{j q} \Leftarrow v_{j q}+\alpha \sum_{i:(i, j) \in S} e_{i j} u_{i q}
$$

这里的 alpha 表示梯度下降的步长，又称为学习率 (learning rate) ，另外，更新公式中的求和项 下标 i，j分别表示向量R上所有非零元素的位置索引构成的集合。




[返回首页](https://666cocohappy.github.io/note/)
