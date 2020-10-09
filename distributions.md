<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/javascript"
      src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.3/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
    </script>
    <script type="text/javascript" charset="utf-8" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML,https://vincenttam.github.io/javascripts/MathJaxLocal.js"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            inlineMath: [['$','$']]
            }
        });
    </script>
</head>

先给出有着紧密联系的四个分布，分别是：**伯努利分布**（Bernoulli Distribution）、**二项分布**（Binomial Distribution）、**类别分布**（Categorical Distribution）和**多项分布**（Multinomial Distribution）。

- 如果变量 [公式] 服从伯努利分布 [公式] ，那么 [公式] 只有两种取值，这里不妨记为 [公式] ，有：

$$
p(X=0)=p p(X=1)=1-p
$$

- 如果变量 [公式] 服从二项分布 [公式] ，那么 [公式] 有 n + 1 种取值，有：

$$
p(X=k)=C_{n}^{k} p^{k}(1-p)^{n-k}, \quad k \in[0, n]
$$

-如果变量X服从Categorical分布，其中满足
$$
\sum_{j=1}^{k} \alpha_{j}=1
$$
，那么 [公式] 有 k 种取值，有：

