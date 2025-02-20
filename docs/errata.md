# 纸质版勘误表

如何使用勘误？首先找到你的书的印次，接下来对着下表索引印次，该印次之后所有的勘误都是你的书中所要注意的勘误，印次前的所有勘误在当印次和之后印次均已印刷修正。

## 第1版第1次印刷（2022.03）

* 35页的图2.2 和 41页的图2.5（a）替换成下图：

![](res/Markov_chain.png ':size=350') 

* 47页，2.3.5节的第3行：称为备份图（backup diagram） → 称为备份图（backup diagram）或回溯图
* 62页，式(2.55) 前第2行：$H$ 是迭代次数 → $H$ 是让 $V(s)$ 收敛所需的迭代次数
* 62页，式(2.57) 改为
$$
\pi(s)=\underset{a}{\arg \max } \left[R(s, a)+\gamma \sum_{s^{\prime} \in S} p\left(s^{\prime} \mid s, a\right) V_{H+1}\left(s^{\prime}\right)\right]
$$

* 76页，式(3.1) 中 $G$ 和 $r$ 后面的数字改为下标，即

$$
\begin{array}{l}
G_{13}=0 \\
G_{12}=r_{13}+\gamma G_{13}=-1+0.6 \times 0=-1 \\
G_{11}=r_{12}+\gamma G_{12}=-1+0.6 \times(-1)=-1.6 \\
G_{10}=r_{11}+\gamma G_{11}=-1+0.6 \times(-1.6)=-1.96 \\
G_9=r_{10}+\gamma G_{10}=-1+0.6 \times(-1.96)=-2.176 \approx-2.18 \\
G_8=r_9+\gamma G_9=-1+0.6 \times(-2.176)=-2.3056 \approx-2.3
\end{array}
$$

* 149页，式(6.15) 改为

$$
\begin{aligned}
V^{\pi}(s) &\le Q^{\pi}(s,\pi'(s)) \\
&=E\left[r_{t}+V^{\pi}\left(s_{t+1}\right) | s_{t}=s, a_{t}=\pi^{\prime}\left(s_{t}\right)\right]\\
&\le E\left[r_{t}+Q^{\pi}\left(s_{t+1}, \pi^{\prime}\left(s_{t+1}\right)\right) | s_{t}=s, a_{t}=\pi^{\prime}\left(s_{t}\right)\right] \\
&=E\left[r_{t}+r_{t+1}+V^{\pi}\left(s_{t+2}\right) |s_{t}=s, a_{t}=\pi^{\prime}\left(s_{t}\right)\right]  \\
& \le E\left[r_{t}+r_{t+1}+Q^{\pi}\left(s_{t+2},\pi'(s_{t+2}\right) | s_{t}=s, a_{t}=\pi^{\prime}\left(s_{t}\right)\right] \\
& = E\left[r_{t}+r_{t+1}+r_{t+2}+V^{\pi}\left(s_{t+3}\right) |s_{t}=s, a_{t}=\pi^{\prime}\left(s_{t}\right)\right] \\
& \le \cdots\\
& \le E\left[r_{t}+r_{t+1}+r_{t+2}+\cdots | s_{t}=s, a_{t}=\pi^{\prime}\left(s_{t}\right)\right]  \\
& = V^{\pi'}(s)
\end{aligned}
$$

* 190页，9.5节第2段的第3行：也是不好实现的。我们可以实现优势演员-评论员算法就可以。 →  不好实现异步优势演员-评论员算法，但可以实现优势演员-评论员算法。
* 191页，第4和第5行：要用梯度去更新参数......就把梯度传 → 要用梯度去更新全局网络的参数。每个进程算出梯度以后，要把梯度传
* 191页，图9.6的上面一段的倒数第1行：变成 $\theta_2$了 → 变成$\theta_2$ 了（其他进程也会更新模型）
* 191页，图9.6的上面一段的末尾添加文字：虽然A3C看起来属于异策略算法，但它其实是一种同策略算法。因为A3C的演员和评论员只使用当前策略采样的数据来计算梯度。因此，A3C不存储历史数据，其主要通过平行探索（parallel exploration）来保持训练的稳定性。
* 191页，图9.6替换成下图：

![](res/A3C.png ':size=450')

* 191页，图9.6加参考文献：Arthur Juliani的文章“Simple Reinforcement Learning with Tensorflow Part 8: Asynchronous Actor-Critic Agents (A3C)”

* 200页，第6行：它的目标是要让每一场表演都获得观众尽可能多的欢呼声与掌声，也就是要最大化未来的总奖励 → 评论员的最终目标是让演员的表演获得观众尽可能多的欢呼声和掌声，从而最大化未来的总收益

* 201页，图10.7的上面一段的倒数第1行：均方差 → 均方误差（mean squared error，MSE）

* 201页，图10.7的下面一段的第3行：之间的一个均方差 → 之间的均方误差

* 203页，式(10.1)上面一段的第2行：均方差 → 均方误差

* 229页，第2行：很强的序列 → 很长的序列

* 242页，13.4.3节上面一段的第1行：均方差损失 → 均方误差损失

  