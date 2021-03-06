# 有关有放回的无序抽样问题（unordered sampling with replacement）

&emsp;&emsp;假设样本集合$A=\lbrace a_1,a_2,...a_n\rbrace$,从中有放回的随机抽取$k$个，一共有多少种结果？

&emsp;&emsp;对于有放回的无序抽样问题其数学模型并不满足古典概型（1.有限样本空间；2.等可能性）中的等可能性要求，因此其计算过程较为复杂。

&emsp;&emsp;（对于为什么不满住等可能性可以有如下解释：考虑从1，2，3中随机有放回抽取两个数，抽到1，1的概率（0.25）显然要小于抽到1，2的概率（0.5），故不满足等可能性。）

&emsp;&emsp;这里我们假设$A={1,2,3},k=2$，因此一共有6总结果，如下所示：

$$
1,1 \to (2,0,0) \to 2+0+0=2\\
2,2 \to (0,2,0) \to 0+2+0=2\\
3,3 \to (0,0,2) \to 0+0+2=2\\
1,2 \to (1,1,0) \to 1+1+0=2\\
1,3 \to (1,0,1) \to 1+0+1=2\\
2,3 \to (0,1,1) \to 0+1+1=2
$$

&emsp;&emsp;这里我们将上述结果等价为右方结果，即统计每个样本出现的次数。也即求解下式：

$$
x_1+x_2+x_3=2,\quad where \quad x_1,x_2,x_3 \in \lbrace 0,1,2\rbrace \tag{1}
$$

&emsp;&emsp;将上述情况推广至n,即有：

$$
x_1+x_2+x_3+...x_n=k,,\quad where \quad x_1,x_2,x_3,...x_n \in \lbrace 0,1,2,..., k
\rbrace \tag{2}
$$

&emsp;&emsp;上式不易求解，这里我们进一步将问题转化。考虑式（1），这里我们记：

$$
1 \to |\\
2 \to ||\\
3 \to |||\\
...
$$

&emsp;&emsp;因此，$x_1+x_2+x_3+x_4=1+0+1+2=|++|+||$。

&emsp;&emsp;现在问题即转化为在k个|中插入n-1个+，一共有多少种结果：

$$
\underbrace{\_|\_|\_|\_|...|\_|\_}_k\\
向k+1个\_中插入n-1个+（允许_中插入多个或0个+），共有多少种结果？
$$

&emsp;&emsp;该问题即为k个|和n-1个+一共有多少种排序方式。

&emsp;&emsp;一共有n-1+k个空位向其中填入|或+，一共有多少种填入方式：

$$
C_{n+k-1}^k=C_{n+k-1}^{n-1}\tag{3}
$$

&emsp;&emsp;因此上述问题的最终答案即为式（3）。

[https://www.probabilitycourse.com/chapter2/2_1_4_unordered_with_replacement.php](https://www.probabilitycourse.com/chapter2/2_1_4_unordered_with_replacement.php)
