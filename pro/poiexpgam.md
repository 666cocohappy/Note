## 指数分布，泊松分布和伽马分布

- 泊松分布参数是单位时间（或单位面积）随机事件发生的平均次数。泊松分布适用于描述单位时间内的随机事件数。

$$
P(X=k)=\frac{\lambda^{k}}{k !} e^{-\lambda}, k=0,1, \cdots
$$

- 指数分布可以用来表示独立随机事件的时间间隔，如旅客进入机场的时间间隔、中文维基百科新条目出现的时间间隔等。

$$
f(x ; \lambda)=\left\{\begin{array}{cc}
\lambda e^{-\lambda x} & , x \geq 0 \\
0 & , x<0
\end{array}\right.
$$

- 指数分布解决的问题是“要等到一个随机事件发生，需要经历多久时间”，伽玛分布解决的问题是“要等到n个随机事件都发生，需要经历多久时间”。

$$
f(x, \beta, \alpha)=\frac{\beta^{\alpha}}{\Gamma(\alpha)} x^{\alpha-1} e^{-\beta x}, x>0
$$

alpha代表上述的n, 当alpha=1时，就变成了指数分布：

伽玛分布=指数分布＊泊松分布
