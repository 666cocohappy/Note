<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

## 伯努利分布和Beta分布
对于伯努利分布：
$$
\operatorname{Bern}(x \mid \mu)=\mu^{x}(1-\mu)^{1-x}
$$
给定集合D=（x1，x2，。。。），其似然表示为
$$
p(\mathcal{D} \mid \mu)=\prod_{n=1}^{N} p\left(x_{n} \mid \mu\right)=\prod_{n=1}^{N} \mu^{x_{n}}(1-\mu)^{1-x_{n}}
$$

$$
\operatorname{Beta}(\mu \mid a, b)=\frac{\Gamma(a+b)}{\Gamma(a) \Gamma(b)} \mu^{a-1}(1-\mu)^{b-1} 
$$

$$
p(\mu \mid m, l, a, b) \propto \mu^{m+a-1}(1-\mu)^{l+b-1}
$$

[返回首页](https://666cocohappy.github.io/note/)
