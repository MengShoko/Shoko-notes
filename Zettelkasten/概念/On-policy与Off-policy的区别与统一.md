[On-Policy 与 Off-Policy 的本质区别及统一：从Q函数到GRPO的深度解析 - 知乎](https://zhuanlan.zhihu.com/p/1896708901447123500)
在RL中，on-policy与off-policy是两种核心的学习策略，区别在于
**学习使用的数据来自当前策略本身，还是来自于其他策略**
On-policy算法中强化学习中的行为策略（生成数据）和目标策略（学习的策略）是相同的
Off-policy算法中行为策略与目标策略不同，可以使用来自其他策略生成的数据

## On-policy
你只能依据==当前==行为策略来学习，只能依据上一步来进行下一步的判断

#### 代表算法
* SARSA(State-Action-Reward-Action)
* PRO(Promimal Policy Optimization)

#### 特点
* 数据与策略紧耦合，稳定但样本利用率比较低
* 策略收敛稳定，适合动态调整策略的情景


## Off-policy
可以读取之前的得到的数据，来进行下一步的动作（学习的策略）

#### 代表算法
* Q-learning
* DQN（Deep Q-Network）
* DDPG/TD3/SAC

#### 特点
* 数据可以反复使用，样本利用率高
* 训练灵活，可以分离采样和训练过程
* 更容易产生偏差或不稳定
## 数理表达区别
![[Pasted image 20260821172537.png]]