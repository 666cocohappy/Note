<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

## 张量分解_2:隐因子模型（latent factor model, LFM）

定义一个关于用户（user）[公式]i在环境（context，在隐性语义分析中常常理解为“语境”或“上下文”）c下对项（item）j的评分为rijc，评分张量的大小为m*n*d，所有观测到位置索引仍然记作集合S，其中，用户的索引为1～m，项的索引为1～n，环境的索引为1～d。
Charu C. Aggarwal在其著作《Recommender systems》中给出了一个特殊的张量分解结构，即大小为m*n*d的评分张量R分解后会得到三个矩阵，这三个矩阵分别是：大小为m*k的用户因子矩阵U（user-factor matrix）、大小为n*k的项因子矩阵V（item-factor matrix）和大小为d*k的环境因子矩阵W（context-factor matrix），这种分解结构是隐性因子模型的一种高阶泛化。
此时，第3阶张量[公式]上任意位置[公式]所对应的评分估计值为

$$
\begin{array}{l}
\hat{r}_{i j c}=\left(U V^{T}\right)_{i j}+\left(U W^{T}\right)_{i c}+\left(V W^{T}\right)_{j c} \\
\text { 即 } \hat{r}_{i j c}=\sum_{q=1}^{k}\left(u_{i q} v_{j q}+u_{i q} w_{c q}+v_{j q} w_{c q}\right)
\end{array}
$$

与矩阵分解中的低秩逼近问题相似，评分张量分解的逼近问题为

$$
\begin{aligned}
&\min J=\frac{1}{2} \sum_{(i, j, c) \in S} e_{i j c}^{2}=\frac{1}{2} \sum_{(i, j, c) \in S}\left(r_{i j c}-\sum_{q=1}^{k}\left(u_{i q} v_{j q}+u_{i q} w_{c q}+v_{j q} w_{c q}\right)\right)^{2}\\
&\text { 对目标函数 } J \text { 中的 } u_{i q}, v_{j q} \text { 和 } w_{c q} \text { 求偏导数，得 }\\
&\frac{\partial J}{\partial u_{i q}}=-\sum_{j, c:(i, j, c) \in S} e_{i j c} \cdot\left(v_{j q}+w_{c q}\right)\\
&\frac{\partial J}{\partial v_{j q}}=-\sum_{i, c:(i, j, c) \in S} e_{i j c} \cdot\left(u_{i q}+w_{c q}\right)\\
&\frac{\partial J}{\partial w_{c q}}=-\sum_{i, j:(i, j, c) \in S} e_{i j c} \cdot\left(u_{i q}+v_{j q}\right)
\end{aligned}
$$

根据梯度下降（gradient descent）方法, u，v和w在每次迭代过程中的更新公式为

$$
\begin{array}{l}
u_{i q} \Leftarrow u_{i q}+\alpha \sum_{j, c:(i, j, c) \in S} e_{i j c} \cdot\left(v_{j q}+w_{c q}\right) \\
v_{j q} \Leftarrow v_{j q}+\alpha \sum_{i, c:(i, j, c) \in S} e_{i j c} \cdot\left(u_{i q}+w_{c q}\right) \\
w_{c q} \Leftarrow w_{c q}+\alpha \sum_{i, j:(i, j, c) \in S} e_{i j c} \cdot\left(u_{i q}+v_{j q}\right)
\end{array}
$$


[返回首页](https://666cocohappy.github.io/note/)
