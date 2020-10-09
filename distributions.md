<head>
        <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
</head>

先给出有着紧密联系的四个分布，分别是：**伯努利分布**（Bernoulli Distribution）、**二项分布**（Binomial Distribution）、**类别分布**（Categorical Distribution）和**多项分布**（Multinomial Distribution）。

- 如果变量X服从伯努利分布 _Ber(p)_ ，那么X只有两种取值，这里不妨记为{0,1}，有：

$$
p(X=0)=p p(X=1)=1-p
$$

- 如果变量X服从二项分布 _B(n,p)_ ，那么X有 n + 1 种取值，有：

$$
p(X=k)=C_{n}^{k} p^{k}(1-p)^{n-k}, \quad k \in[0, n]
$$

-如果变量X服从Categorical分布
$$
Cat( \alpha_{1}, \alpha_{2} ... \alpha_{k})
$$
，其中满足
$$
\sum_{j=1}^{k} \alpha_{j}=1
$$
，那么X有 k 种取值，有：

$$
p(X=j)= \alpha_{j} j \in[1, k]
$$
