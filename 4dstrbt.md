<head>
        <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
</head>

### 四种常见分布
先给出有着紧密联系的四个分布，分别是：**伯努利分布**（Bernoulli Distribution）、**二项分布**（Binomial Distribution）、**类别分布**（Categorical Distribution）和**多项分布**（Multinomial Distribution）。

- 如果变量X服从伯努利分布 _Ber(p)_ ，那么X只有两种取值，这里不妨记为{0,1}，有：

$$
p(X=0)=p p(X=1)=1-p
$$

- 如果变量X服从二项分布 _B(n,p)_ ，那么X有 n + 1 种取值，有：

$$
p(X=k)=C_{n}^{k} p^{k}(1-p)^{n-k}, \quad k \in[0, n]
$$

- 如果变量X服从Categorical分布
$$
Cat( \alpha_{1}, \alpha_{2} ... \alpha_{k})
$$
，其中满足
$$
\sum_{j=1}^{k} \alpha_{j}=1
$$
，那么X有 k 种取值，有：

$$
p(X=j)= \alpha_{j}, \quad j \in[1, k]
$$

### 然后，举个例子说明这些分布的关系：
- 将一个小球放入两个桶，记变量 [公式] 为第一个桶里面有的小球个数，那么只有 0 个或者 1 个，所以是服从伯努利分布；
- 将 n 个小球放入两个桶，记变量 [公式] 为第一个桶里面的小球个数，那么最少可能有 0 个，最多可能有 n 个，所以服从二项分布；
- 将一个小球放入 k 个桶，记变量 [公式] 为 k 个桶内的小球个数，所以是一个向量，并且是One-hot的形式，因为这个小球只能在一个桶里面，所以是服从Categorical分布；
- 将 n 个小球放入 k 个桶，记变量 [公式] 为 k 个桶内的小球个数，是一个向量，并且向量元素的和为 n，所以是服从多项分布。
可以看出多项分布是其余三个分布的广义形式。将 n 设置为 1 即得到Categorical分布；将 k 设置为 2 即得到二项分布；将 n 设置为 1, k 设置为 2 得到伯努利分布。

[返回首页](https://666cocohappy.github.io/paper.io/)
