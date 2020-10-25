<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

## 多项分布和狄利克雷分布

$$
\operatorname{Bin}(m \mid N, \mu)=\left(\begin{array}{l}
N \\
m
\end{array}\right) \mu^{m}(1-\mu)^{N-m} \\
$$

$$
\begin{array}{l}
\text { Mult }\left(m_{1}, m_{2}, \ldots, m_{K} \mid \mu, N\right)=\left(\begin{array}{c}
N \\
m_{1} m_{2} \ldots m_{K}
\end{array}\right) \prod_{k=1}^{K} \mu_{k}^{m_{k}} \\
$$

$$
p(\mathbf{x} \mid \mu)=\prod_{k=1}^{K} \mu_{k}^{x_{k}} \\
$$

$$
p(\boldsymbol{\mu} \mid \boldsymbol{\alpha}) \propto \prod_{k=1}^{K} \mu_{k}^{\alpha_{k}-1} \\
$$

$$
\operatorname{Dir}(\boldsymbol{\mu} \mid \boldsymbol{\alpha})=\frac{\Gamma\left(\alpha_{0}\right)}{\Gamma\left(\alpha_{1}\right) \cdots \Gamma\left(\alpha_{K}\right)} \prod_{k=1}^{K} \mu_{k}^{\alpha_{k}-1}
\end{array}
$$

[返回首页](https://666cocohappy.github.io/note/)
