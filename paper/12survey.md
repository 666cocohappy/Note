<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# An Experimental Evaluation of Pointofinterest Recommendation in Locationbased Social Networks

## Point-of-Interest(POI)系统面临的挑战
1. 丰富的上下文信息
- 用户在一定地理范围内运动
- 用户容易重复访问地点
- 用户行为与时间段有关联
- 用户行为收到社交群体影响

2. 数据缺失问题
- 被访问POI只占很少的比例

## POI推荐
1. 空间影响（spatial influence）
2. 社交影响（social influence）
3. 时间影响（temporal influence）


## 评估模型
- 四种推荐技术
- 五种上下文信息

### 矩阵分解模型
与矩阵分解类似，在共现矩阵看作用户向量与POI向量（而非Item向量）乘积的结果。目标方程为：
$$
\min _{\mathbf{U}, \mathbf{L}}|| \mathbf{C}-\mathbf{U} \mathbf{L}^{\top}\left\|_{F}^{2}+\lambda_{1}\right\| \mathbf{U}\left\|_{F}^{2}+\lambda_{2}\right\| \mathbf{L} \|_{F}^{2}
$$

1. LRT
加入了时间因素，将用户因向量再分为24小时中不同的向量，并在目标方程中增加时间相似度的函数
$$
\sum_{t=1}^{T} \sum_{i=1}^{m} \psi_{i}(t, t-1)\left\|\mathbf{u}_{i}^{(t)}-\mathbf{u}_{i}^{(t-1)}\right\|_{2}^{2}
$$

2. 

[返回首页](https://666cocohappy.github.io/note/)
