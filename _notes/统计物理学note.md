---

title: "统计物理学note"
collection: notes
type: "Ungraduated course"
permalink: /teaching/统计物理学notes
venue: " Wuhan University, 教一楼102，505"
date: 2024-04-03
location: "Wuhan, China"

---

施工中...

# 热统复习众人拾柴

## 第9章 理想气体的量子统计理论

### 9.1 统计对象的量子修正

在之前的理想气体的统计理论中，配分函数导出的熵计算公式有物理上的困难，即Gibbs佯谬。为了解决这一佯谬，我们做出了一个大胆的假设，修正了微观粒子的模型——全同粒子假设。即相同的微观粒子不可区分，不可标序号。

我们在第7章讨论过这个问题，这里简单回顾：
> 对正则系综，我们可以进行内能、熵等热力学量的计算。<br> 在定义上直接利用正则系综的特点，我们有内能：$$\begin{align*}\bar{E}&=\frac{\int{ \rm d}\omega Ee^{-\beta E}}{\int{ \rm d}\omega e^{-\beta E}}\\&=-\frac{\frac{{ \rm d}}{ {\rm d}\beta}(\int{ \rm d}\omega e^{-\beta E})}{\int{ \rm d}\omega e^{-\beta E}}\\&=-\frac{{ \rm d}}{ {\rm d}\beta}\ln Z(\beta)\end{align*}$$ 有压强的计算式：$$\begin{align*} \bar{p}&=\frac{\int{ \rm d}\omega -\frac{\partial E}{\partial V}e^{-\beta E}}{\int{ \rm d}\omega e^{-\beta E}}\\&=--\frac{1}{\beta}\frac{\frac{{ \rm d}}{ {\rm d}V}(\int{ \rm d}\omega e^{-\beta E})}{\int{ \rm d}\omega e^{-\beta E}}\\&=\frac{1}{\beta}\frac{{ \rm d}}{ {\rm d}V}\ln Z(\beta) \end{align*}$$ 有熵的计算式：从 ${ \rm d}E+p{ \rm d}V=T{ \rm d}S$ 出发 $$\begin{align*} \frac{1}{k}{ \rm d}S&=\beta{ \rm d}(-\frac{{ \rm d}\ln Z}{{ \rm d}\beta})+\frac{{ \rm d}\ln Z}{ {\rm d}V}{ \rm d}V\\&={ \rm d}(-\beta\frac{{ \rm d}\ln Z}{{ \rm d}\beta})+\frac{{ \rm d}\ln Z}{{ \rm d}\beta}{ \rm d}\beta +\frac{{ \rm d}\ln Z}{ {\rm d}V}{ \rm d}V\\&={ \rm d}(\beta\bar{E})+{ \rm d}\ln Z\end{align*}$$ 进而，可以得到熵计算式： $$S=k(\ln Z+\beta\bar{E})$$ 而亥姆赫兹自由能也可以计算： $$F=E-TS=-kT\ln Z$$ 这些计算式，对合适的配分函数下，给出这个理论模型下的热力学函数。

N个粒子组成的理想气体（有确定的温度 $T$ 和体积 $V$ ，所以可以等效视为一个正则系综）的配分函数，经典地计算，有：<br> $$Z(\beta)=\Big(\int  e^{-\beta \varepsilon}{ \rm d}^3q{ \rm d}^3p\Big)^N  $$ 其中 $\varepsilon$ 是单个粒子的能量，对于理想气体没有内势能，则 $\varepsilon=\frac{p^2}{2m}$，则：$$ \begin{align*} Z(\beta)&=\Big(\int { \rm d}^3q\Big)^N\Big(\int e^{\frac{\beta p_1^2}{2m}}e^{\frac{\beta p_2^2}{2m}}e^{\frac{\beta p_3^2}{2m}}{ \rm d}p_1{ \rm d}p_2{ \rm d}p_3\Big)^N \\&= V^N\Big(\int_{-\infty}^{+\infty}e^{\frac{\beta p^2}{2m}}{ \rm d}p\Big)^{3N}\\&=V^N\big(\frac{2\pi m}{\beta}\big)^{\frac{3N}{2}}  \end{align*}$$ 

有： $$\begin{align*}\ln Z &= N\ln V -\frac{3}{2}N\ln \beta + \frac{3}{2}N\ln(2\pi m) \\&= N\ln V+\frac{3}{2}N\ln T+\frac{3}{2}N\ln(2\pi mk)\end{align*}$$

那么其热力学函数：
$$E = -\frac{{ \rm d}}{ {\rm d}\beta}\ln Z= \frac{3N}{2\beta} = \frac{3}{2}NkT $$

$$p = \frac{1}{\beta}\frac{{ \rm d}}{ {\rm d}V}\ln Z = \frac{N}{\beta V}=\frac{N}{V}kT$$

$$S=k(\ln Z+\beta{E})=Nk\ln V+\frac{3}{2}Nk\ln T + Nk\sigma$$

其中 $\sigma=\frac{3}{2}(\ln(2\pi m k)+1)$ 是常数。

这就是致命的Gibbs悖论攻击的地方。首先，我们的配分函数计算过程中，量纲不定，这是有危险的。我们可以用相格来做一定程度的补救，将积分元记为 $\frac{{ \rm d}q{ \rm d}p}{h_0}$。但这会引入不定常数（角动量量纲）！另外，就算有这个常数，这个计算式在计算熵的结果时，会出现Gibbs佯谬，在第7章中有讨论。为了避免这个危险，我们最后选择假设微观粒子不可分，这样我原本的计算发生了 $N!$ 次重复，应该剔除。

而如果我们引入量子力学的观点，粒子自身实际上不能用一组正则坐标（广义坐标和广义动量）完全确定。粒子的状态应该用希尔伯特空间中的态矢量描述。但是近似地用 $q,p$ 描述，会有不确定性原理，有：

所以我们进行量子修正后，给出：

$${ \rm d}q{ \rm d}p\sim h$$

也就是说，我们把相格利用普朗克常数划分，同时对经典计算除以 $N!$

有配分函数：

$$\begin{align*} Z(\beta)&=\frac{1}{N!h^{3N}}V^N\big(\frac{2\pi m}{\beta}\big)^{\frac{3N}{2}}\\&=\frac{V^N}{N!}(\frac{2\pi m}{\beta h^2})^{\frac{3N}{2}} \end{align*}$$

量子修正后的配分函数，在这里的计算结果与预期物理图像一样，是无量纲的。

$$\ln Z=N\ln V-\ln N! - \frac{3}{2}N\ln\beta +\frac{3}{2}N\ln(\frac{2\pi m}{h^2})$$

在这一模型下，内能和压强的计算结果相同，但是熵的结果：

$$\begin{align*} S &= k(\ln Z+\beta E) \\&=Nk\ln V-k\ln N! +\frac{3}{2}Nk\ln T+\frac{3}{2}Nk\ln(\frac{2\pi mk}{h^2})+\frac{3}{2}Nk\\&=Nk\ln V-Nk\ln N +Nk+\frac{3}{2}Nk\ln T+\frac{3}{2}Nk\ln(\frac{2\pi mk}{h^2})+\frac{3}{2}Nk \\&= Nk\ln \frac{V}{N} +\frac{3}{2}Nk \ln T+Nk(\frac{3}{2}\ln(\frac{2\pi mk}{h^2})+\frac{5}{2})\\&=Nk\ln \frac{V}{N} +\frac{3}{2}Nk \ln T+Nk\sigma_0 \end{align*}$$

其中 $\sigma_0$ 是一个常数。这个计算式没有Gibbs佯谬提出的困难。所以我们认为全同粒子假设是正确的。

### 9.2 玻色子和费米子

让我们更加严格地考虑全同粒子假设，在量子力学地框架下意味着什么。考虑到这个系统的状态可以用这个系统对应的希尔伯特空间中的态矢量 $|\Psi\rang$ 来描述，而实际上我们关注的物理统计量是由粒子实际出现的位置的概率提供的，所以我们在统计上关注波函数 $\Psi(Q_1,Q_2,...,Q_N)=\lang Q_1Q_2...Q_N|\Psi\rang$ ，其中 $Q_1,Q_2,...,Q_N$ 是我们为了写出表达式，给每个粒子数学上标号后描述其的广义坐标。

全同粒子假设，即认为粒子就算标号后，交换两个编号粒子，系统的状态不变。而注意，我们关注的物理状态是概率波的反映，而不是态矢量本身。概率波是波函数的模方。所以我们得到的总结是，交换两个编号粒子，不改变概率波！就是说波函数本身在发生编号粒子交换时允许且只允许有一个全局相位的改变。

我们认为，交换编号粒子本身是一个本质的物理操作，也就是说产生的相位因子与交换哪两个编号粒子和交换的两个编号粒子的状态是无关的。那么：

$$\Psi(Q_2,Q_1,...,Q_N)=\lambda \Psi(Q_1,Q_2,...,Q_N)$$

再交换一次：

$$\Psi(Q_1,Q_2,...,Q_N)=\lambda \Psi(Q_2,Q_1,...,Q_N)$$

所以我们得到 $\lambda^2 =1$

于是交换操作产生的因子只有 $\lambda = \pm 1$ 两种可能

这个 $\lambda$ 取 $+1$ 或 $-1$ 是由全同粒子本身的性质决定的。我们也便按照这两种可能，将微观粒子分类为：玻色子和费米子。

- 玻色子：$\lambda = +1$

- 费米子：$\lambda = -1$

而费米子有一个很有意思的现象，如果波函数中，有两个粒子处于同一个状态（体现为这两个粒子态矢量在其希尔伯特空间中同一完备正交基下投影系数相同） $Q_i=Q_j$ ，那么就会有：$$\Psi(...,Q_i,...,Q_j,...)=\Psi(...,Q_j,...,Q_j,...)$$

因为本来就相同。但是实现这一点还可以通过交换编号粒子做到：
$$\Psi(...,Q_i,...,Q_j,...)=-\Psi(...,Q_j,...,Q_j,...)$$

这只能说明：
$$\Psi(...,Q_i,...,Q_j,...)=0$$

也就是说，这种状态波函数是零函数，也就说不可能出现这种状态。也就说，对于费米子系统，其中任意两个粒子不能处于同一个状态。用到电子情况，就是泡利总结发现的泡利不相容原理。我们直接说，费米子都是泡利不相容的。

### 9.3 量子分布函数

在量子统计视角下，全同粒子作为一个大前提，我们应该改变描述系统的方式。也就说，对于一个由同一种粒子组成的系统，考虑其所有可能能级（就是所有可能状态），只要知道这个系统各个能级上的粒子数，就确定了这个系统的微观状态。所以粒子在能级上的分布很重要，取平均，就得到宏观效应。

对于一个正则系综，我们可以对这几种不同情况，分析在各个能级上粒子分布的数目的平均值。我们其实已经知道经典情况应与Maxwell-Boltmann分布相协同。

> 一般的讨论来说，我们有配分函数：$$Z(\beta)=\sum_{n_1,n_2,...}e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}$$ 这种配分函数的书写方式天然地适合量子统计 <br> 对于特定能级 $\varepsilon_s$ 上的占据的粒子数，利用正则分布的特点： $$\begin{align*}\bar{n_s}&=\frac{\sum n_se^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...+n_s\varepsilon_s+...)}}{\sum e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...+n_s\varepsilon_s+...)}}\\&=-\frac{1}{\beta}\frac{\frac{{ \rm d}}{{ \rm d}\varepsilon_s}(\sum e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...+n_s\varepsilon_s+...)})}{\sum e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...+n_s\varepsilon_s+...)}}\\&=-\frac{1}{\beta}\frac{{ \rm d}}{{ \rm d}\varepsilon_s}\ln Z \end{align*}$$

我们考虑一个特殊的情况：光子分布

#### Plank 分布

对于一种我们了解的微观粒子——光子，是没有泡利不相容性的，也就是说光子是一种玻色子（这下知道为什么光子自旋是 $\hbar$，而电子是 $\frac{\hbar}{2}$ 了），同时光子只是传递电磁相互作用而已，或者说是携带电磁能量的载体，本身不应该有粒子数的限制，光子是可以被发射和吸收的，没有光子数守恒这种说法。那么这种情况下，配分函数计算时，不需要约束粒子的数目，所以：

$$\begin{align*} Z(\beta)&=\Big(\sum_{n_1=0}^\infty e^{-\beta n_1\varepsilon_1}\Big)\Big(\sum_{n_2=0}^\infty e^{-\beta n_2\varepsilon_2}\Big)...\Big(\sum_{n_s=0}^\infty e^{-\beta n_s\varepsilon_s}\Big)... \\&=\frac{1}{1-e^{-\beta\varepsilon_1}}\frac{1}{1-e^{-\beta\varepsilon_2}}...\frac{1}{1-e^{-\beta\varepsilon_s}}...\end{align*}$$

则可以计算得各个能级上的平均分布粒子数：

$$\begin{align*} \bar{n_s}&=\frac{1}{\beta}\frac{{ \rm d}}{{ \rm d}\varepsilon_s}\Big(\sum_j\ln(1-e^{-\beta\varepsilon_j})\Big)\\&=\frac{1}{\beta}\frac{\beta e^{-\beta\varepsilon_s}}{1-e^{-\beta\varepsilon_s}}\\&=\frac{1}{e^{\beta\varepsilon_s}-1} \end{align*}$$

如果带入 $\varepsilon=\hbar \omega$，就会得到Plank对光子分布的统计。所以这种情况，我们实际上是对没有数量约束的玻色子进行了分布数目的统计。

#### Femi-Dirac 分布
我们实际上考虑的系统一般是有粒子数约束的。比如电子系统，一般而言电子作为一种基本粒子不会太容易的湮灭或产生，而且在稳恒电路中，我们也认为电子数目稳定了，这时有粒子数守恒。而有粒子数守恒时，费米子在同一个能级上不会有多于一个粒子，感觉上会好计算一些。那么我们有：

$$\begin{align*}Z(\beta)&=\sum_{n_1=0,1;n_2=0,1;...}^{n_1+n_2...=N}e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}\end{align*}$$

我们可以看出这时这个配分函数由于过多的隐含约束，求取已经有困难。我们直接看粒子数分布能不能直接计算：

$$\begin{align*}\bar{n_s}&=\frac{\sum n_se^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...+n_s\varepsilon_s+...)}}{\sum e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...+n_s\varepsilon_s+...)}}\\&=\frac{0+e^{-\beta\varepsilon_s}\sum_s e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}}{\sum e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...+n_s\varepsilon_s+...)}}\end{align*}$$

其中$\sum_s$表示求和时直接丢弃对 $\varepsilon_s$ 的求和，同时，总约束粒子数等效的为 $N-1$ 个。所以我们也许可以定义 $Z_s(N-1)=\sum_s e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}$。

或者更有物理图像的，直接将这个系统的 $\varepsilon_s$ 能级删掉后，这样的系统在有 $M$ 个粒子时配分函数为 $Z_s(M)$

那么我们可以将分布数写成：
$$\begin{align*}\bar{n_s}&=\frac{0+e^{-\beta\varepsilon_s}\sum_s e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}}{\sum e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...+n_s\varepsilon_s+...)}}\\&=\frac{e^{-\beta\varepsilon_s}Z_s(N-1)}{Z_s(N)+e^{-\beta\varepsilon_s}Z_s(N-1)}\\&=\frac{1}{1+e^{\beta\varepsilon_s}Z_s(N)/Z_s(N-1)}\end{align*}$$

我们需要估计 $Z_s(N)/Z_s(N-1)$ 是什么。为此，我们进行一个合理的近似。如果一个系统的能级足够多，那显然，物理意义上其多一个能级和少一个能级又能有多大区别呢？这造成不了多大的影响，所以我们取近似：

$$Z_s(M)\approx Z(M)$$

而对于一个系统的配分函数，我们可以定义：

$$\alpha = \frac{\partial}{\partial N}\ln Z(N)$$

那么我们可以有，在粒子数 $N$ 足够大时，进一步的近似：

$$\alpha = \frac{\partial}{\partial N}\ln Z(N) \approx \frac{\ln Z(N)-\ln Z(N-1)}{N-(N-1)}=\ln(\frac{Z(N)}{Z(N-1)}) $$

也就是说，我们近似：
$$\frac{Z_s(N)}{Z_s(N-1)}\approx\frac{Z(N)}{Z(N-1)}\approx e^\alpha$$

有两个近似条件：1.系统的能级足够多；2.系统中粒子数目足够多

而 $\alpha$ 有鲜明的物理含义：
$$\alpha = \frac{\partial \ln Z}{\partial N}=-\frac{1}{kT}\frac{\partial (-kT\ln Z)}{\partial N}=-\beta\Big(\frac{\partial F}{\partial N}\Big)_{V,T}=-\beta\mu$$

$\mu$ 就是这种粒子之间的化学势，在第8章中讨论过。它就像温度指导热流的自发流动方向一样，化学势指导粒子流的自发流动方向。（注：其实不是指导，而是表征，这里采取酷一点的说法而已）

所以在这种近似下，有Femi-Dirac分布：

$$\bar{n_s}=\frac{1}{e^{\alpha+\beta\varepsilon_s}+1}=\frac{1}{e^{\beta(\varepsilon_s-\mu)}+1}$$

这个式子也保证了 $\bar{n_s}\in[0,1] $

#### Bose-Einstein 分布

在前面的经验下，我们可以对一般的玻色子系统发展统计方法得到平均分布数目。这时与对费米子系统进行统计时，有一样的困难。隐含的约束条件令人难以进行计算，我们可以采取相似的近似，尝试得到结果。

$$\begin{align*}\bar{n_s}&=\frac{0+e^{-\beta\varepsilon_s}\sum_s^{N-1} e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}+2e^{-2\beta\varepsilon_s}\sum_s^{N-2} e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}+...}{\sum^N e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...+n_s\varepsilon_s+...)}}\\&=\frac{0+e^{-\beta\varepsilon_s}\sum_s^{N-1} e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}+2e^{-2\beta\varepsilon_s}\sum_s^{N-2} e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}+...}{\sum_s^N e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}+e^{-\beta\varepsilon_s}\sum_s^{N-1} e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}+e^{-2\beta\varepsilon_s}\sum_s^{N-2} e^{-\beta(n_1\varepsilon_1+n_2\varepsilon_2+...)}+...}\\&=\frac{e^{-\beta\varepsilon_s}Z_s(N-1)+2e^{-2\beta\varepsilon_s}Z_s(N-2)+...}{Z_s(N)+e^{-\beta\varepsilon_s}Z_s(N-1)+e^{-2\beta\varepsilon_s}Z_s(N-2)+...}\\&=\frac{\sum_{m=0}^N me^{-m\beta\varepsilon_s}Z(N-m)/Z(N)}{\sum_{m=0}^N e^{-m\beta\varepsilon_s}Z(N-m)/Z(N)}\end{align*}$$

我们首先要先采取第一个近似，那就是后面加上的项由于 $m$ 是相对较大正整数 $e^{-m\beta\epsilon_s}$ 因子的存在，都很小，所以对后面的项估计就算有一些大的误差也没有关系。接着再用我们刚刚在推导Femi-Dirac分布时运用的两个近似，要求系统能级和粒子数足够大。

在 m 不太大时，即 $m<<N$ ，可以估计：

$$ \ln \frac{Z(N-m)}{Z(N)}=\ln Z(N-m)-\ln Z(N)=-m\frac{\ln Z(N-m)-\ln Z(N)}{(N-m)-N}\approx-m\alpha$$

即可以有估计：

$$\frac{Z(N-m)}{Z(N)}\approx e^{-m\alpha}$$

这个估计在 $m$ 比较小时比较好。不过我们在 $m$ 比较大的时候也用。因为就算 $m$ 比较大时这个估计比较松弛，$e^{-m\beta\varepsilon_s}$ 因子的存在却又弥补了这一点。使用这个近似，我们得到：

$$\begin{align*} \bar{n_s}&= \frac{\sum_{m=0}^N me^{-m(\alpha+\beta\varepsilon_s)}}{\sum_{m=0}^N e^{-m(\alpha+\beta\varepsilon_s)}}\\&=-\frac{1}{\beta}\frac{\frac{{ \rm d}}{{ \rm d}\varepsilon_s}\sum_{m=0}^N e^{-m(\alpha+\beta\varepsilon_s)}}{\sum_{m=0}^N e^{-m(\alpha+\beta\varepsilon_s)}}\\&=-\frac{1}{\beta}\frac{{ \rm d}}{{ \rm d}\varepsilon_s}\ln\Big(\sum_{m=0}^N e^{-m(\alpha+\beta\varepsilon_s)}\Big)\\&=-\frac{1}{\beta}\frac{{ \rm d}}{{ \rm d}\varepsilon_s}\ln\Big(\frac{1}{1-e^{-(\alpha+\beta\varepsilon_s)}}\Big)\\&=\frac{1}{\beta}\frac{{ \rm d}}{{ \rm d}\varepsilon_s}\ln(1-e^{-(\alpha+\beta\varepsilon_s)})\\&=\frac{1}{\beta}\frac{\beta e^{-(\alpha+\beta\varepsilon_s)}}{1-e^{-(\alpha+\beta\varepsilon_s)}}\\&=\frac{1}{e^{\alpha+\beta\varepsilon_s}-1} \end{align*}$$

所以这就是Bose-Einstein分布，一样可以解释为化学势：

$$\bar{n_s}=\frac{1}{e^{\alpha+\beta\varepsilon_s}-1}=\frac{1}{e^{\beta(\varepsilon_s-\mu)}-1}$$

而在没有粒子数约束时，谈不上化学式，$\mu =0$ ，自然退化为Plank分布。

最后，我们看看经典情况。也就是所谓的
#### Maxwell-Boltzmann分布

在这种表述下，配分函数实际上是N个单粒子配分函数乘积（由于互不影响）：
$$Z(\beta)=\Big(\sum_r e^{-\beta\varepsilon_r}\Big)^N$$
所以可以计算出：
$$\begin{align*}\bar{n_s}&=-\frac{1}{\beta}\frac{ {\rm d}}{{ \rm d}\varepsilon_s}\ln Z\\&=-\frac{N}{\beta}\frac{ {\rm d}}{{ \rm d}\varepsilon_s}\ln\Big(\sum_r e^{-\beta\varepsilon_r}\Big)\\&=-\frac{N}{\beta}\frac{-\beta e^{-\beta\varepsilon_s}}{\sum_r e^{-\beta\varepsilon_r}}\\&=Ne^{-\beta\varepsilon_s}/\sum_r e^{-\beta\varepsilon_r}\end{align*}$$

这时，分布正比于 $e^{-\beta\varepsilon_s}$ ，典型的Maxell-Boltmann分布。

### 9.4 巨配分函数统计法

实际上，我们可以利用一些统计手段，绕开这令人烦恼的隐含约束，把配分函数求出来，或者说，把我们关注的 $\ln Z$ 求出来。一般，当我们谈论到统计方法，在物理上，就是一套求取配分函数的方法。

#### Bose-Einstein 统计

我们貌似以前遇到过相似的问题，有一个烦人的约束，牵制我们。 那就是在微正则系综的计算中，我们有一个约束，那就是系统总能量一定，这时后我们对状态求和要有状态能量为 $E$ 的约束。当时，我们想到了一个很好的办法，利用正则系综，在一定角度下退化回微正则系综。如何做到？物理上，我们视孤立系统实际上和一个热库接触，但是由于二者温度相同，所以没有交换，但是我们还是可以直接将这个系统用正则系综的方式来讨论。数学上，我们引入了因子 $e^{-\beta E'}$ ，而实际真实的 $\beta$
即是让状态数取峰值的情况，即 $E'=E$ 取极值 。

那么对于有一个粒子数约束的情况，我们可以尝试做类似的事情，取一个因子 $e^{-\alpha N'}$，让系统粒子数可变，但是实际情况是取极值的时候 $N$ 是实际的粒子数。我们便定义巨配分函数：

$$\mathcal{Z}:=\sum_{N'}Z(N')e^{-\alpha(N) N'}$$

这里的求和是关键的，因为只有求和掉，表达式才与粒子数无关。而 $Z(N')$ 随 $N'$ 增长极快，$e^{-\alpha N'}$ 随 $N'$ 衰减极快，所以这是一个很尖锐的函数！我们可以直接取近似：

$$\mathcal{Z}=Z(N)e^{-\alpha N}\Delta^*N$$

其中 $\Delta^*N$ 只是一个常数而已。

而实际粒子数 $N$ 决定这里的参数 $\alpha(N)$，决定条件，即 $\mathcal{Z}$取极值。也即 $\ln \mathcal{Z}$取极值：

$$\frac{\partial}{\partial N'}\ln \mathcal{Z}=\frac{\partial \ln Z(N')}{\partial N'}-\alpha=0$$

这说明 $\alpha=\frac{\partial \ln Z(N')}{\partial N'}$，这和我们上一节用到的参数 $\alpha$ 是一回事！$\alpha = -\beta \mu$

在这种近似下，我们得到：

$$\ln \mathcal{Z} = \ln Z-\alpha N +{ \rm const.}$$

而这个加和形式的常数通常是无所谓的，我们可以直接取：

$$\ln Z(N) = N\alpha(N)+ \ln \mathcal{Z} $$

我们将 $\alpha(N)$ 解出来，即对 $N$ 求导：
$$ \frac{\partial \ln Z(N)}{\partial N} = \alpha + N\frac{\partial \alpha}{\partial N} + \frac{\partial \ln \mathcal{Z}}{\partial N} $$

而 $\frac{\partial \ln Z(N)}{\partial N} = \alpha$，所以可以直接得到：

$$N\frac{\partial \alpha}{\partial N} + \frac{\partial \ln \mathcal{Z}}{\partial N} = (N+\frac{\partial \ln \mathcal{Z}}{\partial \alpha})\frac{\partial \alpha}{\partial N}=0$$

由于一般而言，$\alpha(N)$ 是与 $N$ 相关的。所以我们得到 $N(\alpha)$ 应该满足方程：

$$N+\frac{\partial \ln \mathcal{Z}}{\partial \alpha}=0$$

作为隐函数，确定 $\alpha$。

那么这里我们就可以直接计算玻色子的情况：

$$\begin{align*}\mathcal{Z}&=\sum_{n_1,n_2,...}e^{-\beta (n_1\varepsilon_1+n_2\varepsilon_2+...)}e^{-\alpha (n_1+n_2+...)}\\&=\Big(\sum_{n_1=0}^{\infty}e^{-n_1(\alpha+\beta\varepsilon_1)}\Big)\Big(\sum_{n_2=0}^{\infty}e^{-n_2(\alpha+\beta\varepsilon_2)}\Big)...\\&=\frac{1}{1-e^{-(\alpha+\beta\varepsilon_1)}}\frac{1}{1-e^{-(\alpha+\beta\varepsilon_2)}}...\end{align*}$$

所以我们可以确定，$$N(\alpha)=-\frac{\partial \ln \mathcal{Z}}{\partial \alpha}=\frac{\partial}{\partial \alpha}\sum_{r}\ln(1-e^{-(\alpha+\beta\varepsilon_r)})=\sum_r\frac{1}{e^{(\alpha+\beta\varepsilon_r)}-1}$$

现在，可以解得 $\alpha$ 已经由此确定为一个确定的参数了。

所以我们就有：

$$\begin{align*}\ln Z(N) &= N\alpha-\sum_{r}\ln(1-e^{-(\alpha+\beta\varepsilon_r)})\end{align*}$$

这是Bose-Einstein统计的重要结果。

所以可以求得分布函数：

$$\begin{align*}\bar{n_s}&=-\frac{1}{\beta}\frac{{ \rm d}}{{ \rm d}\varepsilon_s}\ln Z \\&=\frac{1}{\beta}\frac{\beta e^{-(\alpha+\beta\varepsilon_s)}}{1-e^{-(\alpha+\beta\varepsilon_s)}}\\&=\frac{1}{e^{\alpha+\beta\varepsilon_s}-1}=\frac {1}{e^{\beta(\varepsilon_s-\mu)}-1}  \end{align*}$$

#### Femi-Dirac 统计
实际上，我们也就可以用相同的技巧，规避在费米子系统中，规避总粒子数的约束。但是泡利不相容还是有的。

$$\begin{align*}\mathcal{Z}&=\sum_{n_1=0,1;n_2=0,1;...}e^{-\beta (n_1\varepsilon_1+n_2\varepsilon_2+...)}e^{-\alpha (n_1+n_2+...)}\\&=\Big(\sum_{n_1=0}^{1}e^{-n_1(\alpha+\beta\varepsilon_1)}\Big)\Big(\sum_{n_2=0}^{1}e^{-n_2(\alpha+\beta\varepsilon_2)}\Big)...\\&=(1+e^{-(\alpha+\beta\varepsilon_1)})(1+e^{-(\alpha+\beta\varepsilon_2)})...\end{align*}$$

进而对于费米子系统： $$\ln\mathcal{Z}=\sum_r\ln(1+e^{-(\alpha+\beta\varepsilon_r)})$$

一样可以确定参数 $\alpha$

$$N = -\frac{\partial \ln \mathcal{Z}}{\partial \alpha}=\sum_r\frac{1}{e^{\alpha+\beta \varepsilon_r}+1}$$

同时，有Femi-Dirac统计的结果：

$$\ln Z = N\alpha +\ln \mathcal{Z}=N\alpha +\sum_r\ln(1+e^{-(\alpha+\beta\varepsilon_r)})$$

所以，我们最终可以清楚地得到分布函数：

$$\begin{align*}\bar{n_s}&=-\frac{1}{\beta}\frac{{ \rm d}}{{ \rm d}\varepsilon_s}\ln Z \\&=\frac{1}{\beta}\frac{\beta e^{-(\alpha+\beta\varepsilon_s)}}{1+e^{-(\alpha+\beta\varepsilon_s)}}\\&=\frac{1}{e^{\alpha+\beta\varepsilon_s}+1}=\frac {1}{e^{\beta(\varepsilon_s-\mu)}+1}  \end{align*}$$

综上所述，我们得到了有用的量子系统配分函数：
$$\ln Z = N\alpha +\ln \mathcal{Z}=N\alpha \pm\sum_r\ln(1\pm e^{-(\alpha+\beta\varepsilon_r)})$$

其中正负由系统是玻色子系统还是费米子系统决定。费米子系统取正，玻色子系统取负。

### 9.5 量子统计的经典极限

我们知道，我们的经典经验在一定程度上，反映了事物在一定条件下的客观规律。我们姑且认为上面的巨配分函数统计法是一种量子统计，那么在一定条件下，它应该与经典统计的结果相协调。我们直接看配分函数：

$$\begin{cases}\ln Z = N\ln(\sum_re^{-\beta\varepsilon_r})\quad { \rm MB}\\\ln Z = N\alpha-\sum_r\ln(1-e^{-(\alpha+\beta\varepsilon_r)})\quad{ \rm BE}\\\ln Z = N\alpha+\sum_r\ln(1+e^{-(\alpha+\beta\varepsilon_r)})\quad{ \rm FD}\end{cases}$$

这是3种统计法视角下，得到的配分函数。下面两种虽然是不同种类的粒子，但是应当都能给出经典统计的结果。

其对应的分布有：
$$\begin{cases}\bar{n_s} = Ne^{-\beta\varepsilon_s}/\sum_r e^{-\beta\varepsilon_r}\quad { \rm MB}\\\bar{n_s} =1/(e^{\alpha+\beta\varepsilon_s}-1)\quad{ \rm BE}\\\bar{n_s} = 1/(e^{\alpha+\beta\varepsilon_s}+1)\quad{ \rm FD}\end{cases}$$

我们统一表述两种情况：
$$\bar{n_s}=\frac{1}{e^{\alpha+\beta\varepsilon_s}\pm1}\quad\ln Z=N\alpha \pm\sum_r\ln(1\pm e^{-(\alpha+\beta\varepsilon_r)})$$

我们回忆理想气体的使用条件，高温低压。这给我们一定的提示，那就是在高温低浓度的情况下，也许可以把量子统计的结果极限为经典统计。

高温的条件很显然，即 $\beta\to 0^+$ ；低浓度，某种意义上来说，就是粒子的数目相较于能级来说少得多。物理图像上，由于粒子比能级少得多，那处于同一能级的情况就很难出现，掩盖了的费米子的不相容性。数学上，我们就是在要求 $\bar{n_r}<< 1$ 。

低浓度的条件，就是要求 $e^{\alpha+\beta \varepsilon_r}>>1$，即 $e^{-(\alpha+\beta \varepsilon_r)}\to0^+$

进而我们清楚的了解到在这种条件下，对于分布来说，有没有1不重要，有：

$$\bar{n_s}=\frac{1}{e^{\alpha+\beta\varepsilon_s}\pm1}\approx e^{-(\alpha+\beta \varepsilon_s)}$$

进而: 
$$N \approx \sum_r e^{-(\alpha+\beta \varepsilon_r)}\Rightarrow e^{-\alpha}\approx N/\sum_re^{-\beta\varepsilon_r}$$

进而，我们回代，得到:

$$\bar{n_s}\approx Ne^{-\beta \varepsilon_s}/\sum_re^{-\beta\varepsilon_r}$$

确实可以得到Maxwell-Bolzmann分布。

由于高温条件，我们了解到 $e^{-\beta \varepsilon_r}\to 1$，所以为了满足低浓度的近似，这时本质上我们要求了 $\alpha>>\beta \varepsilon_r$，也就是说我们实际上可以取得：

所以，有：
$$ \begin{align*} \ln Z &= N\alpha \pm\sum_r\ln(1\pm e^{-(\alpha+\beta\varepsilon_r)})\\&\approx N\alpha \pm\sum_r \pm e^{-(\alpha+\beta\varepsilon_r)}\\&=N\alpha+\sum_r e^{-(\alpha+\beta\varepsilon_r)}\\&\approx N\alpha +N\\&\approx N\ln\Big(\sum_r  e^{-\beta\varepsilon_r}\Big)-N\ln N+N \\&\neq N\ln\Big(\sum_r  e^{-\beta\varepsilon_r}\Big) \end{align*} $$

在这样的近似下，我们还是没办法给出原来的统计模型，看得出来，量子配分函数和经典配分函数之间就是差了个 $N!$ 因子。全同粒子是本质的，不能随便近似一下就极限掩盖掉。这也是Gibbs佯谬能够提出，并成为经典统计困难的一个本质原因。

回到我们9.1中的讨论方法，我们要对那种方法进行批判。

虽然看上去我们在那是在讨论量子统计，但实际这个理论并不是一个完全彻底的量子的理论。原因很简单，我们实际上还是近似在用广义动量和广义动量来描述微观粒子的状态，并且只是为相格进行了一点点辩护，利用不确定性关系强行定义了 $h$ 普朗克常数的间隔大小。实际上，这一套就是上世纪初旧量子论的逻辑，认为一组正则坐标是量子化的突破点，进行圈积分得到普朗克常数的整数倍（这套逻辑是错误的，只是一个巧合，碰巧能解决一些问题）。

所以在一定程度上，这也仅仅是理想气体模型的一种“量子”统计理论。

而现在进行的这一套巨配分函数统计法，是引入全同粒子假设的，量子论的，但是语言上，并不是彻底的量子统计。而且也有一定程度的近似，是对本征态的统计。

真正的量子统计应该是这样的——建立在希尔伯特空间中，用态矢量或者密度矩阵描述系统状态，用算符的语言，在新量子论的框架（也就是现有量子力学框架）下，进行的一套全新的统计方法。对于本科生的热统课程来说，可以先按下不表了。

### 9.6 理想气体的量子模型

#### 理想气体分子满足的运动方程

实际上，我们还是要稍微深入的了解一下理想气体的微观粒子的量子解。对于理想气体，我们认为其没有内势能，所以其单个粒子的哈密顿量没有势能项，于是：

$$\hat{H}=\frac{\hat{p}^2}{2m}$$

运用薛定谔方程 $\hat{H}|\psi\rang=i\hbar\frac{\partial}{\partial t}|\psi\rang$ ，考虑其本征态，即定态薛定谔方程 $\hat{H}|\psi\rang=\varepsilon |\psi\rang$

$$\frac{1}{2m}\lang\vec{r}|\hat{p}^2|\psi(t)\rang=i\hbar\frac{\partial}{\partial t}\lang\vec{r}|\psi(t)\rang=\varepsilon\lang\vec{r}|\psi(t)\rang$$

从波函数定义的角度说：$\psi(\vec{r},t)=\lang\vec{r}|\psi(t)\rang$，以及 $\lang\vec{r}|\hat{p}|\psi(t)\rang = -i\hbar\nabla\psi(\vec{r},t)$，我们得到能量本征波函数满足：

$$\frac{\hbar^2}{2m}\nabla^2\psi(\vec{r})-\varepsilon\psi(\vec{r})=0$$

这显然有解，为：
$$\psi(\vec{r})=A_0e^{i\vec{\kappa}\cdot\vec{r}},\quad \kappa^2=\frac{2m\varepsilon}{\hbar^2}$$

在经典物理意义上，动量 $p^2=2m\epsilon=\hbar^2\kappa^2$，而这个本征解在运动时，有：

$$\psi(\vec{r},t)=A_0e^{i(\vec{\kappa}\cdot\vec{r}-\omega t)},\quad \omega = \frac{\varepsilon}{\hbar}$$

这是理想气体分子概率波在无穷大空间中的本征态，由这些简谐振动模式可以叠加出所有可能。

#### 紧致化

为了实际处理的方便，讨论态密度等概念，我们在理论上要进行紧致化操作。无穷大空间确实不是紧的，但是我们只要加上一些边界条件，就可以将空间紧致化——即有界。我们一个常用的手段是，引入周期性边界条件：在三个直角坐标系维度下，各有 $L_x,L_y,L_z$ 的周期性。实际上，我们也可以等效的取箱边界条件，即在边界上波函数是0.

这时，我们确定了本征函数的波矢只能取一些离散的值：
$\kappa_x = \frac{2\pi}{L_x}n_x,\kappa_y = \frac{2\pi}{L_y}n_y,\kappa_z = \frac{2\pi}{L_z}n_z$。这里 $n_x,n_y,n_z\in \mathbb{Z}$ ，所以这时，我们确定：

$$\varepsilon = \frac{\hbar^2\kappa^2}{2m}=\frac{2\pi^2\hbar^2}{m}\Big(\frac{n_x^2}{L_x^2}+\frac{n_y^2}{L_y^2}+\frac{n_z^2}{L_z^2}\Big)$$

而对于一个量子数的变化，能引起的波矢变化有：

$${ \rm d}\kappa_x=\frac{2\pi}{L_x}\Delta n_x=\frac{2\pi}{L_x}$$

进而：
$${ \rm d}\kappa_x{ \rm d}\kappa_y{ \rm d}\kappa_z = \frac{(2\pi)^3}{L_xL_yL_z}=\frac{(2\pi)^3}{V}$$

即有状态密度 $\rho(\vec{\kappa}){ \rm d}^3\vec{\kappa} = 1, \quad \rho(\vec{\kappa}) = \frac{V}{(2\pi)^3} $

这表征了在某空间中，多大的变化会包括进来一个新的态，也就是所谓的态密度。

我们可以考虑其它物理量的态密度：由于 $\vec{p}=\hbar\vec{\kappa}$

所以
$${ \rm d}p_x{ \rm d}p_y{ \rm d}p_z=\hbar^3{ \rm d}\kappa_x{ \rm d}\kappa_y{ \rm d}\kappa_z = \frac{h^3}{L_xL_yL_z}=\frac{h^3}{V}$$

我们也就得到 $\rho(\vec{p})=\frac{V}{h^3}$

我们阐明清楚，其意义在于：

在 $\vec{\kappa}\sim\vec{\kappa}+{ \rm d}\vec{\kappa}$ 中包含态的个数是：$\rho(\vec{\kappa}){ \rm d}^3\vec{\kappa}=\frac{V}{(2\pi)^3}{ \rm d}^3\vec{\kappa}$

在 $\vec{p}\sim\vec{p}+{ \rm d}\vec{p}$ 中包含态的个数是：$\rho(\vec{p}){ \rm d}^3\vec{p}=\frac{V}{h^3}{ \rm d}^3\vec{p}$

进一步，我们可以得到：

关于波矢大小的态函数：$\rho(\kappa)=4\pi\kappa^2\rho(\vec{\kappa})=\frac{V}{2\pi^2}\kappa^2$

关于能量的态函数，有：

$$\rho(\varepsilon){ \rm d}\varepsilon = \rho(\kappa){ \rm d}\kappa = \frac{V}{2\pi^2}\kappa^2{ \rm d}\kappa $$

注意到 $\varepsilon = \frac{\hbar^2\kappa^2}{2m}$，有 $\frac{{ \rm d}\kappa}{{ \rm d}\varepsilon}=\frac{1}{\hbar}\sqrt{\frac{m}{2\varepsilon}}$

则有：
$$\rho(\varepsilon)= \frac{V}{2\pi^2}\frac{2m\varepsilon}{\hbar^2}\frac{1}{\hbar}\sqrt{\frac{m}{2\varepsilon}}=\frac{V}{4\pi^2}\frac{(2m)^{3/2}}{\hbar^3}\sqrt{\varepsilon}$$

这些计算，让我们确定了一个确定体积的理想气体的能级密度情况。能级密度本身是系统结构，与温度没有关系。

注意，我们这里的希尔伯特空间其实不一定是完备的，因为我们回避了粒子自旋。我们近似认为，这里有自旋简并，也就是说，一个能级上可以有自旋不同的粒子占据，这才是有自旋的粒子的实际情况。

### 9.7 费米面与费米温度

我们回到已有的讨论，接下的目的是进行费米子统计的讨论，因为比较特殊，可以将导体中的电子气运用我们上述的讨论，得到一些有用的结论。

#### 费米面

首先，我们知道费米子的分布函数：
$$\bar{n_s}=\frac{1}{e^{\alpha+\beta \varepsilon_s}+1}=\frac{1}{e^{\beta(\varepsilon_s-\mu)}+1}$$

那么，在极低温的情况下，这个分布函数很有趣，$\beta\to +\infty$ ，这时若 $\varepsilon_s>\mu$，则分母无穷大，$\bar{n_s}\to 0$；这时若 $\varepsilon_s<\mu$，则分母趋于1，$\bar{n_s}\to 1$.

也就是说，低温情况下，粒子都乖乖地呆在尽可能低地能级，将低能级塞满。而化学势 $\mu$ 就像一个大坝一样，拦住粒子们，只能呆在这 “费米面” 之下。在这种图像下，我们也可以看出费米能（化学势）$\mu$ 和体系粒子数是紧密相关的。

对于一个体积为 $V$ 的金属导体，我们有其态密度：$\rho(\vec{\kappa}) = \frac{V}{(2\pi)^3}$

对于有确定费米能 $\mu$ 的系统，有其占据的能级，必有能量在费米能之下，即：$$\varepsilon=\frac{\hbar^2\kappa^2}{2m}\leq\mu$$

取 $\kappa_F= \frac{\sqrt{2m\mu}}{\hbar}$ ，即最大可能的波矢大小。那么直接就可以计算出总共的粒子数：(利用 $\rho(\vec{\kappa})$ 的均匀性，以及电子自旋有两种取向，$\pm \frac{1}{2}$)，我们这里例演示电子的情况。

$$N = \frac{4}{3}\pi\kappa_F^3\rho(\vec{\kappa})\times 2=\frac{V}{3\pi^2}\kappa_F^3$$

进而，有：

$$\kappa_F = \Big(\frac{3\pi^2N}{V}\Big)^{\frac{1}{3}}$$

$$\mu = \frac{\hbar^2}{2m}\Big(\frac{3\pi^2N}{V}\Big)^{\frac{2}{3}}$$

$$\lambda_F = \frac{2\pi}{\kappa_F}=2\Big(\frac{\pi}{3}\frac{V}{N}\Big)^{\frac{1}{3}}$$

所有 $\lambda>\lambda_F$ 的状态都被占据。我们也看出来，费米能只是粒子数密度的函数，在体积固定时，$\mu\propto N^{\frac{2}{3}}$

#### 费米温度

对于能量较低的能级，$\varepsilon<<\mu$，这时这种能级上的粒子数分布主要由 $-\frac{\mu}{kT}$决定，定义金属的费米温度为： $$T_F:=\mu_0/k$$  其中 $\mu_0$ 就是这种金属的费米能，因为对于特定的金属，其自由电子数密度是恒定的。显然，如果金属的温度远低于费米温度，则 $-\mu/kT = -T_F/T \to -\infty$ 这时候低能级任然将被沾满。即这时，可以近似认为只有费米能附近的能级中的费米子可以「活动」。

注，如果能级比较高，平均占据数就都趋近于0，这个分析是平凡的。

对于铜来说，费米温度 $T_F \approx 80,000 { \rm K}$，远远超出室温以及铜的熔点。所以对于固态金属铜来说，其中的电子总是几乎沾满低能级态。常温下金属中的电子总是高度简并，温度的变化只引起费米能附近能级的粒子数占据状况的改变。

### 9.8 电子气与电子比热

都什么年代了，还在搞经典比热？是时候搞电子的了！（bushi）
我们考虑金属导体中的电子，其收到金属本身的相互作用是弱的，我们近似认为这是一个无势能的体系，所以这时我们相当于对电子套用理想气体模型，也就是所谓的电子气模型。对于电子在固体中的运动，严格意义的讨论在固体物理。

电子气模型实际上就是一种费米理想气体，适用9.6的讨论，在低温情况下适用我们上面9.7的讨论。显然，其在低温时的比热不能用经典理想气体的结论，有 $C_V=\frac{3}{2}Nk$，因为这实际上是能均分定理的结果，要求经典模型。在低温时，不满足经典极限需要的高温低浓度条件，所以低温费米气体，必须重新讨论。

实际上我们的低温指的是，温度远低于费米温度，这一点对于几乎所有固态金属中的电子都是成立的，这时温度的变化，只会引起费米能附近的能级中占据粒子的变动。

#### 定性分析

$$n_s=\frac{1}{e^{-(\varepsilon-\mu)/kT}-1}$$

由于 $T<<T_F$ ，我们近似看到，几乎只有 $\varepsilon\sim\mu\pm kT$ 的数量级范围内能级上的电子分布会改变，也就是说只有这些电子对电子热容有贡献，我们只需要统计这些粒子就可以了。

对于这个范围内的电子，不太收到全同性的干扰，我们近似认为其分布比较经典，可以用Maxwell-Bolzmann分布近似，那么，在这个范围内，有电子数近似为：

$$N_{eff}=\int_{\mu-kT}^{\mu+kT}\rho(\epsilon){ \rm d}\epsilon\approx\rho(\mu)kT$$

- 注：我们这里只是做数量级估计，所以其实 $kT$ 前有一个靠近1的常数都没有关系。最后这个近似相当于估计三角形面积，我们把常数2也就直接丢掉了，毕竟只是估计。

所以我们可以有：

$$C_V=\frac{3}{2}N_{eff}k\approx \frac{3}{2}\rho(\mu)k^2T\propto T$$

而稍微严格一点的定性分析，可以这样直接取：$N_{eff}\approx N\frac{kT}{\mu}=N\frac{T}{T_F}$

这样的取法在于，现象能级崩塌的过程，在原本绝对零度时，参与到这个崩塌的粒子聚集在 $[\mu-kT,\mu]$ 中的能级上，那这些就是有效粒子，可以直接均匀分布得到上面的近似，所以有：

$$C_V\approx\frac{3}{2}Nk\Big(\frac{T}{T_F}\Big)$$

#### 定量严格计算

其实也不算很严格，也用到了很多看上去狂野的近似，但是确实要清晰很多。

考虑到电子系统的平均能量：

$$\bar{E}=\sum_r\frac{\varepsilon_r}{e^{-\beta(\varepsilon-\mu)}+1}=\int_0^{+\infty}\frac{\epsilon}{e^{-\beta(\epsilon-\mu)}+1}2\rho(\epsilon){ \rm d}\epsilon$$

其中 $\rho(\epsilon)$ 是之前计算的能级密度（关于能量），而 $2$ 的因子是因为自旋的两种取向。

对于粒子数确定的系统：

$$N = \int_0^{+\infty}\frac{1}{e^{-\beta(\epsilon-\mu)}+1}2\rho(\epsilon){ \rm d}\epsilon$$

令费米函数：

$$F(\epsilon)=\frac{1}{e^{-\beta(\epsilon-\mu)}+1}$$

下面研究，任意一个性质足够好的函数 $\varphi(\epsilon)$ 与之乘积的积分，因为这个形式在上面反复出现：

$$\int_0^{+\infty}F(\epsilon)\varphi(\epsilon){ \rm d}\epsilon$$

尝试使用分部积分，构造一个原函数：

$$\psi(\epsilon)=\int_0^\epsilon\varphi(\epsilon'){ \rm d}\epsilon'$$

显然：$\psi(0)=0,F(+\infty)=0$

那么就有：

$$\begin{align*}\int_0^{+\infty}F(\epsilon)\varphi(\epsilon){ \rm d}\epsilon&=F(\epsilon)\psi(\epsilon)|^{+\infty}_0-\int_0^{+\infty}F'(\epsilon)\psi(\epsilon){ \rm d}\epsilon\\&=-\int_0^{+\infty}F'(\epsilon)\psi(\epsilon){ \rm d}\epsilon\end{align*}$$

然而，$F'(\epsilon)$ 应该和一个负的delta函数差不多，因为只有在费米能附近有变化。所以我们只需要关注 $\psi(\epsilon)$ 在 $\mu$ 附近的行为就可以了，将其在 $\mu$ 附近泰勒展开：

$$\psi(\epsilon)=\sum_{m=0}^\infty \frac{1}{m!}\psi^{(m)}(\mu)(\epsilon-\mu)^m$$

我们实际计算：

$$F'(\epsilon)=-\frac{\beta e^{-\beta(\epsilon-\mu)}}{(e^{-\beta(\epsilon-\mu)}+1)^2}$$

带回：
$$\begin{align*}\int_0^{+\infty}F(\epsilon)\varphi(\epsilon){ \rm d}\epsilon&=-\int_0^{+\infty}F'(\epsilon)\psi(\epsilon){ \rm d}\epsilon\\&=\sum_{m=0}^{\infty}\int_0^{+\infty}\frac{\beta e^{-\beta(\epsilon-\mu)}}{(e^{-\beta(\epsilon-\mu)}+1)^2}\frac{1}{m!}\psi^{(m)}(\mu)(\epsilon-\mu)^m{ \rm d}\epsilon\\&=\sum_{m=0}^{\infty}\frac{1}{m!}\psi^{(m)}(\mu)\int_0^{+\infty}\frac{\beta e^{-\beta(\epsilon-\mu)}}{(e^{-\beta(\epsilon-\mu)}+1)^2}(\epsilon-\mu)^m{ \rm d}\epsilon\\&=\sum_{m=0}^{\infty}\frac{\beta^{-m}}{m!}\psi^{(m)}(\mu)\int_0^{+\infty}\frac{ e^{-\beta(\epsilon-\mu)}}{(e^{-\beta(\epsilon-\mu)}+1)^2}(\beta(\epsilon-\mu))^m{ \rm d}(\beta(\epsilon-\mu))\\&=\sum_{m=0}^{\infty}\frac{\beta^{-m}}{m!}\psi^{(m)}(\mu)\int_{-\beta\mu}^{+\infty}\frac{x^m e^{-x}}{(e^{-x}+1)^2}{ \rm d}x\end{align*}$$

由于 $\beta\mu=T_F/T\to+\infty$，而且趋于负无穷时，被积函数也趋于0，所以我们直接取积分下限为 $-\infty$，也没有太大的误差，这里近似一次：

$$\begin{align*}\int_0^{+\infty}F(\epsilon)\varphi(\epsilon){ \rm d}\epsilon&=\sum_{m=0}^{\infty}\frac{\beta^{-m}}{m!}\psi^{(m)}(\mu)\int_{-\beta\mu}^{+\infty}\frac{x^m e^{-x}}{(e^{-x}+1)^2}{ \rm d}x\\&\approx\sum_{m=0}^{\infty}\frac{\beta^{-m}}{m!}\psi^{(m)}(\mu)\int_{-\infty}^{+\infty}\frac{x^m e^{-x}}{(e^{-x}+1)^2}{ \rm d}x\end{align*}$$

计算：

$$I_m=\int_{-\infty}^{+\infty}\frac{x^m e^{-x}}{(e^{-x}+1)^2}{ \rm d}x=\int_{-\infty}^{+\infty}\frac{x^m}{(e^{-x}+1)(e^x+1)}{ \rm d}x$$

显然，被积函数在 $m$ 是奇数时，是奇函数，积分结果为0。而在 $m$ 是偶数时，有积分结果：

$$\begin{align*}I_{2n}&=2\int^0_{-\infty}\frac{x^{2n} e^{-x}}{(e^{-x}+1)^2}{ \rm d}x\\&=2\int^0_{-\infty}(-x)^{2n}{ \rm d}(\frac{1}{e^{-x}+1})\\&=2\int^0_{+\infty}x^{2n}{ \rm d}(\frac{1}{e^x+1})\\&=\frac{2x^{2n}}{e^x+1}\Big|_{+\infty}^{0}+2\int_0^{+\infty}\frac{2nx^{2n-1}}{e^x+1}{ \rm d}x\\&=4n\int_0^{+\infty}\frac{x^{2n-1}}{e^x+1}{ \rm d}x\end{align*}$$

这个积分我们在数学附录5中讨论了，可以得到结果：

$I_{2n}=\frac{2^{2n-1}-1}{2^{2n-3}}(2n-1)!n\zeta(2n)$

有 $I_2 = 4\times \frac{\pi^2}{12}=\frac{\pi^2}{3}$

特别讨论 $m=0$ 的情况，有：

$$I_0 = 2\int^0_{-\infty}{ \rm d}(\frac{1}{e^{-x}+1})=\frac{2}{e^x+1}\Big|_{+\infty}^{0}=1$$

所以最终我们得到：

$$\begin{align*}\int_0^{+\infty}F(\epsilon)\varphi(\epsilon){ \rm d}\epsilon&\approx\sum_{m=0}^{\infty}\frac{\beta^{-m}}{m!}\psi^{(m)}(\mu)\int_{-\infty}^{+\infty}\frac{x^m e^{-x}}{(e^{-x}+1)^2}{ \rm d}x\\&=\sum_{m=0}^{\infty}\frac{(kT)^{2m}}{(2m)!}\psi^{(2m)}(\mu)I_{2m}\\&=\psi(\mu)+\frac{\pi^2}{6}(kT)^2\psi''(\mu)+...\\&=\int_0^\mu\varphi(\epsilon){ \rm d}\epsilon+\frac{\pi^2}{6}(kT)^2\varphi'(\mu)+...\end{align*}$$

利用这个结论，我们可以计算：

$$\bar{E}=\int_0^{+\infty}F(\epsilon)2\epsilon\rho(\epsilon){ \rm d}\epsilon\approx2\int_0^\mu\epsilon\rho(\epsilon){ \rm d}\epsilon+\frac{\pi^2}{3}(kT)^2(\epsilon\rho(\epsilon))'|_\mu$$

考虑每一项的意义.

由于金属在加热时，会有热电子释出，导致金属中的电子数量稍微增多一点点，所以我们明确在我们观测的温度下，计算出来的等效费米能 $\mu$ 要比实际的费米能 $\mu_0$ 要高一点点。

对于第一项

$$2\int_0^\mu\epsilon\rho(\epsilon){ \rm d}\epsilon=\bar{E_0}+2\int_{\mu_0}^\mu\epsilon\rho(\epsilon){ \rm d}\epsilon\approx \bar{E_0}+2\mu_0\rho(\mu_0)(\mu-\mu_0)$$

第一项显然就是在绝对零度时，系统的内能。

而第二项，我们求导：

$$(\epsilon\rho(\epsilon))'|_\mu=\rho(\mu)+\mu\rho'(\mu)\approx\rho(\mu_0)+\mu_0\rho'(\mu_0)$$

考虑到

$$N = \int_0^{+\infty}F(\epsilon)2\rho(\epsilon){ \rm d}\epsilon\approx2\int_0^\mu\rho(\epsilon){ \rm d}\epsilon+\frac{\pi^2}{3}(kT)^2\rho'(\mu)$$

与上面相似，分析每一项，这个约束给我们：

$$ N \approx N+2\rho(\mu_0)(\mu-\mu_0)+\frac{\pi^2}{3}(kT)^2\rho'(\mu_0) $$

也就是说，有费米能变化：

$$\mu-\mu_0\approx -\frac{\pi^2}{6}(kT)^2\frac{\rho'(\mu_0)}{\rho(\mu_0)}$$

带回平均能量计算式：

$$ \begin{align*}\bar{E}&\approx  \bar{E_0}+2\mu_0\rho(\mu_0)(\mu-\mu_0)+\frac{\pi^2}{3}(kT)^2(\rho(\mu_0)+\mu_0\rho'(\mu_0))\\&\approx \bar{E_0}-\frac{\pi^2}{3}(kT)^2\mu_0\rho'(\mu_0)+\frac{\pi^2}{3}(kT)^2(\rho(\mu_0)+\mu_0\rho'(\mu_0))\\&=\bar{E_0}+\frac{\pi^2}{3}(kT)^2\rho(\mu_0) \end{align*} $$

以此，可以计算电子热容：

$$C_V\approx\frac{2\pi^2}{3}\rho(\mu_0)k^2T$$

而带入9.6的讨论，我们得到：

$$\begin{align*} C_V &= \frac{2\pi^2}{3}\frac{V}{4\pi^2}\frac{(2m)^{3/2}}{\hbar^3}\sqrt{\mu_0}k^2T\\&=\frac{\pi^2}{2}N \frac{V}{3\pi^2N}\frac{(2m)^{3/2}}{\hbar^3}\sqrt{\mu_0}k^2T\\&=\frac{\pi^2}{2}N\frac{k^2T}{\mu_0}=\frac{3}{2}Nk(\frac{\pi^2kT}{3\mu_0}) \end{align*}$$

进而电子摩尔热容：

$$c_V \approx \frac{3}{2}R(\frac{\pi^2kT}{3\mu_0})$$

### 9.9 固体蒸汽压的计算

这里例演示怎么用热力学积分的办法进固体蒸汽压的计算。热力学积分，就是对一些可测的热力学函数，进行积分得到配分函数的过程。我们考虑一个实际的问题，固体蒸汽压的计算。

这里我们要求气体是理想气体，固体的体积几乎不变。

同一种物质的固气共存时，这时处于相平衡，利用第8章的讨论，我们知道有化学势相同：

$$\mu_1 = \mu_2 $$

其中1是气态，2是固态。

对于气态来说，我们可以计算：

$$ \mu_1 = \Big(\frac{\partial F}{\partial N_1}\Big)_{T,V,N_2}=-kT\ln(\zeta_1/N_1)$$

其中 $\zeta_1$ 是单个气体分子的配分函数。对于理想气体分子，我们可以计算：

$$\zeta_1 = V_1\Big(\frac{2\pi m kT}{h^2}\Big)^{3/2}$$

所以有：

$$\mu_1 = -kT\ln\Big(\frac{V_1}{N_1}\Big(\frac{2\pi m kT}{h^2}\Big)^{3/2}\Big)=-kT\ln\Big(\frac{kT}{p}\Big(\frac{2\pi m kT}{h^2}\Big)^{3/2}\Big)$$

这里用到了理想气体状态方程，将平衡时的气体气压，即蒸汽压显式地写了出来。

而对于固体，$\zeta_2$ 的求解时困难的，所以不这样解。

$$ \mu_2 = \Big(\frac{\partial F}{\partial N_2}\Big)_{T,V,N_1}=-kT\Big(\frac{\partial \ln Z}{\partial N_2}\Big)_{T,V,N_1}$$

由于配分函数中关于气体的部分与 $N_2$ 无关，所以直接可以丢掉 $Z_1$ 的部分（我们认为固气之间几乎没有相互作用），也就是说：

$$ \mu_2 =-kT\Big(\frac{\partial \ln Z_2}{\partial N_2}\Big)_{T,V,N_1}$$

而配分函数怎么求取？这里利用热力学积分的办法，注意到 $\beta = \frac{1}{kT}$ $$\bar{E_2}=-\Big(\frac{\partial \ln Z_2}{\partial \beta}\Big)_{V_2}=-\Big(\frac{\partial T}{\partial \beta}\Big)_{V_2}\Big(\frac{\partial \ln Z_2}{\partial T}\Big)_{V_2}=kT^2\Big(\frac{\partial \ln Z_2}{\partial T}\Big)_{V_2}$$

而实际上固体体积也不怎么变，我们可以直接用内能关于温度的函数积分出：

$$\ln Z_2(T)-\ln Z_2(T_0) = \int_{T_0}^T \frac{\bar{E_2}(T')}{kT'^2}{ \rm d}T'$$

而内能本身又可以用比热积分得到 $N_2 c =C_V = (\frac{\partial E}{\partial T})_V$

$$\bar{E_2}(T')-\bar{E_2}(0)=N_2\int_0^{T'}c(T''){ \rm d}T''$$

取绝对零度时的系统内能，这时候固体分子不再振动，但是由于相距较近，还有势能，物理图像上，这能量正是有理想气体状态到固态相变的潜热对应得能量，直接记：

$$\bar{E_2}(0)=-N_2 \eta$$

所以有：

$$\bar{E_2}(T')=-N_2 \eta+N_2\int_0^{T'}c(T''){ \rm d}T''$$

而 $$Z_2 = \sum_re^{-\beta\epsilon_r}$$

在温度趋于绝对零度时，所有粒子都处于一个状态（基态），也就是说这时能量就是潜热

而 $$Z_2(T_0\to0^+) = e^{-\beta(-N_2\eta)}$$

即

$$\lim_{T_0\to 0^+} \ln Z_2(T_0)=\frac{N_2\eta}{kT_0}$$

$$\begin{align*} \ln Z_2(T)&= \ln Z_2(T_0=0^+)+ \int_{T_0}^T \frac{{ \rm d}T'}{kT'^2}\Big(-N_2 \eta+N_2\int_0^{T'}c(T''){ \rm d}T''\Big)\\ &=\frac{N_2\eta}{kT_0}+\frac{N_2\eta}{k}(\frac{1}{T}-\frac{1}{T_0})+N_2\int_{0}^T \frac{{ \rm d}T'}{kT'^2}\int_0^{T'}c(T''){ \rm d}T''\\&=\frac{N_2\eta}{kT}+ N_2\int_{0}^T \frac{{ \rm d}T'}{kT'^2}\int_0^{T'}c(T''){ \rm d}T''\end{align*}$$

进而我们算出了配分函数，可以求化学势了：

$$\begin{align*} \mu_2 &=-kT\Big(\frac{\partial \ln Z_2}{\partial N_2}\Big)_{T,V,N_1}\\&=-\eta-T\int_{0}^T \frac{{ \rm d}T'}{T'^2}\int_0^{T'}c(T''){ \rm d}T''\end{align*}$$

因此由 $\mu_1=\mu_2$ 可以得到：

$$-kT\ln\Big(\frac{kT}{p}\Big(\frac{2\pi m kT}{h^2}\Big)^{3/2}\Big)=-\eta-T\int_{0}^T \frac{{ \rm d}T'}{T'^2}\int_0^{T'}c(T''){ \rm d}T''$$

解得：

$$p = (kT)^{5/2}\frac{(2\pi m)^{3/2}}{h^3}\exp\Big(-\frac{\eta}{kT}-\frac{1}{k}\int_{0}^T \frac{{ \rm d}T'}{T'^2}\int_0^{T'}c(T''){ \rm d}T''\Big)$$

潜热和热容在实验上是好测得的。实际上我们也有很多有效的固体热容理论，比如Einstein模型，以及我们下一章马上要讨论的若干模型和近似。

## 第10章 近似方法

本章讨论有内部相互作用的体系，什么时候可以处理，以及怎么处理。

### 10.1 有相互作用的困难

为什么有相互作用会变得困难，考虑有相互作用，那么就会有相互作用能 $U_{ij}$ ，我们考虑简单的情况，就是相互作用只与两个粒子的相对位形有关，我们简单看配分函数的计算：

$$\begin{align*}Z(\beta)&=\int\frac{{ \rm d}^{3N} q{ \rm d}^{3N} p}{N!h^{3N}}e^{-\beta(\sum_i p^2_i/2m+\sum_{ij}U_{ij}(q_i,q_j))}\\&=\frac{1}{N!h^{3N}}(\int{ \rm d}pe^{-\beta p^2/2m})^{3N}\int{ \rm d}^{3N} qe^{-\beta\sum_{ij}U_{ij}(q_i,q_j)}\\&=\frac{1}{N!h^{3N}}(\frac{2\pi m}{\beta})^{3N/2}\int{ \rm d}^{3N} qe^{-\beta\sum_{ij}U_{ij}(q_i,q_j)}\end{align*}$$

这留下的这个积分是困难的。第一，项有很多，第二，指数上扛一个不太好的形式的函数积分因起来十分痛苦，第三，势能函数本身就很难确定。这几重困难让我们难以处理，令位形配分函数：

$$Z_{U}(\beta)=\int e^{-\beta U(q)}{ \rm d}^{3N}q $$

这是困难的一个来源。

#### 可能处理的情况

这个积分固然困难，但是有时我们也能近似处理，可以完成这个计算。

第一种情况，就是低温情况。低温的时候，微观粒子的热运动很弱，这时候它们不会到处乱跑。另外，在能级的观点上，粒子主要占据低能态，不会随便跑到高能级上去，那这时候我们需要求和的状态其实是比较少的，我们也许可能可以解决这个问题。

对于强项互作用的低温系统，粒子会呈现一些集体行为（毕竟和附近的粒子关联强）。这时后一个微弱的扰动可以形成一种波的模式传播出去，将其量子化，这种传播模式也就有粒子性，被我们称为准粒子。比如在低温铁磁系统中的自旋波——磁振子。

第二种情况，就是极高温情况，这时候粒子无序，相互作用显得不重要，我们可以略去，这就近似于无相互作用的情况。

我们接下来将讨论几个实际的模型，并给出计算。这些本质是一些模型假设和近似方法。

### 10.2 固体比热

对于固体来说，其微观粒子相互作用比较强。我们显然不能像之前那样用理想气体模型的结论分析。物理图像上来说，固体的内能就是以晶格振动的能量形式储存的，但不管怎么样，微观粒子始终是在一个平衡位置附近振动，而不可能乱跑，不然就散架了，就不是固体了。所以我们可以认为「固体」一词，就在物理图像上意味着「低温」。

这时候，势能函数在平衡位置附近做泰勒展开，由于平衡位置一阶导是0，于是保留到位移有二次方关系。即这时微观粒子进行简谐振动。

#### 经典近似

我们先考虑一般温度下，这时温度不太低，晶格振动可以处理为一种经典的谐振子，这时有能量(每个维度上)：

$$H = \frac{p^2}{2m}+\frac{1}{2}m\omega^2q^2$$

利用能均分定理，每个维度贡献能量：$\bar{\varepsilon}=2\times\frac{1}{2}kT=kT$

那么总内能有：

$$\bar{E} = 3NkT$$

进而有热容：

$$C_V=\Big(\frac{\partial \bar{E}}{\partial T}\Big)_V=3Nk$$

也就是说固体热容在温度较高时是一个定定值。但这显然和 $$C_V=T\Big(\frac{\partial S}{\partial T}\Big)_V$$

相抵触，这个式子说明了在低温情况下热容总是趋于0，不可能是常数，这个式子只在温度比较高的情况下使用。

#### 量子谐振子统计

自然想到，在低温的时候不适用经典近似，所以自然想到要用量子力学讨论问题：

$$\hat{H} = \frac{\hat{p}^2}{2m}+\frac{1}{2}m\omega^2\hat{q}^2$$

这个哈密顿量下的定态薛定谔方程解出来的能级是：

$$\varepsilon_n = (n+\frac{1}{2})\hbar\omega$$

我们可以计算一个粒子的配分函数：

$$\zeta(\beta) = \sum_{n=0}^\infty e^{-\beta\varepsilon_n}=\sum_{n=0}^\infty e^{-\beta(n+\frac{1}{2})\hbar\omega}=\frac{e^{-\beta\hbar\omega/2}}{1-e^{-\beta\hbar\omega}}$$

所以：

$$\ln \zeta(\beta)=-\frac{1}{2}\beta\hbar\omega-\ln(1-e^{-\beta\hbar\omega})$$

可以计算一个粒子在一个维度上的平均动能：

$$\bar{\varepsilon}=-\frac{\partial\ln \zeta(\beta)}{\partial \beta}=\frac{1}{2}\hbar\omega+\frac{\hbar\omega}{e^{\beta\hbar\omega}-1}$$

在温度较高，即 $\beta\to 0^+$ 时，有：

$$\bar{\varepsilon}\approx\frac{1}{2}\hbar\omega+\frac{\hbar\omega}{\beta\hbar\omega}=kT+\hbar\omega\approx kT\$$

可见可以退化到经典情况的讨论。

#### Einstein 模型

考虑到每个原子的振动可能不一样，因为约束的势能可能有一些不同，所以实际上各个原子的振动参数 $\omega$ 实际上是不同的。但是仔细考虑，在固体中各个原子会因为所处的晶格位置不同而在约束上有巨大的差别吗？实际上应该差别不大，所以这里我们就做一个大胆的假设，也是Einstein当年的假设——所有原子的振动基频 $\omega$ 相同

那么我们就可以写出系统的内能：

$$\bar{E}=3N\hbar\omega\Big(\frac{1}{2}+\frac{1}{e^{\beta\hbar\omega}-1}\Big)$$

这时我们只需要求导就可以算出体系的内能了：

$$\begin{align*}C_V&=\Big(\frac{\partial \bar{E}}{\partial T}\Big)_V=\Big(\frac{\partial \beta}{\partial T}\Big)_V\Big(\frac{\partial \bar{E}}{\partial \beta}\Big)_V\\&=-\frac{1}{kT^2}3N\hbar\omega\frac{-\hbar\omega e^{\beta\hbar\omega}}{(e^{\beta\hbar\omega}-1)^2}\\&=\frac{3N\hbar^2\omega^2}{kT^2}\frac{ e^{\hbar\omega/kT}}{(e^{\hbar\omega/kT}-1)^2}\end{align*}$$

取Einstein温度：$\Theta_E:=\hbar\omega/k$ 是一个由系统相互作用决定的参量，具体温度量纲，有：

$$C_V=3Nk\Big(\frac{\Theta_E}{T}\Big)^2\frac{e^{\Theta_E/T}}{(e^{\Theta_E/T}-1)^2}$$

在温度 $T\to 0^+$ 的时候，相当于 $$\lim_{x\to +\infty}\frac{x^2e^x}{(e^x-1)^2}=\lim_{x\to +\infty}\frac{x^2}{e^x-1}\cdot\lim_{x\to +\infty}\frac{1}{1-e^{-x}}=0\times 1 =0 $$

我们得到了符合热容基本特征的表达式，爱因斯坦模型确实也在实验上符合得不错。其进行的假设也算可以接受。

而在 $T>>\Theta_E$，即 $\Theta_E/T\to 0^+$ 时，有：

$$C_V\approx3Nk\Big(\frac{\Theta_E}{T}\Big)^2\frac{1}{({\Theta_E/T})^2}=3Nk$$

在与经典情况也是相协调的。

这个模型不错，但是还是有一点点缺陷，那就是该模型下热容虽然在低温时趋近于0，但是趋近的方式和实验对不太上，这里是以 $\Big(\frac{\Theta_E}{T}\Big)^2\frac{e^{\Theta_E/T}}{(e^{\Theta_E/T}-1)^2}$ 的形式趋近0，但实验上得到的是以 $T^3$ 的方式趋于 0. 稍微有点对不上。

#### 晶格振动的精确计算

Einstein模型本质上是做了一次近似，认为所有维度上的振动基频都一样，这很合理。因为应该说在庞大的固体体系中，这些维度应该没有什么太大的区别。但是既然结果与实验之间有一些问题，那就说明这里的近似还是可以改进的。

对于 $3N$ 个维度，我们认为其基频不一样，那么这时我们可以考虑系统的状态。相当于有 $3N$ 种能级足，而每种能级族种总是填了且只填了一个粒子。

系统本身的结构有一个隐含的常数内势能 $V_0$，可以写出各个维度在取两量子数 $n_1,n_2,...$ 时，有系统能量：

$$E = V_0+\sum_r(n_r+\frac{1}{2})\hbar\omega_r\equiv-N\eta+\sum_rn_r\hbar\omega_r$$

这里提出去的项 $V_0+\sum_r\frac{1}{2}\hbar\omega_r$ 其实就是系统基态能量，物理图像上就是构建这个系统需要释放的能量（从毫无关联，即理想气体的状态凝集成这个固体），所以我们物理意义上就看得出来这一项时潜热，记为 $-N\eta$

那么我们可以计算配分函数：

$$\begin{align*}Z(\beta)&=\sum_{n_1,n_2,...}e^{-\beta(-N\eta+\sum_{r}n_r\hbar\omega_r)}\\&=e^{\beta N\eta}\Big(\sum_{n_1=0}^\infty e^{-\beta n_1\hbar \omega_1}\Big)\Big(\sum_{n_2=0}^\infty e^{-\beta n_2\hbar \omega_2}\Big)...\\&=e^{\beta N\eta}\Big(\frac{1}{1-e^{-\beta\hbar\omega_1}}\Big)\Big(\frac{1}{1-e^{-\beta\hbar\omega_2}}\Big)...\end{align*}$$

于是

$$\ln Z(\beta)=\beta N\eta-\sum_{r=1}^{3N}\ln (1-e^{-\beta\hbar\omega_r})$$

我们可以根据实际基频关于频率大小的分布情况，定义自由度分布密度 $\sigma(\omega)$，有 $\sigma(\omega){ \rm d}\omega$ 表示基频在 $\omega\sim\omega+{ \rm d}\omega$ 范围内的自由度个数，于是上式改写为积分形式：

$$\ln Z(\beta)=\beta N\eta-\int_0^{+\infty}\ln (1-e^{-\beta\hbar\omega})\sigma(\omega){ \rm d}\omega$$

那么就可以计算系统的内能：

$$\begin{align*}\bar{E}=-\frac{\partial \ln Z}{\partial \beta}=-N\eta-\int_0^{+\infty}\frac{\hbar\omega}{1-e^{-\beta\hbar\omega}}\sigma(\omega){ \rm d}\omega\end{align*}$$

再进一步计算比热：

$$\begin{align*}C_V&=\Big(\frac{\partial \bar{E}}{\partial T}\Big)_V=\Big(\frac{\partial \beta}{\partial T}\Big)_V\Big(\frac{\partial \bar{E}}{\partial \beta}\Big)_V\\&=-\frac{1}{kT^2}\Big(-\int_0^{+\infty}\frac{-\hbar\omega(-\hbar\omega e^{-\beta\hbar\omega})}{(1-e^{-\beta\hbar\omega})^2}\sigma(\omega){ \rm d}\omega\Big)\\&=k\int_0^{+\infty}\frac{ e^{-\beta\hbar\omega}}{(1-e^{-\beta\hbar\omega})^2}(\beta\hbar\omega)^2\sigma(\omega){ \rm d}\omega\end{align*}$$

所以精确的 $\sigma(\omega)$ 给出精确的比热表达式。

显然 $\sigma(\omega)$ 有性质：

$$\int_0^{+\infty}\sigma(\omega){ \rm d}\omega=3N$$

而取高温情况，即 $\beta\to 0^+$，有：

$$\begin{align*}C_V&= k\int_0^{+\infty}\frac{ e^{-\beta\hbar\omega}}{(1-e^{-\beta\hbar\omega})^2}(\beta\hbar\omega)^2\sigma(\omega){ \rm d}\omega\\&\approx k\int_0^{+\infty}\frac{1}{(\beta\hbar\omega)^2}(\beta\hbar\omega)^2\sigma(\omega){ \rm d}\omega\\&=k\int_0^{+\infty}\sigma(\omega){ \rm d}\omega=3Nk\end{align*}$$

我们这个精确计算在高温情况下，也总是给出经典近似。

Einstein模型即取 $\sigma(\omega')=3N\delta(\omega'-\omega)$，即认为所有自由度的振动基频都是一样的，所以都分布在同一个频率上，形成一个delta函数。结果积分退化给出 Einstein模型的结果：

$$C_V = 3Nk(\beta\hbar\omega)^2\frac{ e^{-\beta\hbar\omega}}{(1-e^{-\beta\hbar\omega})^2}=3Nk\Big(\frac{\Theta_E}{T}\Big)^2\frac{e^{\Theta_E/T}}{(e^{\Theta_E/T}-1)^2}$$

#### Debye近似

那实际上，$\sigma(\omega)$ 到底是什么样的呢？这实在是有点为难人了，这实验上也不好测，只能猜了。（实际上实验上有一个结果，但不可能解析的写出来）

我们现在就是要凑一个 $\sigma(\omega)$，使积分出来的结果作为热容在 $T\to 0^+$ 时，以 $T^3$ 的形式趋于0.

Debye选择这样考虑晶格振动在某一自由度上的基频，显然，振动还有另外一个物理含义，那就是固体中的声音。我们取固体中的等效声速为 $c_s$ ，那么频率和波矢之间有：

$$\omega = c_s \kappa$$

而声波本身应该满足波动方程，相关讨论也便是9.6进行过的，我们相当于把声子气体当作理想气体处理，那么就可以套用相关的能级密度理论：

$$\rho(\kappa)=4\pi\kappa^2\rho(\vec{\kappa})=\frac{V}{2\pi^2}\kappa^2$$

所以关于频率的能级分布情况：

$$\rho(\omega){ \rm d}\omega=\rho({\kappa}){ \rm d}\kappa=\frac{V}{2\pi^2}\kappa^2{ \rm d}\kappa$$

有：

$$\rho(\omega)=\frac{V}{2\pi^2}\frac{\omega^2}{c_s^2}\frac{1}{c_s}=\frac{V\omega^2}{2\pi^2c_s^3}$$

即对于声子来说，其频率处于 $\omega\sim\omega+{ \rm d}\omega$ 范围内的能级的个数是 $\rho(\omega){ \rm d}\omega$ 个

而对于一个声子的振动模式，我们总是可以将其投影到3个方向上，就是一个振动模式对应了3个自由度上的同频率的振动模式，也就是说得到了3个不同的振动模式，有：

$$\sigma(\omega)=3\rho(\omega)=\frac{3V\omega^2}{2\pi^2c_s^3}$$

或者说，必须要在自由度上有这么多基频的原子，这个方式的声音才可能存在。这是比较物理图像的看法，其实有乏严谨性，但是还算勉强可以接受。

再次考虑声音这个图像在什么时候比较成立。一般地，声音是固体中的原子的集体行为，波长是远远大于原子间距的。也就是说，声音这个图像只适用于频率比较低的情况。当振动频率太小，以至于其波长可与原子间距离相比拟时，就不是我们物理图像上熟悉的声音了。

于是，这里再来一次近似，其实很武断。即高基频模式不存在。

所以我们就这样写：

$$\sigma(\omega)\begin{cases}\frac{3V\omega^2}{2\pi^2c_s^3}\quad\omega<\omega_D\\0\qquad \omega>\omega_D\end{cases}$$

其中 $\omega_D$ 为Debye频率，有：

$$\int_0^{\omega_D}\frac{3V\omega^2}{2\pi^2c_s^3}{ \rm d}\omega=3N$$

这样，我们就构造出了一种频率的自由度密度。可以解得：

$$\omega_D=c_s\Big(6\pi^2\frac{N}{V}\Big)^{1/3}$$

上述构造的 $\sigma(\omega)$ 就称为Debye近似。

那么我们就可以计算Debye近似下热容：

$$\begin{align*}C_V&= k\int_0^{+\infty}\frac{ e^{-\beta\hbar\omega}}{(1-e^{-\beta\hbar\omega})^2}(\beta\hbar\omega)^2\sigma(\omega){ \rm d}\omega\\&=k\int_0^{\omega_D}\frac{ e^{-\beta\hbar\omega}}{(1-e^{-\beta\hbar\omega})^2}(\beta\hbar\omega)^2\frac{3V\omega^2}{2\pi^2c_s^3}{ \rm d}\omega\\&=k\frac{3V}{2\pi^2(c_s\beta\hbar)^3}\int_0^{\beta\hbar\omega_D}\frac{x^4e^x}{(e^x-1)^2}{ \rm d}x\\&=k\frac{3V}{2\pi^2c_s^3}\frac{\omega_D^3}{y^3}\int_0^{y}\frac{x^4e^x}{(e^x-1)^2}{ \rm d}x\\&=3Nk\cdot\frac{3}{y^3}\int_0^{y}\frac{x^4e^x}{(e^x-1)^2}{ \rm d}x\end{align*}$$

其中运用了还原 $x=\beta\hbar\omega$ ，以及令了变量：$y=\beta\hbar\omega_D$

一样的，我们可以取Debye温度，只有系统本身决定，有温度量纲：$\Theta_D=\hbar\omega_D/k$

则有：$y=\Theta_D/T$

令Debye函数：

$$D(y)=\frac{3}{y^3}\int_0^{y}\frac{x^4e^x}{(e^x-1)^2}{ \rm d}x$$

那么我们就可以直接写出Debye近似下的热容精确表达式：

$$C_V=3NkD\Big(\frac{\Theta_D}{T}\Big)$$

我们分析这个函数的行为，就可以得到一些结果，首先考虑高温情况，即 $y\to 0^+$

$$\begin{align*}D(y=0^+)&=\lim_{y\to 0^+}\frac{3}{y^3}\int_0^{y}\frac{x^4e^x}{(e^x-1)^2}{ \rm d}x\\&=\lim_{y\to 0^+}\frac{1}{y^2}\frac{y^4e^y}{(e^y-1)^2}\\&=\lim_{y\to 0^+}\Big(\frac{y}{e^y-1}\Big)^2\lim_{y\to 0^+}e^y\\&=1\times1 =1\end{align*}$$

确实，这在高温下必然回到经典情况，如我们之前的讨论：$C_V=3Nk$

我们这时候考虑低温情况，也就是 $y\to +\infty$

$$\begin{align*}D(y=+\infty)&=\frac{3}{y^3}\int_0^{+\infty}\frac{x^4e^x}{(e^x-1)^2}{ \rm d}x\\&=-\frac{3}{y^3}\int_0^{+\infty}x^4{ \rm d}\Big(\frac{1}{e^x-1}\Big)\\&=\frac{3}{y^3}\int_0^{+\infty}\frac{4x^3}{e^x-1}{ \rm d}x\\&=\frac{3}{y^3}\cdot4I_-(3)\\&=\frac{12}{y^3}\cdot3!\zeta(4)\\&=\frac{4\pi^2}{5\Theta_D^3}T^3\end{align*}$$

这个积分在数学附录5中有过讨论。

也就是说，在低温情况下，$T\to 0^+$，有：

$$C_V = \frac{12\pi^2}{5\Theta_D^3}NkT^3$$

这时确实热容以 $T^3$ 的速度趋于0，这与实验更加符合。

- 评论：这个近似其实就是一种调参了，只要你把 $\omega_D$ 调得够好就可以符合实验，等价地就是调有效声速 $c_s$，但他把形式凑出来了，这样做实验的人就可以调参了。这个模型讲实话没有Einstein模型的假设来的优美，但是确实解决了问题，不过我会认为这只是一种解决的方式而已，虽然很好用就是了。

### 10.3 平均场近似

平均场近似是这样的，它只需要将相互作用的来源近似为一个整体的场的效果，而具体的粒子之间要考虑的东西就很多了。（注：鸣潮公式秒了）

什么意思？就是说在有相互作用的系统中，为什么难处理？原因就在于我们之前是这样考虑相互作用的效应的—— $U_{ij}(q_i,q_j)$ ，即真的去细致的考虑某两个粒子的相互作用，并且具体地把它们写出来。但是我们实际去考虑一个系统，具体是哪个粒子施加的作用真的很重要吗？貌似也不然，我们其实可以直接把一个粒子受到的相互作用当作由一个场施加的，这个场是由这个系统的状态构建的。

我们进入到具体的情景里面去吧。

#### 铁磁系统——Ising Model

铁磁系统的物理图像是，构成铁磁体的微观粒子是大量有自旋的粒子（这是会被磁化的物体的基本物理图像），但是这些磁矩之间有较强的相互作用，不可忽略。

原子磁矩和自旋之间的关系可以直接表达为：

$$\vec{\mu} = g\mu_B\vec{S}$$

其中 $g$ 就是朗道g因子，$\mu_B$ 是波尔磁矩。

不考虑磁矩相互作用时，系统受均匀外场 $\vec{H_0}$ 的影响的哈密顿量就可以写为：

$$\mathcal{H}_0=-\sum_{i}\vec{H_0}\cdot\vec{\mu_i}=-g\mu_B\sum_i\vec{H_0}\cdot\vec{S_i}=-g\mu_B\sum_iH_0S_{iz}$$

这里就直接把外场方向设为 $z$ 方向，而相当于在这个方向进行了一次自旋观测。

考虑自旋的相互作用，有：

$$\mathcal{H}_{jk}=-2J_{jk}\vec{S_j}\cdot\vec{S_k}$$

实际上，这有很多项，但是我们知道磁矩间的相互作用能随距离的衰减是以 $1/r^{2}$ 速度衰减的，我们完全可以只考虑近邻的相互作用，即只考虑两个相邻的相互作用，这时取 $J_{jk}=J$ ，其它的不相邻的相互作用都直接取 $J_{jk}=0$，所以：

$$\mathcal{H}_{jk}=-2J\vec{S_j}\cdot\vec{S_k}$$

直接求总的内相互作用能（哈密顿量）$N$ 为原子总数，$n$为一个原子最近邻的原子个数（即与之发生相互作用的原子个数，由具体晶体结构确定），同时在外磁场的观测下，自旋方向也就确定了（注意，j指代哪些原子是由k决定的）：

$$\mathcal{H}_{int}=\frac{1}{2}\sum_{k=1}^N\sum_{j=1}^n\mathcal{H}_{jk}=-J\sum_{k=1}^N\sum_{j=1}^n\vec{S_{j(k)}}\cdot\vec{S_k}=-J\sum_{k=1}^NS_{kz}\sum_{j=1}^nS_{jz}$$

这里的 $1/2$ 是因为每个相互作用被求和了两次。我们有系统的哈密顿量：

$$\begin{align*}\mathcal{H}=\mathcal{H_0}+\mathcal{H}_{int}&=-g\mu_B\sum_{k=1}^{N}H_0S_{kz}-J\sum_{k=1}^NS_{kz}\sum_{j=1}^nS_{jz}\\&=-\sum_{k=1}^N\Big(g\mu_BH_0+J\sum_{j=1}^nS_{j(k)z}\Big)S_{kz}\end{align*}$$

这个模型可以被我们抽象出来，也就是Ising Model，我们之前在第1章就讨论过了。Ising Model可以很好地描述铁磁系统。

我们只需要对所有可能状态求和得到配分函数，那这个统计系统就完全可解了：

$$Z(\beta)=\sum_{r}e^{-\beta\mathcal{H}}$$

这个配分函数在1维晶格上利用紧致化条件可以很简单地得到结果，是解析的。在2维晶格上（正方晶格）的解析解由Onsager给出，已经很难看懂了。3维的解析解至今没有被公认地找到，这疑似是拓扑结构上的困难。

接下来，我们利用平均场近似，这种近似可以给出一些近似的结果。有人证明了对于4维及以上维度的Ising Model利用平均场近似结果是精确的（这我听说的）,可见3维解析解已经是Ising Model的皇冠上的明珠了。

#### Weiss 分子场近似

我们知道这个模型最终的结果是磁化，即铁磁体因为外磁场的存在而自发产生了一个磁场 $H_m$ ，这个磁化结果就是一个平均场，我们可以反过来认为铁磁体的微观粒子间的相互作用就是自发磁化场在这些原子上的作用。物理上，我们就是把磁化的效果平均到了每个原子上，或者说将某个原子受到的相互作用的真正贡献者给淡化掉，而认为是一个整体的场的作用。

即取：

$$2J\Big\langle \sum_{j=1}^n  S_{j(k)z} \Big\rangle=g\mu_BH_m \quad \forall k$$

将平均的相互作用直接视为一个整体的场，这个场被称为「分子场」，这个近似也叫做Weiss分子场近似。

那么对于某个原子，其自身的哈密顿量也就清楚了：

$$\mathcal{H}_k=-g\mu_B(H_0+H_m)S_{kz}$$

注意，这里 $H_m$ 还是一个未定的常量，这是要最后计算出来的，物理图像上应与温度有关。我们可以研究这个系统的平均磁矩应该是什么样的，反过来代回定义式可以解出分子场。

对于单个磁矩，其自旋在某一方向上的投影可能是：$-J,-J+1,...,J$ ，共 $2J+1$ 个可能，这里 $J$ 是磁量子数，这个结论在原子物理里学过，这学期学了群论的话就更不会陌生。

那么单个原子状态的配分函数可以写为：

$$\begin{align*}Z_a(\beta)&=\sum_{m=-J}^J e^{-\beta g\mu_B(H_0+H_m)m}\equiv\sum_{m=-J}^Je^{-m\eta}\\&=e^{J\eta}\frac{1-e^{-(2J+1)\eta}}{1-e^{-\eta}}\\&=\frac{e^{(J+\frac{1}{2})\eta}-e^{-(J+\frac{1}{2})\eta}}{e^{\frac{1}{2}\eta}-e^{-\frac{1}{2}\eta}}\\&=\frac{\sinh(J+\frac{1}{2})\eta}{\sinh\frac{1}{2}\eta}\end{align*}$$

这里 $\eta=\beta g\mu_B(H_0+H_m)$ 是一个待定的关于 $\beta$ 的函数。

而我们计算平均磁矩：

$$\bar{\mu_a}=\frac{\sum_r(-\frac{\partial E_a}{\partial H})e^{-\beta E_a}}{\sum_re^{-\beta E_a}}=\frac{1}{\beta}\frac{\partial \ln Z_a}{\partial H}$$

而注意到：$\eta=\beta g\mu_BH$，所以：

$$\begin{align*}\bar{\mu_a}&=\frac{1}{\beta}\frac{\partial \ln Z_a}{\partial H}=\frac{1}{\beta}\frac{\partial \ln Z_a}{\partial \eta}\frac{\partial \eta}{\partial H}=g\mu_B\frac{\partial \ln Z}{\partial \eta}\\&=g\mu_B\frac{\partial}{\partial \eta}(\ln \sinh(J+\frac{1}{2})\eta-\ln\sinh\frac{1}{2}\eta)\\&=g\mu_B\Big((J+\frac{1}{2})\coth(J+\frac{1}{2})\eta-\frac{1}{2}\coth\frac{1}{2}\eta\Big)\end{align*}$$

定义布里渊函数：

$$B_J(x):=\frac{1}{J}\Big((J+\frac{1}{2})\coth(J+\frac{1}{2})x-\frac{1}{2}\coth\frac{1}{2}x\Big)$$

所以就有：

$$\bar{\mu_a}=g\mu_BJB_J(\eta)=\mu_{\max}B_J(\eta)$$

可以分析布里渊函数的渐近行为，在 $x\to 0^+$

$$\begin{align*}\coth x&=\frac{e^x+e^{-x}}{e^{x}-e^{-x}}\\&\approx\frac{2+x^2+...}{2x+\frac{1}{3}x^3+...}\\&=\frac{1}{x}\frac{1+\frac{1}{2}x^2+...}{1+\frac{1}{6}x^2+...}\frac{}{}\\&\approx\frac{1}{x}(1+\frac{1}{2}x^2)(1-\frac{1}{6}x^2)\\&\approx\frac{1}{x}+\frac{x}{3}\end{align*}$$

于是：

$$\begin{align*} B_J(x=0^+)&=\frac{1}{J}\Big((J+\frac{1}{2})\coth(J+\frac{1}{2})x-\frac{1}{2}\coth\frac{1}{2}x\Big)\\&\approx\frac{1}{J}\Big(\frac{1}{x}+\frac{(J+\frac{1}{2})^2x}{3}-\frac{1}{x}-\frac{x}{12}\Big)\\&=\frac{1}{J}\Big(\frac{(J+\frac{1}{2})^2}{3}-\frac{1}{12}\Big)x\\&=\frac{J+1}{3}x\to 0 \end{align*}$$

也就是说布里渊函数在 $x\to 0$  时也趋于 0，此处斜率为 $\frac{J+1}{3}$

在 $x\to +\infty$ 显然： $\coth x\to 1$ ，则 $B_J(x\to+\infty)=1$


可以得到平均自旋为：（注意，这里为了避免与耦合参量 $J$ 记号重合，将磁量子数直接写为自旋大小的记号 $S$ ）

$$\bar{S}=SB_{S}(\eta)$$

带回分子场最开始的定义：

$$g\mu_BH_m=2J\Big\langle \sum_{j=1}^n  S_{j(k)z} \Big\rangle=2nJSB_S(\eta)$$

以及约束：

$$\eta = \beta g\mu_B(H_0+H_m)$$

消掉分子场 $H_m$，得到：

$$B_S(\eta)=\frac{1}{2nJS}(\frac{\eta}{\beta}-g\mu_BH_0)=\frac{kT}{2nJS}\Big(\eta-\frac{g\mu_BH_0}{kT}\Big)$$

我们研究铁磁体自发磁化的现象，取 $H_0=0$ 那么有：

$$B_S(\eta)=\frac{kT}{2nJS}\eta$$

接出 $\eta$ 就相当于算出了分子场 $H_m$

图解法：画直线 $y=\frac{kT}{2nJS}(\eta-\frac{g\mu_BH_0}{kT})$ 和 $y=B_S(\eta)$ 考察其交点位置。

而在知道分子场的情况下，即解出 $\eta$ 后，磁化强度也就自然得到了：

$$\bar{M}=Ng\mu_B\bar{S}=Ng\mu_BSB_S(\eta)$$

在没有外磁场时，有一个平凡解 $\eta =0$ ，有 $B_S(\eta) = 0$ 这时系统不会发生自发磁化。

那要有非平凡的解，其实就是要求在$x=0$ 处，$B_S(x)$ 的斜率要大于 $kT/nJS$

即有要求：

$$\frac{S+1}{3}>\frac{kT}{2nJS}$$

影响斜率因素的主要时温度，我们知道铁磁系统在高温时不会自发磁化，但是在低温时会，中间有一个转变温度，这个临界温度在分子场近似下，就是：

$$T_c = \frac{2nJS(S+1)}{3k}$$

在 $T<T_c$ 时，系统发生自发磁化。

$T\to 0^+$ 直线几乎是平的，有 $\eta \to +\infty$ 则 $B_S(\eta)\to 1$ 这时磁化率最大 $\bar{M}\to Ng\mu_BS$ 物理图像上看自旋朝向都一致。

$T\to T_c$，$\bar{M}\to 0$ 自发磁化现象消失


而在 $T>T_c$ 时系统不会自发磁化。这时研究其加外磁场下的磁化效果：

考虑到：$B_S(\eta)=\frac{kT}{2nJS}\Big(\eta-\frac{g\mu_BH_0}{kT}\Big)$ 的解

注意到：$\eta = \beta g\mu_B H$ ，在高温弱磁场时 $\eta\to 0$，那么有可以线性近似：$B_S(\eta)\approx\frac{S+1}{3}\eta$

联立有：

$$\frac{S+1}{3}\eta=\frac{kT}{2nJS}\Big(\eta-\frac{g\mu_BH_0}{kT}\Big)\Rightarrow T_c\eta=T\eta-\frac{g\mu_BH_0}{k}$$

即有：$$\eta \approx\frac{g\mu_BH_0}{k(T-T_c)}$$

那么磁化强度有：

$$\bar{M}=Ng\mu_BSB_S(\eta)\approx Ng\mu_BS\frac{S+1}{3}\eta=\frac{Ng^2\mu_B^2S(S+1)H_0}{3k(T-T_c)}$$

有磁化率：

$$\chi=\frac{\bar{M}}{H_0}=\frac{Ng^2\mu_B^2S(S+1)}{3k(T-T_c)}\propto\frac{1}{T-T_c}$$

这正是实验上总结出来的居里定律。

#### 实际气体平均场近似—— van de Waals 气体模型

我们之前考虑的理想气体就是忽略了分子间相互作用的情况。实际的气体分子之间是有相互作用的。其相互作用的形式有很多种模型，这里我们选用有引力的钢球模型。即在分子实体范围内，势能无穷大，而分子实之外的部分，有一个微弱的吸引势（ $-r^{-s}$ 形式的衰减）

$$u=\begin{cases}-u_0\Big(\frac{R_0}{r}^s\Big)\quad r>R_0\\+\infty \qquad\quad r<R_0\end{cases}$$

我们在本章开头，就计算了：

$$\begin{align*}Z(\beta)&=\frac{1}{N!h^{3N}}(\frac{2\pi m}{\beta})^{3N/2}Z_U(\beta)\end{align*}$$

位形配分函数的计算在这种情况下依然困难：

$$Z_{U}(\beta)=\int e^{-\beta U(q)}{ \rm d}^{3N}q $$

我们这里采取平均场的观点，不再一个个地去看粒子间的相互作用，而是想象，这个系统中的一个气体分子总和地受到的平均相互作用会因为处在不同位置而区别很大吗？实际上也不太会，气体是均匀的。那我们直接取一个内部相互作用场为平均场 $\bar{U}(q)$

这个场有一个特点，毕竟我们采用钢球模型，那么还是有一部分区域，体积大小为所有分子实体本身占据的体积，势能是无穷大。而在其余部分，是一个常数 $\bar{U}_a$

$$\begin{align*}Z_{U}(\beta)&=\int e^{-\beta U(q)}{ \rm d}^{3N}q=\Big(\int e^{-\bar{U}(q)}{ \rm d}^3 q\Big)^{N}\\&=\Big(e^{-\bar{U}_a}\int_{V-V_a} { \rm d}^3 q\Big)^{N}=\Big(e^{-\bar{U}_a}(V-V_a)\Big)^{N}\end{align*}$$

这样，我们就计算出了平均场近似下的配分函数：

$$Z(\beta)\approx\frac{1}{N!}\Big[\Big(\frac{2\pi m}{\beta h^2}\Big)^{3/2}(V-V_a)e^{-\beta\bar{U}_a}\Big]^N$$

我们考虑 $\bar{U}_a$ 和 $V_a$ 具体和什么有关

总的平均势能，有共 $C_N^2=\frac{1}{2}N(N-1)$ 对相互作用，我们取两个气体分子的平均相互作用能为 $\bar{u}$，那么总的相互作用能有两种表述，相同：

$$N\bar{U}_a=\frac{1}{2}N(N-1)\bar{u}\approx\frac{1}{2}N^2\bar{u}$$

也就是说，有：

$$\bar{U}_a=\frac{1}{2}N\bar{u}$$

那么我们计算两个分子之间的平均相互作用（$s>3$）：

$$\begin{align*}\bar{u}&=-\frac{1}{V}\int_{R_0}^R u_0(\frac{R_0}{r})^s4\pi r^2{ \rm d}r\\&\approx-\frac{1}{V}\int_{R_0}^{+\infty} u_0(\frac{R_0}{r})^s4\pi r^2{ \rm d}r\\&=-\frac{4\pi u_0}{V}\frac{R_0^3}{s-3}\end{align*}$$

那么有平均势能：

$$\bar{U}_a=\frac{1}{2}N\bar{u}=-\frac{N}{V}\frac{2\pi}{3}R_0^3\Big(\frac{3}{s-3}\Big)u_0\equiv-\frac{N}{V}a$$

而体积 $V_a$ 可以这样计算：有 $\frac{1}{2}N^2$ 对分子，一对贡献 $\frac{4}{3}\pi R_0^2$ 的禁止区域，这样计算相当于计算了 $N$ 个粒子的禁止区域，有：

$$NV_a=\frac{2}{3}\pi R_0^3N^2$$

则取：$$V_a=\frac{2}{3}\pi R_0^3N\equiv bN$$

配分函数写为：

$$Z(\beta)=\frac{1}{N!}\Big[\Big(\frac{2\pi m}{\beta h^2}\Big)^{3/2}(V-bN)e^{\beta aN/V}\Big]^N$$

有：

$$\ln Z(\beta)=\frac{3}{2}N\ln(\frac{2\pi m}{\beta h^2})+\beta a\frac{N^2}{V}+N\ln(V-bN)-\ln N!$$

那么，可以计算出状态方程：

$$\begin{align*}\bar{p}&=\frac{1}{\beta}\frac{\partial \ln Z}{\partial V}\\&=\frac{1}{\beta}\Big(-\beta a\frac{N^2}{V^2}+\frac{N}{V-bN}\Big)\\&=-a\frac{N^2}{V^2}+\frac{NkT}{V-bN}\end{align*}$$

于是我们推导出了著名的 van de Waals 状态方程：

$$\Big(p+a(\frac{N}{V})^2\Big)(V-bN)=NkT$$

可见van de Waals 气体本身其实就是对气体模型进行了一次平均场近似。

看完这两个实例以后，我们确实可以认可平均场近似了。但毕竟是近似，肯定还是会有些问题的。其最大的特点是，磨灭了个体在相互作用中的贡献。在一些体系中，有一些特别的相互作用时，平均场近似就会出问题（强关联系统）。

### 10.4 低密度气体的热力学积分办法

我们求解配分函数，还有一种很厉害的方法，叫热力学积分的方法。我们直接解析写出 $Z_U$ 不是有困难吗？那我们能不能从简单情况入手，把这个东西积分出来？

考虑配分函数：

$$\begin{align*}Z(\beta)&=\frac{1}{N!h^{3N}}(\frac{2\pi m}{\beta})^{3N/2}Z_U(\beta)\end{align*}$$

对于低密度的气体，温度很高的时候，就可以当作理想气体，这在9.5中讨论过。也就是 $\beta\to 0^+$ 有：

$$\begin{align*}Z(\beta=0^+)&=\frac{1}{N!h^{3N}}(\frac{2\pi m}{\beta})^{3N/2}V^N\end{align*}$$

即 $Z_U(\beta\to 0^+)=V^N$

那我们可以尝试从这里为起点，积分出低密度情况下其它温度时的位形配分函数。

注意到平均势能有：

$$\bar{U}=\frac{\int U(q)e^{-\beta U(q)}{\rm d}^{3N}q}{\int e^{-\beta U(q)}{\rm d}^{3N}q}=-\frac{\partial \ln Z_U}{\partial \beta}$$

所以我们可以这样积：

$$\begin{align*}\ln Z_U(\beta)&=\ln Z_U(0)-\int_0^\beta\bar{U}(\beta'){ \rm d}\beta'\\&=N\ln V-\int_0^\beta\bar{U}(\beta'){ \rm d}\beta'\end{align*}$$

我们还是用每个分子的平均相互作用能来讨论：

$$\bar{U}=\frac{1}{2}N^2\bar{u}$$

而显然一样的，平均相互作用能有：

$$\bar{u}=-\frac{\partial}{\partial \beta}\ln \int e^{-\beta u}{ \rm d}^3 r$$

由于低密度，相互作用能其实会很小，所以有 $e^{-\beta u}\to 1$，不妨取：

$$\int e^{-\beta u}{ \rm d}^3r = \int 1+(e^{-\beta u}-1){ \rm d}^3 r\equiv V+I(\beta)$$

这个积分 $I(\beta)$ 是一个比较小的值，那么：

$$\bar{u}=-\frac{\partial}{\partial \beta}\Big(\ln V+\ln(1+\frac{I}{V})\Big)\approx-\frac{\partial}{\partial \beta}(\frac{I}{V}+...)$$

即可以取：

$$\bar{u}=-\frac{1}{V}\frac{\partial I}{\partial \beta}$$

那么有：

$$\bar{U}=\frac{1}{2}\frac{N^2}{V}\frac{\partial I}{\partial \beta}$$

积分可以得到：

$$\ln Z_U(\beta)=N\ln V+\frac{1}{2}\frac{N^2}{V}I(\beta)$$

所以我们又一次可以得到状态方程：

$$\begin{align*}\bar{p}&=\frac{1}{\beta}\frac{\partial \ln Z}{\partial V}=\frac{1}{\beta}\frac{\partial \ln Z_U}{\partial V}\\&=\frac{N}{V}kT-\frac{1}{2}I(\beta)\frac{N^2}{V^2}kT\\&=nkT-\frac{1}{2}I(\beta)n^2kT\end{align*}$$

所以这里相当于另外一中实际气体表述方式：viral 展开

$$\frac{p}{kT}=B_1n+B_2n^2+B_3n^3+...$$

这些系数 $B_1,B_2,...$就称为viral系数。

那么我就就知道了这种处理下：$B_2=-\frac{1}{2}I(\beta)$

我们取高温近似取钢球模型，会再一次得到 van de Waals 方程：

$$\begin{align*}I(\beta)&=\int_0^{+\infty}4\pi(e^{-\beta u}-1)r^2{ \rm d }r\\&\approx-\int_0^{R_0}4\pi r^2{ \rm d }r-\beta\int_{R_0}^{+\infty} u(r)4\pi r^2{ \rm d }r\\&=-\frac{4}{3}\pi R_0^3+4\pi u_0\beta\frac{R_0^3}{s-3}\\&=-\frac{4}{3}\pi R_0^3\Big(1-\frac{3}{s-3}\frac{u_0}{kT}\Big)\end{align*}$$

则有：

$$B_2= -\frac{1}{2}I(\beta)=\frac{2}{3}\pi R_0^3\Big(1-\frac{3}{s-3}\frac{u_0}{kT}\Big)=b-\frac{a}{kT}$$

则：

$$\frac{p}{kT}=n+(b-\frac{a}{kT})n^2$$

化简得：

$$p+an^2=nkT(1+nb)$$

而实际上由稀薄条件 $nb<<1$ 于是有：

$$(p+an^2)(1-bn)=nkT$$

我们又一次得到了van de Waals 方程。

## 第15章 不可逆过程和涨落

这里做一个概览就好，就是两个方程，解释清楚每一项是什么：主方程和朗之万方程

### 15.1 主方程 (Master Equation)

$$\frac{{ \rm d}P_r}{{ \rm d}t}=\sum_sP_sW_{sr}-\sum_sP_rW_{rs}$$

每一项的意义是：$P_r$ 表示处于 $r$ 状态上的粒子数，而其变化的个数有出和进两种原因。前一项对所有其它会来到 $r$ 状态的状态求和，$W_{sr}$ 为由状态 $s$ 转变到 $r$ 状态的概率。剩下剪掉的项就是从 $r$ 出去的个数。

### 15.2 Langevin 方程

相当于牛顿方程引入随机力：

$$m\frac{{ \rm d}v}{{ \rm d}t}=F(t)+\mathcal{F}(t)$$

其中 $F(t)$ 就是正常的外力；$\mathcal{F}(t)$ 是由于随机的力。在布朗运动中指代有微粒附近的分子碰撞产生的力。

## 数学附录

### 1. $\Gamma$函数

对阶乘函数的解析延拓。由于解析延拓的唯一性，这也是阶乘唯一的解析延拓结果：
$$\Gamma (x)=\int_0^{+\infty}t^{x-1}e^{-t}{ \rm d}t$$
积分变量 $t$ 沿着实数轴的正半轴从0跑到正无穷。从复变函数理论知道，在积分收敛的区域内，这个函数是解析的。实际上这个积分在负、非正整数处不收敛，这是一个亚纯函数。

显然，定义这个含参积分的一个初衷是为了构造阶乘性质。直接用分部积分可以看出：$$\begin{align*} \Gamma(x)&=-\int_0^{+\infty} t^{x-1}{ \rm d}(e^{-t})\\&=-t^{x-1} e^{-t}|_0^{+\infty}+\int_0^{+\infty} e^{-t}{ \rm d}(t^{x-1})\\&=(x-1)\int_0^{+\infty}t^{x-2}e^{-t}{ \rm d}t\\&=(x-1)\Gamma(x-1)\end{align*}$$

这里的计算要求$x>1$。我们已经观察到阶乘性质，又显然 $ \Gamma(1)=1$，那么我们可以递推知道正整数下Gamma函数有：

$$\Gamma(n+1)=n!\quad n\in\mathbb{N}$$

另外，还有一个好用的公式：余元公式
$$\Gamma(1-z)\Gamma(z)=\frac{\pi}{\sin \pi z}$$

证明我们在数学物理方法作业中做过，可以这样：
$$\begin{align*} \Gamma(1-z)\Gamma(z)&=\frac{\Gamma(1-z)\Gamma(z)}{\Gamma(1)}\\&={ \rm B}(z,1-z)\\&=\int_0^1t^{z-1}(1-t)^{-z}{ \rm d}t\\&=\int_0^{+\infty}\frac{s^{z-1}}{1+s}{ \rm d}s \end{align*}$$

这里用了 $t=\frac{s}{1+s}$ 的换元，这个积分我们在作业题中做过，多值函数的积分，就是一个留数定理，留作习题(bushi)

因此，我们就直接得到 $$\Gamma(\frac{1}{2})=\sqrt{\pi}$$

也可以直接递推得到半奇数的 $\Gamma$ 函数值：
$$\Gamma(\frac{2n+1}{2})=\frac{(2n-1)!!}{2^n}\sqrt{\pi}\quad n\in\mathbb{N}$$

这里定义要求 $(-1)!!=1$

### 2.高斯积分
由于各种各样的原因（主要是计算配分函数和利用分布函数计算各种有平均意义的物理量），我们不得不面对形如: $$I(\alpha,\beta)=\int_{0}^{+\infty}x^{\alpha}e^{-\beta x^2}{ \rm d }x$$
的积分，实际上这类积分在复变函数的视角下是平凡的，只需要知道 $\Gamma$ 函数就可以了。

利用 $z=\beta x^2$ 的还原，我们直接得到：

$$\begin{align*} I(\alpha,\beta)&=\int_0^{+\infty} (\frac{z}{\beta})^{\frac{\alpha}{2}}e^{-z}\frac{1}{2}(\beta z)^{-\frac{1}{2}}{ \rm d}z\\&=\frac{1}{2}\beta^{-(\alpha+1)/2}\int_0^{+\infty}z^{(\alpha+1)/2-1}e^{-z} { \rm d}z \\&=\frac{1}{2}\frac{\Gamma(\frac{\alpha+1}{2})}{\beta^{\frac{\alpha+1}{2}}}\end{align*}$$

这就是高斯积分的通用表达式，对于 $\alpha$ 取非负整数时，直接利用 $\Gamma$ 函数的结论可以得到：
$$I_{2n}(\beta)=\frac{(2n-1)!!}{2^{n+1}\beta^n}\sqrt{\frac{\pi}{\beta}}$$
$$I_{2n+1}(\beta)=\frac{1}{2}\frac{n!}{\beta^{n+1}}$$

特别的，如果考虑全体实数的积分，那奇数情况都是奇函数，积分为0，而偶数情况是偶函数，直接翻倍即可：
$$\hat{I}_{2n}(\beta)=\frac{(2n-1)!!}{2^{n}\beta^n}\sqrt{\frac{\pi}{\beta}}$$

特别记得： 
$$\hat{I}_{0}(\beta)=\int_0^{+\infty}e^{-\beta x^2}{ \rm d}x=\sqrt{\frac{\pi}{\beta}}$$

### 3.Strling公式

讲实话，这其实是高等数学作业里做过的一道题目的推论。这里进行一点点回忆。

$$\ln n!=\sum_{k=1}^n\ln k$$

首先，是一个很显然的夹逼，用定积分的面积意义，我们可以估计：

$$\int_1^n \ln x{ \rm d}x<\sum_{k=1}^n\ln k<\int_1^{n+1} \ln x{ \rm d}x$$

即我们可以确定：

$$n\ln n- n<\ln n!<(n+1)\ln(n+1)-(n+1)$$

所以我们估计：$\ln n! \approx n\ln n-n$ 是非常精确的，因为上下界就在这个范围。我们的估计偏差在：$(n+1)\ln(n+1)-(n+1)+n\ln n- n\approx \ln(n+1)$ 以内，可以接受。

另一方面，我们看出几乎 $n!\propto n^ne^{-n}=(\frac{n}{e})^n$

实际上，有更加精确的估计：

$$n!\approx \sqrt{2\pi n}\Big(\frac{n}{e}\Big)^n$$

这就是Striling公式。

这个估计有一个高数作业题给出了提示。

### 4.黎曼 $\zeta$ 函数 

初级的定义是：

$$\zeta(s)=\sum_{n=1}^{\infty}\frac{1}{n^s}\quad s=\sigma +i t\in\mathbb{C}(\sigma>1)$$

这个级数的收敛性很好判断。接着，我们可以将这个定义解析延拓到几乎整个复平面上。

我们在正文中已经被一种积分摧残过了，那就是：

$$F(s)=\int_0^{+\infty}\frac{t^{s-1}}{e^t-1}{ \rm d}t$$

我们可以用个一点点技巧化简这个积分：

$$\begin{align*}F(s)&=\int_0^{+\infty}t^{s-1}\frac{e^{-t}}{1-e^{-t}}{ \rm d}t\\&=\int_0^{+\infty}t^{s-1}\Big(\sum_{n=1}^{\infty}e^{-nt}\Big){ \rm d}t\\&=\sum_{n=1}^\infty\int_0^{+\infty}t^{s-1}e^{-nt}{ \rm d}t\\&=\sum_{n=1}^\infty\frac{1}{n^s}\int_0^{+\infty}(nt)^{s-1}e^{-nt}{ \rm d}(nt)\\&=\sum_{n=1}^\infty\frac{1}{n^s}\Gamma(s)=\Big(\sum_{n=1}^\infty\frac{1}{n^s}\Big)\Gamma(s)\\&=\zeta(s)\Gamma(s)\end{align*}$$

我们可以利用这个提示完成 $\zeta$ 函数的解析延拓，定义一种更加刁钻的，关于$\frac{t^{s-1}}{e^t-1}$ 的复积分，完成 $\zeta(s)$ 函数的解析延拓。这里按下不表，若敢兴趣可以查阅复分析相关书籍。

值得一提的是，在延拓完以后，用新的定义，可以有公式：

$$\zeta(s)=2^s\pi^{s-1}\sin\frac{\pi s}{2}\Gamma(1-s)\zeta(1-s)$$

这可以理解为解析延拓的方式，但实际上是构造后得到的解析函数 $\zeta(s)$ 的性质，但毕竟解析延拓有唯一性，你完全可以认为这个式子给出了解析延拓的结果。

计算 $\zeta(-1)=1+2+3+...$ 

$$\begin{align*}\zeta(-1)&=2^{-1}\pi^{-2}\sin(-\frac{\pi}{2})\Gamma(2)\zeta(2)\\&=-\frac{1}{2\pi^2}\times 1\times(\sum_{n=1}^\infty \frac{1}{n^2})\\&=-\frac{1}{2\pi^2}\times 1\times\frac{\pi^2}{6}=-\frac{1}{12} \end{align*}$$

你知道的，$1+2+3+...=-\frac{1}{12}$

这里列出一些 $\zeta(s)$ 函数的值 ：

$\zeta(2)=\frac{\pi^2}{6}\quad \zeta(4)=\frac{\pi^4}{90} \quad \zeta(6)=\frac{\pi^6}{945}...$

这些我们在高数中构造傅里叶级数，计算的出来。而一般的表达式，要引入伯努利数：

$$\zeta(2n)=(-1)^{n+1}\frac{(2\pi)^{2n}}{2(2n)!}B_{2n}$$

而奇数的取值将是令人难过的困难，解析地写出来的话，要用很复杂的积分表达。

### 5.形如 $\int_0^{+\infty} \frac{x^m}{e^x\pm1}{ \rm d}x$ 的积分

这类积分主要是在量子统计中需要计算，这种积分比较困难。

我们引入 $\zeta$ 函数，帮助我们计算出了

$$\int_0^{+\infty} \frac{x^m}{e^x-1}{ \rm d}x=\Gamma(m+1)\zeta(m+1)=m!\Big(\sum_{k=1}^\infty\frac{1}{k^{m+1}}\Big)$$

例如：

$$\int_0^{+\infty} \frac{x}{e^x-1}{ \rm d}x=1!\zeta(2)=1\times\frac{\pi^4}{6}=\frac{\pi^2}{6}$$

$$\int_0^{+\infty} \frac{x^3}{e^x-1}{ \rm d}x=3!\zeta(4)=6\times\frac{\pi^4}{90}=\frac{\pi^4}{15}$$

某种意义上，我们解决了积分：

$$I_-(m)=\int_0^{+\infty} \frac{x^m}{e^x-1}{ \rm d}x=m!\zeta(m+1)$$

而另外一积分看上去困难不少，但是我们可以这样去约化：

$$\begin{align*}I_+(m)&=\int_0^{+\infty} \frac{x^m}{e^x+1}{ \rm d}x\\&=\int_0^{+\infty}\frac{x^m(e^x-1)}{e^{2x}-1}{ \rm d}x\\&=\int_0^{+\infty}\frac{x^me^x}{e^{2x}-1}{ \rm d}x-\int_0^{+\infty}\frac{x^m}{e^{2x}-1}{ \rm d}x\\&=\frac{1}{2}\Big(\int_0^{+\infty} \frac{x^m}{e^x+1}{ \rm d}x+\int_0^{+\infty} \frac{x^m}{e^x-1}{ \rm d}x\Big)-\frac{1}{2^{m+1}}\int_0^{+\infty} \frac{(2x)^m}{e^{2x}-1}{ \rm d}(2x)\\&=\frac{1}{2}(I_+(m)+I_-(m))-\frac{1}{2^{m+1}}I_-(m)\end{align*}$$

因此，解得：

$$I_+(m)=\frac{2^m-1}{2^m}I_-(m)=\frac{2^m-1}{2^m}m!\zeta(m+1)$$

也就是说：

$$\int_0^{+\infty} \frac{x^m}{e^x+1}{ \rm d}x=\frac{2^m-1}{2^m}\int_0^{+\infty} \frac{x^m}{e^x-1}{ \rm d}x=\frac{2^m-1}{2^m}m!\zeta(m+1)$$

例如：

$$\int_0^{+\infty} \frac{x}{e^x+1}{ \rm d}x=\frac{2-1}{2}\times\frac{\pi^2}{6}=\frac{\pi^2}{12}$$

$$\int_0^{+\infty} \frac{x^3}{e^x+1}{ \rm d}x= \frac{2^3-1}{2^3}\times\frac{\pi^4}{15}=\frac{7\pi^4}{120}$$
