## 0-1背包问题
该问题考察动态规划，即将一个大任务分解成若干步骤，每一步骤可以求出当前最优解。
### 问题定义
对于一个固定容积（j）的背包，和若干个具有各自体积（w）和价值（v）的物品（i），如何选择物品组合使放进背包中的价值总和达到最大。
### 解题思路
1. 依次选择物品，在每一次选择时，将背包容积从0-j增加，查看每次增加时能携带的最大价值是多少。
2. 在解题之前创建i*（j+1）维的二维数组，储存对于每个物品在基于前一个物品计算结果的基础上，背包空间从0-j时的最大价值。[Image](https://img-blog.csdnimg.cn/20190810165633366.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM3NzY3NDU1,size_16,color_FFFFFF,t_70)
3. 在选定一个物品后，随着

