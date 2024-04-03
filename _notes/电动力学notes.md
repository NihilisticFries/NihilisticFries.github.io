---

title: "电动力学note"
collection: notes
type: "Ungraduated course"
permalink: /teaching/电动力学notes
venue: " Wuhan University, 教三楼402"
date: 2024-04-03
location: "Wuhan, China"

---

施工中...

前言：这里我期望完成对电动力学理论框架的构建，是课程随笔，不过已经在纸质笔记本上预演过要写什么。之后我会尽量以我最满意的方式将电动力学的内容梳理出来。

## 目录
> 1 Maxwell方程组<br> $\quad$ 1.1 真空中Maxwell方程组的归纳<br> $\quad$ 1.2 Maxwell方程组的对称性<br> $\quad$ 1.3 介质中的Maxwell方程组 <br>2 静电学 <br> $\quad$ 2.1 静电学基本方程 <br> $\quad$ 2.2 格林函数法 <br> $\quad$ 2.3 静电唯一性定理<br> $\quad$ 2.4 导体组的静电平衡 <br> $\quad$ 2.5 用分离变量法求解 <br> $\quad$ 2.6 多极展开

## Chapter 1 Maxwell方程组

### 1.1 真空中Maxwell方程组的归纳

这里其实是对电磁学的快速复习。同时，也在此快速熟悉一些矢量分析的技巧。

首先，关于静止点电荷，在实验上总结出了库仑定律。真空中：

$$\vec{F}=\frac{q_1q_2}{4\pi\varepsilon_0r^2}\hat{r}$$

我们将这样定义全note的记号：场的坐标为
$\vec{x}$
，带电体的坐标（源坐标）
$\vec{r'}$，
在某个源来看，场点为:
$\vec{r}=\vec{x}-\vec{r'}$

注意
$\vec{x}$和
$\vec{r'}$
是两套完全独立的坐标系统，即认为这二者无关（所以刻意用了两种不同的符号），那么其对应的微分算符分别作用在另一个上的场上是总是0。即
$\nabla_x$
与只和
$\vec{r'}$
有关的场作用的结果是0，反过来
$\nabla'$
作用于只与
$\vec{x}$
有关的场时结果也总是0。而
$\vec{r}=\vec{x}-\vec{r'}$
所以实际上可以认为在作用于只与
$\vec{r}$
有关的场时：
$\nabla_x=\nabla;-\nabla'=\nabla$
（注意条件是作用于只与
$\vec{r}$
有关的场）

对于某个试探电荷 $Q$ ，其受到库仑力：
$$\vec{F}=Q(\sum_i\frac{q_i}{4\pi\varepsilon_0r_i^2}\hat{r_i})$$

由于力的矢量合原理，我们直接得到了电场的叠加原理：

$$\vec{E}=\sum_i\frac{q_i}{4\pi\varepsilon_0r_i^2}\hat{r_i}$$

同时也给出了电场的定义，一个点电荷系激发的电场就是如此计算的。

考虑连续化，将点电荷化为电荷密度，那么：

$$\vec{E}(\vec{x})=\int_{\infty}\frac{\rho(\vec{r'})}{4\pi\varepsilon_0r^2}\hat{r}{\rm d}^3\vec{r'}$$

简单地从这个式子推导出高斯定律是电磁学中的内容，这里直接数学观察。
$\frac{\hat{r}}{r^2}=-\nabla(\frac{1}{r})$ ，则

$$\vec{E}(\vec{x})=\int_{\infty}\frac{\rho(\vec{r'})}{4\pi\varepsilon_0}\nabla(-\frac{1}{r}){\rm d}^3\vec{r'}=-\nabla_{x}\int_{\infty}\frac{\rho(\vec{r'})}{4\pi\varepsilon_0r}{\rm d}^3\vec{r'}$$

这说明这种电场总是可以表示成某个标量场的梯度，定义电势：
$$V(\vec{x})=\int_{\infty}\frac{\rho(\vec{r'})}{4\pi\varepsilon_0r}{\rm d}^3\vec{r'}$$

所以可以有：
$\vec{E}(\vec{x})=-\nabla V(\vec{x})$

又注意到：
${\rm rot}\cdot{\rm grad}\equiv 0$ ，所以 $\nabla\times(\frac{\hat{r}}{r^2})=\nabla\times\nabla(-\frac{1}{r})=0\quad$

$$\nabla_x\times\vec{E}(\vec{x})=\int_{\infty}\frac{\rho(\vec{r'})}{4\pi\varepsilon_0}\nabla\times\nabla(-\frac{1}{r}){\rm d}^3\vec{r'}=0$$

即有：
$\nabla\times\vec{E}=0$

实际上简单讨论就会发现：
$\nabla^2\frac{1}{r}=-4\pi\delta(\vec{x}-\vec{r'})$

所以可以直接对电场求散度：
$$\nabla_x\cdot\vec{E}(\vec{x})=\int_{\infty}\frac{\rho(\vec{r'})}{4\pi\varepsilon_0}\nabla^2(-\frac{1}{r}){\rm d}^3\vec{r'}=\int_{\infty}\frac{\rho(\vec{r'})}{\varepsilon_0}\delta(\vec{x}-\vec{r'}){\rm d}^3\vec{r'}=\frac{\rho(\vec{x})}{\varepsilon_0}$$

即高斯定理：
$\nabla\cdot\vec{E}=\frac{\rho}{\varepsilon_0}$

至此库仑定律的数学推论就至此了。

这个方程也便就是真空中的Maxwell方程组。

这个方程可以给出若干预言，后来被实验证实，在这些小心求证的基础上，我们认为那个大胆的假设是正确的。至此，我们也完成了真空中Maxwell方程组的归纳。

我们需要细致地讨论一下电流的模型。实验上我们发现运动电荷在磁场中受到洛伦兹力：

$$\vec{F}=q\vec{v}\times\vec{B}$$

这时，我们可以定义一个量来表征运动的电荷。

如果运动的电荷只存在于一条一维的线中，和我们朴素的电流的认知比较像，可以定义流过线上某一点的电流强度:

$$ I  :=\frac{ {\rm d} q }{ {\rm d} t } $$

即单位时间经过线上某点的电荷量，一般由稳恒电流假设，认为线上各处（没有分支）电流是相等的。这时可以确定这条线上有一个不随时间变化的电荷线密度 $\lambda$ ，这时考虑一个电流线的受力情况：

$$\vec{F}=\int_{\Gamma}\vec{v}\times\vec{B}{\rm d}q=\int_{\Gamma}  (\lambda\vec{v})\times\vec{B}{\rm d}l$$

而 $I=\frac{ {\rm d} q}{ {\rm d} t}=\frac{ {\rm d} q}{ {\rm d} l}\frac{ {\rm d} l}{ {\rm d} t}=\lambda v$ ，则可取：

$$\vec{F}=I\int_\Gamma {\rm d}\vec{l}\times\vec{B}$$

这就是电流线在磁场中受安培力的表达式。

如果考虑一个二维面上有运动的电荷，可以看作在二维面上有一个矢量场 $\vec{K}$ ，为表征流向（一维的时候不用定方向，因为线的切矢已经定义好方向了）所以定义成了矢量，本质上是二维面上的切空间中的矢量。

可以这样表征流过面上某个线段元的电荷量：

$${\rm d}q=\vec{K}\cdot{\rm d}\vec{l}{\rm d}t$$

$\vec{K}$ 被称为面电流密度，有 ${\rm d}a$ 是小面元：

$$K{\rm d} l_{\parallel}=\frac{ {\rm d} q}{ {\rm d} t}=\frac{ {\rm d} q}{ {\rm d} a}\frac{ {\rm d} a}{ {\rm d} t }=\sigma\frac{ {\rm d} a}{ {\rm d}t}=\sigma\frac{ {\rm d}l_{\perp}}{ {\rm d}t}{\rm d} l_{\parallel}$$

进而有: $\vec{K}=\sigma \vec{v}$

那么这个面受到的洛伦兹力：

$$\vec{F}=\int_D\vec{v}\times\vec{B}{\rm d}q=\int_D(\sigma\vec{v})\times\vec{B}{\rm d}a=\int_D\vec{K}\times\vec{B}{\rm d}a$$

再进一步，考虑三维空间中的电荷移动，可以定义电流密度，单位时间内通过某个元面的电荷量有：
$${\rm d}q=\vec{J}\cdot{\rm d}\vec{S}{\rm d}t$$

可以推出：
$$\vec{J}\cdot{\rm d}\vec{S}=\frac{ {\rm d}q}{ {\rm d}t}=\frac{ {\rm d}q}{ {\rm d}V}\frac{ {\rm d}V}{ {\rm d}t}=\rho\frac{ {\rm d}V}{ {\rm d}t}$$

再利用 $\vec{J}\cdot{\rm d}\vec{S}=J{\rm d}a_\perp$ ， ${\rm d}V={\rm d}a_{\perp}{\rm d}l_{\parallel}$

$$J=\rho\frac{ {\rm d}l_{\parallel}}{ {\rm d}t}\Rightarrow\vec{J}=\rho\vec{v}$$

进一步，我们可以有整个三维体受力：
$$\vec{F}=\int_\Omega\vec{v}\times\vec{B}{\rm d}q=\int_\Omega(\rho\vec{v})\times\vec{B}{\rm d}V=\int_\Omega\vec{J}\times\vec{B}{\rm d}V$$

总之我们用各种方式定义了各种层面上的电流“密度”。

在实验上，我们也发现磁场是由运动的电荷激发的，有毕-萨公式：

$$\vec{B}(\vec{x})=\int_\Gamma \frac{\mu_0}{4\pi}\frac{I{\rm d}\vec{r'}\times\hat{r}}{r^2}$$

这是用电流元做实验得到的结果，经过上述定义，可以自然地推广：
$$I=\vec{J}\cdot{\rm d}\vec{S}=\vec{K}\cdot{\rm d}\vec{l}$$

自然地 $I{\rm d}\vec{r'}$ 表征了电流方向，有：

$$I{\rm d}\vec{r'}=\vec{J}{\rm d}V=\vec{K}{\rm d}a$$

对于三维：

$$\vec{B}(\vec{x})=\int_\Omega \frac{\mu_0}{4\pi}\frac{\vec{J}{\rm d}V\times\hat{r}}{r^2}=\int_\Omega \frac{\mu_0}{4\pi}\frac{\vec{J}(\vec{r'})\times\hat{r}}{r^2}{\rm d}^3\vec{r'}$$

对于二维面：
$$\vec{B}(\vec{x})=\int_D\frac{\mu_0}{4\pi}\frac{\vec{K}{\rm d}a\times\hat{r}}{r^2}=\int_D \frac{\mu_0}{4\pi}\frac{\vec{K}(\vec{r'})\times\hat{r}}{r^2}{\rm d}a'$$

形式上没什么区别，就像体电荷密度和面点和密度积出电场时地形式是一样的。

这里只对三维情况进行讨论。

由于可以显然地观察到：
$$\vec{B}(\vec{x})=\int_\Omega \frac{\mu_0}{4\pi}\frac{\vec{J}(\vec{r'})\times\hat{r}}{r^2}{\rm d}^3\vec{r'}=\int_\Omega\frac{\mu_0}{4\pi}\vec{J}(\vec{r'})\times\nabla(-\frac{1}{r}){\rm d}^3\vec{r'}$$

而 $\nabla\times(\frac{1}{r}\vec{J}(\vec{r'}))=\nabla(\frac{1}{r})\times\vec{J}(\vec{r'})+\frac{1}{r}\nabla\times\vec{J}(\vec{r'})$

实际上 ${J}(\vec{r'})$ 与 $\vec{x}$ 无关，所以 $\nabla_x\times\vec{J}(\vec{r'})=\vec{0}$

进而： $\nabla_x\times(\frac{1}{r}\vec{J}(\vec{r'}))=\nabla_x(\frac{1}{r})\times\vec{J}(\vec{r'})=\vec{J}(\vec{r'})\times\nabla(-\frac{1}{r})$

所以可以确定磁场一定有：
$$\vec{B}(\vec{x})=\int_\Omega\frac{\mu_0}{4\pi}\nabla_x\times(\frac{1}{r}\vec{J}(\vec{r'})){\rm d}^3\vec{r'}=\nabla_{x}\times\int_\Omega\frac{\mu_0}{4\pi}\frac{\vec{J}(\vec{r'})}{r}{\rm d}^3\vec{r'}$$

可以定义磁矢势：
$$\vec{A}(\vec{x})=\int_\Omega\frac{\mu_0}{4\pi}\frac{\vec{J}(\vec{r'})}{r}{\rm d}^3\vec{r'}$$

所以磁场一定可以表达成一个矢量场的旋度场：
$\vec{B}=\nabla\times\vec{A}$

注意到 ${\rm div}\cdot{\rm rot}\equiv 0$，所以：

$$\nabla\cdot\vec{B}=\nabla\cdot(\nabla\times\vec{A})=0$$

我们知道由于电荷守恒：

$$\begin{aligned}\frac{ {\rm d}}{ {\rm d}t}\int_{\Omega} \rho(\vec{r'}){\rm d}^3\vec{r'}=\oint_{\partial \Omega}\vec{J}(\vec{r'})\cdot{\rm d}\vec{S'}\\\\ \Rightarrow\int_{\Omega} \frac{\partial}{\partial t}\rho(\vec{r'}){\rm d}^3\vec{r'}=\oint_{\partial \Omega}\vec{J}(\vec{r'})\cdot{\rm d}\vec{S'}\\\\ \Rightarrow\int_{\Omega} \frac{\partial}{\partial t}\rho(\vec{r'}){\rm d}^3\vec{r'}=\int_\Omega\nabla'\cdot\vec{J}(\vec{r'}){\rm d}^3\vec{r'}\\\\ \Rightarrow\int_{\Omega} \Big(\frac{\partial}{\partial t}\rho(\vec{r'})-\nabla'\cdot\vec{J}(\vec{r'})\Big){\rm d}^3\vec{r'}=0\end{aligned}$$

由 $\Omega$ 任意性得到： $\frac{\partial \rho}{\partial t}+\nabla\cdot\vec{J}=0$

对于一个电流分布，我们认为其对应的电荷密度分布不变，也就是实验上常考虑的稳恒电流情况，这时 $\frac{\partial \rho}{\partial t}=0$ ，这就直接对电流密度加了一个很强的约束：

$$\nabla\cdot\vec{J}=0$$

参考电场的考虑，现在考虑磁场的旋度，为了方便，可以直接考虑磁矢势：

$$\begin{align}\nabla_x\times\vec{B}(\vec{x})&=\nabla_x\times(\nabla_x\times\vec{A}(\vec{x}))\\\\& =\nabla_x(\nabla_x\cdot\vec{A}(\vec{x}))-\nabla_x^2\vec{A}(\vec{x})\\\\& =\nabla_x(\int_\Omega\frac{\mu_0}{4\pi}\nabla_x\cdot\frac{\vec{J}(\vec{r'})}{r}{\rm d}^3\vec{r'})-\int_\Omega\frac{\mu_0}{4\pi}\nabla_x^2\frac{\vec{J}(\vec{r'})}{r}{\rm d}^3\vec{r'}\\\\& =\nabla_x(\int_\Omega\frac{\mu_0}{4\pi}\vec{J}(\vec{r'})\cdot(\nabla\frac{1}{r}){\rm d}^3\vec{r'})-\int_\Omega\frac{\mu_0}{4\pi}\vec{J}(\vec{r'})\nabla^2\frac{1}{r}{\rm d}^3\vec{r'}\\\\& =\nabla_x(\int_\Omega\frac{\mu_0}{4\pi}\vec{J}(\vec{r'})\cdot(\nabla\frac{1}{r}){\rm d}^3\vec{r'})-\int_\Omega\frac{\mu_0}{4\pi}\vec{J}(\vec{r'})(-4\pi\delta(\vec{x}-\vec{r'})){\rm d}^3\vec{r'}\\\\& =\int_\Omega\mu_0\vec{J}(\vec{r'})\delta(\vec{x}-\vec{r'}){\rm d}^3\vec{r'}+\nabla_x(\int_\Omega\frac{\mu_0}{4\pi}\vec{J}(\vec{r'})\cdot(\nabla\frac{1}{r}){\rm d}^3\vec{r'})\\\\& =\mu_0\vec{J}(\vec{x})+\nabla_x(\int_\Omega\frac{\mu_0}{4\pi}\vec{J}(\vec{r'})\cdot(\nabla\frac{1}{r}){\rm d}^3\vec{r'})\end{align}$$

考察 $\int_\Omega\frac{\mu_0}{4\pi}\vec{J}(\vec{r'})\cdot(\nabla\frac{1}{r}){\rm d}^3\vec{r'}$ 这一项积分式，看着能凑高斯定理的形式：

$$\begin{align}\int_\Omega\frac{\mu_0}{4\pi}\vec{J}(\vec{r'})\cdot(\nabla\frac{1}{r}){\rm d}^3\vec{r'} & = \frac{\mu_0}{4\pi}\int_\Omega\vec{J}(\vec{r'})\cdot(\nabla'(-\frac{1}{r})){\rm d}^3\vec{r'}\\\\ &=\frac{\mu_0}{4\pi}\Big(\int_\Omega\big(\vec{J}(\vec{r'})\cdot(\nabla'(-\frac{1}{r}))+(-\frac{1}{r})\nabla'\cdot\vec{J}(\vec{r'})\big){\rm d}^3\vec{r'}\Big)+\frac{\mu_0}{4\pi}\int_\Omega\frac{\nabla'\cdot\vec{J}(\vec{r'})}{r}{\rm d}^3\vec{r'}\\\\ &=\frac{\mu_0}{4\pi}\int_\Omega\nabla'\cdot(-\frac{\vec{J}(\vec{r'})}{r}){\rm d}^3\vec{r'}+\frac{\mu_0}{4\pi}\int_\Omega\frac{\nabla'\cdot\vec{J}(\vec{r'})}{r}{\rm d}^3\vec{r'}\\\\ &=-\frac{\mu_0}{4\pi}\int_{\partial\Omega}\frac{\vec{J}(\vec{r'})}{r}{\rm d}^3\vec{r'}+\frac{\mu_0}{4\pi}\int_\Omega\frac{\nabla'\cdot\vec{J}(\vec{r'})}{r}{\rm d}^3\vec{r'}\end{align}$$

我们对我们考虑的电流场做两个基本的假设：
 
 （1）电流场是稳恒电流场，即 $\nabla'\cdot\vec{J}(\vec{r'})\equiv 0$ 
 
 （2）我们考虑的积分域 $\Omega$ 囊括了一个连通的有电流密度的区域，即 $\vec{J}(\vec{r'})\mid_{\vec{r'}\in {\partial \Omega}}\equiv \vec{0}$

这是两个很合理的假设，这是我们在实验上很容易达到的情况，我们实验上的导线形成的回路就会很快稳定下来形成一个稳恒电流场；同时电流场常常只是分布在一个流通的有界区域内（导线内）。

这两个条件直接保证了上面两个积分全都是0，所以：

$$\int_\Omega\frac{\mu_0}{4\pi}\vec{J}(\vec{r'})\cdot(\nabla\frac{1}{r}){\rm d}^3\vec{r'}=0$$

进而我们得到：

$$\nabla_x\times\vec{B}(\vec{x})=\mu_0\vec{J}(\vec{x})$$

也就是所谓的安培定律： $\nabla\times\vec{B}=\mu_0\vec{J}$

至此，我们得到了毕-萨实验定律的数学推论。

这时我们可以总结出：

$$\begin{cases} \nabla \cdot \vec{E}=\frac{\rho}{\varepsilon_0} \\\\ \nabla\times\vec{E}=0\\\\  \nabla \cdot\vec{B}=0 \\\\ \nabla\times\vec{B}=\mu_0\vec{J}\end{cases}$$

这直接是两个实验定律的数学推论，对电磁场的散度和旋度进行了一定程度的描述。

如果电和磁没有关系，那故事就到此为止了。但是实际上他们之间有互相转换的关系，法拉第发现感生电场（从感应电动势总结）。我们回顾一下什么是电场，会使静止电荷响应的场就是电场（试探电荷来帮助我们认知是否有电场），所以把变化的磁场产生电动势的机制，看作是产生了电场，是一种自然的观点。

$$\oint_{\partial D}\vec{E}\cdot{\rm d}\vec{l}=-\frac{ {\rm d}}{ {\rm d}t}\int_D\vec{B}\cdot{\rm d}\vec{S}$$

这就是法拉第的电磁感应定律，电动势和磁通量的变化量有关。 $D$ 本身变化时用洛伦磁力或者说安培力就可以解释，这是电磁学中的认知。我们直接考虑 $D$ 不动的情况，此时磁场变化，可以将方程写为：

$$\oint_{\partial D}\vec{E}\cdot{\rm d}\vec{l}=-\int_D\frac{\partial}{\partial t}\vec{B}\cdot{\rm d}\vec{S}$$

用Stokes公式，有：

$$\int_{D}(\nabla\times\vec{E})\cdot{\rm d}\vec{l}=-\int_D\frac{\partial}{\partial t}\vec{B}\cdot{\rm d}\vec{S}$$

由 $D$ 任意性，得： $\nabla\times\vec{E}=-\frac{\partial \vec{B}}{\partial t}$

这是对感生电场的描述，如果将这种电场与我们原来讨论的静电场合成，自然还是有这一点。也就是说，电场的旋度总和磁场的随时变化有关。

这时方程变为：

$$\begin{cases} \nabla \cdot \vec{E}=\frac{\rho}{\varepsilon_0} \\\\ \nabla\times\vec{E}=-\frac{\partial \vec{B}}{\partial t} \\\\  \nabla \cdot\vec{B}=0 \\\\ \nabla\times\vec{B}=\mu_0\vec{J}\end{cases}$$

我们已经知道了磁能生电，并加到了这组方程当中。问题是没有电回到磁的机制，也就是说如果电磁规律如此，那么某种程度上宇宙中电场会远多于磁场。从一些哲学思辨中（比如《斐多篇》中苏格拉底关于生与死相互转换的讨论），我们可以有这样的信念——磁应该也要能生电。（注：这里关于哲学的引证只是一种阐释，其实也有不能相互转换的东西，比如热能这种无序的能量不能再不付出任何代价地变成有序的能量，其实关键的是对理论本身的理解以及提出猜想可能的理由）

也许我们应该把 $\frac{\partial \vec{E}}{\partial t}$ 这样的项放入到方程里面。

观察到最后一个式子： $\nabla\times\vec{B}=\mu_0\vec{J}$ ，实际上描述了一个旋度场，取散度一定是0：

$$0=\nabla\cdot\vec{J}$$

也就是这个方程一定只在电流分布是稳恒电流时成立。虽然这是实验室里大部分时候出现的情况，但是实际上在达到稳恒电流的过程中这个条件是不成立的，极端地，在有电容器时，这个条件其实很好破坏。这很大程度上限制了这个方程的使用范围。


---
