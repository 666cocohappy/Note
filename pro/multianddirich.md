<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

## 多项分布和狄利克雷分布

与伯努利分布相似，多项分布中的x可以有多种取之，而不是0和1，所以其似然可以表示为

$$
p(\mathbf{x} \mid \mu)=\prod_{k=1}^{K} \mu_{k}^{x_{k}} \\
$$

取之为1-k的变量发生mk次概率为
$$
\text { Mult }\left(m_{1}, m_{2}, \ldots, m_{K} \mid \mu, N\right)=\left(\begin{array}{c}
N \\
m_{1} m_{2} \ldots m_{K}
\end{array}\right) \prod_{k=1}^{K} \mu_{k}^{m_{k}} \\
$$

与二项分布和Beta分布类似，需要的共轭先验需要有下面的特点

$$
p(\boldsymbol{\mu} \mid \boldsymbol{\alpha}) \propto \prod_{k=1}^{K} \mu_{k}^{\alpha_{k}-1} \\
$$

经过归一化表示为

$$
\operatorname{Dir}(\boldsymbol{\mu} \mid \boldsymbol{\alpha})=\frac{\Gamma\left(\alpha_{0}\right)}{\Gamma\left(\alpha_{1}\right) \cdots \Gamma\left(\alpha_{K}\right)} \prod_{k=1}^{K} \mu_{k}^{\alpha_{k}-1}
$$

[返回首页](https://666cocohappy.github.io/note/)
