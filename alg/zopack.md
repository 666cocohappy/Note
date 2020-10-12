## 0-1背包问题
该问题考察动态规划，即将一个大任务分解成若干步骤，每一步骤可以求出当前最优解。
### 问题定义
对于一个固定容积（j）的背包，和若干个具有各自体积（w）和价值（v）的物品（i），如何选择物品组合使放进背包中的价值总和（V）达到最大。
### 解题思路
1. 依次选择物品，在每一次选择时，将背包容积从0-j增加，查看每次增加时能携带的最大价值是多少。
2. 在解题之前创建i*（j+1）维的二维数组，储存对于每个物品在基于前一个物品计算结果的基础上，背包空间从0-j时的最大价值。[Image](https://img-blog.csdnimg.cn/20190810165633366.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM3NzY3NDU1,size_16,color_FFFFFF,t_70)
3. 在选定一个物品后，每一次增加容积，都有两个选择即放或者不放
3.1 如果增加后容积不够放，那么肯定不会放进去，而背包内物品的价值与上一个物品相同，即 V[i][j]= V[i-1][j]
3.2 如果容积够，那么此时要对比放和不放时那种情况下背包内价值大，不放的情况上面已经讨论过。而放的话，此时的背包价值则变成V[i][j]= (V[i-1][j-w[i]])+v[i]
3.3 所以V[i][j]取3.1 和 3.2 中较大的数。[image](https://img-blog.csdnimg.cn/20190810165740701.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM3NzY3NDU1,size_16,color_FFFFFF,t_70)
4. 通过回溯找到最大价值时的物品组成
4.1 如果V[i][j]= V[i-1][j]说明在j容积时未选择当前物品，而是选择了上一件物品
4.2 如果V[i][j]= (V[i-1][j-w[i]])+v[i]，说明选择了当前物品，而容积只剩下j-w[i]。此时查看V[i-1][j-w[i]]在4.1和4.2时的情景。
4.3 将i逐步递减至0，即可找到所有装进背包的物品


