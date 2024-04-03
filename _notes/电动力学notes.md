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

我们希望考虑最一般的情况，即不一定有 $\nabla\cdot\vec{J}=0$ 成立时，应该如何。这时我们可以增加一个信念——电荷守恒。如果我们相信电荷守恒（实际上实验中正是如此，没有观察到过电荷的消失，它们只是转移），那其实总有 $\nabla\cdot\vec{J}+\frac{\partial \rho}{\partial t}=0$

那么我们可以写出：

$$\nabla\cdot(\nabla\times\vec{B})=\mu_0(\nabla\cdot\vec{J}+\frac{\partial \rho}{\partial t})$$

这是总成立的，注意到 $\rho=\varepsilon_0\nabla\cdot\vec{E}$

可以写出：
$$\nabla\cdot(\nabla\times\vec{B})=\mu_0(\nabla\cdot\vec{J}+\varepsilon_0\nabla\cdot\frac{\partial \vec{E}}{\partial t})=\nabla\cdot(\mu_0\vec{J}+\varepsilon_0\mu_0\frac{\partial \vec{E}}{\partial t})$$

于是这里我们就做一个大胆的猜测：

$$\nabla\times\vec{B}=\mu_0\vec{J}+\varepsilon_0\mu_0\frac{\partial \vec{E}}{\partial t}$$

实际上可以认为有一种等效电流云云，在电磁学中介绍过的位移电流假说，这便是Maxwell的天才工作。方程被写为：

$$\begin{cases} \nabla \cdot \vec{E}=\frac{\rho}{\varepsilon_0} \\\\ \nabla\times\vec{E}=-\frac{\partial \vec{B}}{\partial t} \\\\  \nabla \cdot\vec{B}=0 \\\\ \nabla\times\vec{B}=\mu_0\vec{J}+\varepsilon_0\mu_0\frac{\partial \vec{E}}{\partial t}\end{cases}$$

这个方程也便就是真空中的Maxwell方程组。

这个方程可以给出若干预言，后来被实验证实，在这些小心求证的基础上，我们认为那个大胆的假设是正确的。至此，我们也完成了真空中Maxwell方程组的归纳。

---

### 1.2 Maxwell方程组的对称性




---


### 1.3 介质中的Maxwell方程组

在结束了一些对真空中Maxwell方程组对称性的观察之后，我们来引入一些唯象的参量，将有介质的环境中的电磁场被纳入Maxwell方程组的考量中。

鉴于电动力学本身其实是一个较为经典的理论，所以这里提出的介质对外场响应的微观模型是较为经典的。电介质对电场的响应我们用原子分子的极化（转向极化、色散极化等等）来阐述；磁介质对磁场的响应我们用分子电流假说来阐述。

首先考虑极化。电介质在外电场的驱使下，电介质中的微观粒子会发生以下几种图像：
> (1) 原子/分子本身是电中性且正负电荷的中心是重合的，这时加一个电场，正负电荷会有相反运动的趋势，导致这些粒子整体电中性但正电荷中心和负电荷中心分离开来一段距离，可以等价地看作一个电偶极子。（2.6多极展开的观点看会更清晰，相当于保留多极展开的第二项）称为色散极化 <br> (2) 对于有的原子/分子本身其正负电荷的中心就不重合，那么在外电场的作用下，它们会转向使能量更低

在这些图像下，会导致电介质中有一个电偶极子的分布，这些电偶极子会激发电场，改变原电场。所以现在我们需要研究电偶极子分布场激发的电场。

对于一个电偶极子，我们考察离散的情况，即两个电荷量大小相等符号相反的两个点电荷，分开一个距离$d$，定义电偶极子的方向是从负电荷指向正电荷，那么：
$$\vec{p}=q\vec{d}$$
定义为一个电偶极子的偶极矩。

我们考虑这样一个带点客体激发的电势场，那么就会有：

$$\begin{align}V(\vec{r})=\frac{q}{4\pi\varepsilon_0}(\frac{1}{r_{+}}-\frac{1}{r_-})=\frac{q}{4\pi\varepsilon_0}(\frac{1}{\sqrt{r^2+d^2/4-rd\cos{\theta}}}-\frac{1}{\sqrt{r^2+d^2/4+rd\cos{\theta}}})\\\\ =\frac{q}{4\pi\varepsilon_0 r}(\frac{1}{\sqrt{1-(\frac{d}{r})\cos{\theta}+(\frac{d}{2r})^2}}-\frac{1}{\sqrt{1+(\frac{d}{r})\cos{\theta}+(\frac{d}{2r})^2}})\end{align}$$

考虑 $d << r$ 略去二阶小量，进行泰勒展开

$$\begin{align}V(\vec{r})&=\frac{q}{4\pi\varepsilon_0 r}((1-(-\frac{1}{2})(\frac{d}{r})\cos{\theta})-(1+(-\frac{1}{2})(\frac{d}{r})\cos{\theta}))\\\\& =\frac{q}{4\pi\varepsilon_0 r}(\frac{d}{2r}\cos\theta-(-\frac{d}2{r}\cos\theta))\\\\ &=\frac{qd\cos\theta}{4\pi\varepsilon_0 r^2}=\frac{\vec{p}\cdot\hat{r}}{4\pi\varepsilon_0r^2}\end{align}$$

所以电偶极子在宏观上会激发一个 $r^{-2}$ 衰减的一个电势场

不妨模仿将电荷变为电荷密度场，我们将电偶极子变为「电偶极子场」，实际上唯象地称为极化强度 $\vec{P}$ ：
$$\vec{P}(\vec{r'}):=\lim_{\Delta V \to 0}\frac{\sum\vec{p}}{\Delta V}$$

总之就是去描述密度，这样，自然地电势场为：
$$V(\vec{x})=\int_\Omega\frac{\vec{P}(\vec{r'})\cdot\hat{r}}{4\pi\varepsilon_0r^2}{\rm d}^3\vec{r'}$$

那么我们可以

---

## Chapter 2 静电学

### 2.1 静电学基本方程

我们看到电磁场的一般规律是：

$$\begin{cases} \nabla \cdot \vec{D}=\rho_0 \\\\ \nabla\times\vec{E}=-\frac{\partial\vec{B}}{\partial t}\\\\  \nabla \cdot\vec{B}=0 \\\\ \nabla\times\vec{H}=\vec{J}_0+\frac{\partial\vec{D}}{\partial t}\end{cases}$$

我们此处只讨论线性各向同性介质的情况: $\vec{D}=\varepsilon\vec{E}$

静电学问题即考虑可以定义普通电势的情况：要求一个带电体系激发的电场不再发生变化 $\varepsilon\frac{\partial\vec{E}}{\partial t}=\frac{\partial\vec{D}}{\partial t}=0$ ，且电势可以良好定义 $\nabla\times\vec{E}=0$ ，此时关于电场的方程可以完全分离出来

$$\begin{cases} \nabla \cdot \vec{D}=\rho_0 \\\\ \nabla\times\vec{E}=0 \end{cases}$$

空间中填满了分块的不同的线性各向同性材料，但是在一个局部（非介质分界面），我们总有 $\varepsilon$ 是一个常数，直接写出事实上的方程：

$$\begin{cases} \nabla \cdot \vec{E}=\frac{\rho_0}{\varepsilon} \\\\ \nabla\times\vec{E}=0 \end{cases}$$

或者可以直接定义电势： $\vec{E}=-\nabla V$ ，得到静电学基本方程：

$$\nabla^2V=-\frac{\rho_0}{\varepsilon}$$

注意，这就是我们所谓的静电平衡，是一个状态。我们用这个方程描述系统的前提是达到了静电平衡。所以静电平衡的方程不描述过程，所以在用本章的结论思考达到静电平衡的过程时是不合适的，不过许多高中生会乐于此。

静电学基本方程是一个Poission方程。其求解在数学上已有充分的讨论。

这里描述一种极其简单的情况，无限大真空空间。此时 $\nabla^2V=-\frac{\rho_0}{\varepsilon_0}$ ，解显然可以表述为：

$$V(\vec{x})=\int_{\infty}\frac{\rho_0(\vec{r'})}{4\pi\epsilon_0r}{\rm d}^3\vec{r'}$$

这是我们从库伦定律直接得到的观察，实际上也是格林函数解法的直接推论。

考虑到 $\nabla^2\frac{1}{r}=-4\pi\delta(\vec{x}-\vec{r'})$ ，有：

$\nabla^2G(\vec{x}\mid\vec{r'})=\delta(\vec{x}-\vec{r'})$ 的解为： $G(\vec{x}\mid\vec{r'})=-\frac{1}{4\pi r}$ ，进而有：
$$V(\vec{x})=\int_{\infty}-G(\vec{x}\mid\vec{r'})\frac{\rho_0(\vec{r'})}{\varepsilon_0}{\rm d}^3\vec{r'}=\int_{\infty}\frac{\rho_0(\vec{r'})}{4\pi\epsilon_0r}{\rm d}^3\vec{r'}$$

在讨论静电问题时，其实就是在考虑静电学基本方程的解，为了方便，我们选取无穷远处为参考点，此时无穷远处电势为0，这是电势极其相关微分运算得到的场应当在全空间上的积分是收敛的，或者说去一个极大的球壳保住我们考虑的体系，场在这个球壳上的面积分应当是0。

---

### 2.2 格林函数法
 
 对于一般的问题，应当有边界条件，即方程不是在全空间上成立的。我们在数学物理方法中讨论过相关问题。对于Poission方程的边值问题： $\alpha^2+\beta^2\neq0$
 
 $$\begin{cases}\nabla^2V=-\frac{\rho_0}{\epsilon}\equiv f\quad\mid_{\Omega_j} \\\\ \alpha V(\vec{x})+\beta \partial_n V(\vec{x})=B(\vec{x})\mid_{\vec{x}\in\partial\Omega_j}\end{cases}$$
 
 取方程：
 
 $$\begin{cases}\nabla^2G(\vec{x}\mid\vec{r'})=\delta(\vec{x}-\vec{r'})\quad\mid_{\Omega_j}\\\\ \alpha G(\vec{x}\mid\vec{r'})+\beta \partial_n G(\vec{x}\mid\vec{r'})=0\mid_{\vec{x}\in\partial\Omega_j}\end{cases}$$
 
 即考虑齐次边界条件的Green函数，这样的格林函数具有对称性：
 
 >定理1：好齐次边界条件格林函数具有对称性 <br> $$G(\vec{r_1}\mid\vec{r_2})=G(\vec{r_2}\mid\vec{r_1})$$

>证明：考虑 $G(\vec{r}|\vec{r_2})\delta(\vec{r}-\vec{r_1})-G(\vec{r}|\vec{r_1})\delta(\vec{r}-\vec{r_2})$ ，显然对 $\Omega_j$ 积分有：
>
>$$\int_{\Omega_j}[G(\vec{r}|\vec{r_2})\delta(\vec{r}-\vec{r_1})-G(\vec{r}|\vec{r_1})\delta(\vec{r}-\vec{r_2})]{\rm d}^3\vec{r}=G(\vec{r_1}|\vec{r_2})-G(\vec{r_2}|\vec{r_1})$$
>
><br>另一方面：
> $\delta(\vec{r}-\vec{r_i})=\nabla^2G(\vec{r}|\vec{r_i})\quad i=1,2$ 则：
>
>$$G(\vec{r_1}|\vec{r_2})-G(\vec{r_2}|\vec{r_1})=\int_{\Omega_j}[G(\vec{r}|\vec{r_2})\nabla^2G(\vec{r}|\vec{r_1})-G(\vec{r}|\vec{r_1})\nabla^2G(\vec{r}|\vec{r_2})]{\rm d}^3\vec{r}$$
><br>又由高斯公式：$$\int_\Omega(\psi\nabla^2\phi-\phi\nabla^2\psi){\rm d}V=\oint_{\partial\Omega}(\psi\partial_n\phi-\phi\partial_n\psi){\rm d}S$$则：$$G(\vec{r_1}|\vec{r_2})-G(\vec{r_2}|\vec{r_1})=\int_{\Omega_j}[G(\vec{r}|\vec{r_2})\partial_nG(\vec{r}|\vec{r_1})-G(\vec{r}|\vec{r_1})\partial_nG(\vec{r}|\vec{r_2})]{\rm d}S$$<br>又边界条件$\alpha G(\vec{r}|\vec{r_i})+\beta \partial_n G(\vec{r}|\vec{r_i})=B(\vec{x})|_{\vec{x}\in\partial\Omega_j}\quad i=1,2$告诉我们$(G(\vec{r}|\vec{r_i}),\partial_nG(\vec{r}|\vec{r_i}))$是共线的，或者说平行，自然有：$$G(\vec{r}|\vec{r_2})\partial_nG(\vec{r}|\vec{r_1})-G(\vec{r}|\vec{r_1})\partial_nG(\vec{r}|\vec{r_2})=0$$即$G(\vec{r_1}|\vec{r_2})-G(\vec{r_2}|\vec{r_1})=0$，则 $G(\vec{r_1}|\vec{r_2})=G(\vec{r_2}|\vec{r_1})$
一个显然的推论即是：$$\nabla^2G(\vec{x}|\vec{r'})=\nabla'^2G(\vec{r'}|\vec{x})$$

在这样对称性的启发下，我们构造：
$$\int_{\Omega_j}[V(\vec{r'})\nabla'^2G(\vec{r'}|\vec{x})-G(\vec{r'}|\vec{x})\nabla'^2V(\vec{r'})]{\rm d}^3\vec{r'}\\=\int_{\Omega_j}[V(\vec{r'})\nabla'^2\delta(\vec{r'}-\vec{x})-G(\vec{r'}|\vec{x})\nabla'^2V(\vec{r'})]{\rm d}^3\vec{r'}\\=V(\vec{x})-\int_{\Omega_j}G(\vec{x}|\vec{r'})f(\vec{r'}){\rm d}^3\vec{r'}$$
因此我们构造出解：
$$V(x)=\int_{\Omega_j}[V(\vec{r'})\nabla'^2G(\vec{r'}|\vec{x})-G(\vec{r'}|\vec{x})\nabla'^2V(\vec{r'})]{\rm d}^3\vec{r'}+\int_{\Omega_j}G(\vec{x}|\vec{r'})f(\vec{r'}){\rm d}^3\vec{r'}\\=\int_{\Omega_j}G(\vec{x}|\vec{r'})f(\vec{r'}){\rm d}^3\vec{r'}+\int_{\partial\Omega_j}[V(\vec{r'})\partial_n'G(\vec{r'}|\vec{x})-G(\vec{r'}|\vec{x})\partial_n'V(\vec{r'})]{\rm d}S'$$

有两种处理面积分的路径：
$V(\vec{r'})\partial_n'G(\vec{r'}|\vec{x})-G(\vec{r'}|\vec{x})\partial_n'V(\vec{r'})|_{\vec{r'}\in\partial\Omega_j}\\=V(\vec{r'})[\frac{\alpha}{\beta}G(\vec{r'}|\vec{x})+\partial_n'G(\vec{r'}|\vec{x})]|_{\vec{r'}\in\partial\Omega_j}-G(\vec{r'}|\vec{x})[\frac{\alpha}{\beta}V(\vec{r'})+\partial_n'V(\vec{r'})]|_{\vec{r'}\in\partial\Omega_j}\\=-\frac{1}{\beta}G(\vec{x}|\vec{r'})B(\vec{r'})|_{\vec{r'}\in\Omega_j}$

或者：
$V(\vec{r'})\partial_n'G(\vec{r'}|\vec{x})-G(\vec{r'}|\vec{x})\partial_n'V(\vec{r'})|_{\vec{r'}\in\partial\Omega_j}\\=-\partial_n'V(\vec{r'})[G(\vec{r'}|\vec{x})+\frac{\beta}{\alpha}\partial_n'G(\vec{r'}|\vec{x})]|_{\vec{r'}\in\partial\Omega_j}+\partial_n'G(\vec{r'}|\vec{x})[V(\vec{r'})+\frac{\beta}\alpha \partial_nV(\vec{r'})]|_{\vec{r'}\in\partial\Omega_j}\\=\frac{1}{\alpha}\partial_nG(\vec{x}|\vec{r'})B(\vec{r'})|_{\vec{r'}\in\Omega_j}$

即我们可以给出形式上的解：
$$V(\vec{x})=\int_{\Omega_j}G(\vec{x}|\vec{r'})f(\vec{r'}){\rm d}^3\vec{r'}-\frac{1}{\beta}\int_{\partial\Omega_j}G(\vec{x}|\vec{r'})B(\vec{r'}){\rm d}S'$$
$$V(\vec{x})=\int_{\Omega_j}G(\vec{x}|\vec{r'})f(\vec{r'}){\rm d}^3\vec{r'}+\frac{1}{\alpha}\int_{\partial\Omega_j}\partial_nG(\vec{x}|\vec{r'})B(\vec{r'}){\rm d}S'$$

可见求出格林函数，解就是唯一的了，而格林函数的求解实际上是困难的，但至少由格林函数边界条件的齐次性，我们可以断言其存在且唯一，所以对于这样的方程，解总是存在且唯一。

---

### 2.3 静电唯一性定理
我们已经初见静电学基本方程边界问题解的存在唯一性了，是从格林函数和数学物理方法的结论上看出来的。实际上距离我们常见的情况，还有一点点距离。另外不算一个特别严谨的证明。我们常见的情况是，一个存在一个导体组的空间，这个空间中的自由电荷都在导体中。对于这样一个问题，解是否有存在唯一性。

此时蕴含的边界条件是：取通过一种线性各向同性介质，其边界有三种情况：
>（1）导体的边界：由于静电平衡时，导体中没有电场（不然导体内电荷继续移动），导体是一个等势体；另外导体在不接触其它导体（大地）时电荷守恒。所以导体的边界条件有两类：导体的电势；导体上总电荷量。<br>（2）无穷远边界：我们认为场在无穷远处为0，所以在无穷远边界上，场的面积分总是0，所以我们可以忽略掉无穷远面积分的大小，直接取为0<br>（3）介质的交界面：有介质交界面的边界条件。实际上我们认为自由电荷只存在于导体中，所以有边界条件 $\vec{E}_{i\tau}=\vec{E}_{j\tau}\quad \varepsilon_i\vec{E}_{in}=\varepsilon_j\vec{E}_{jn}$

考虑一个导体组，作为一个带点体系，一定激发一个电场。这个体系的能量是：
$$W=\sum_j\int_{\Omega_j}\frac{1}{2}\vec{E}\cdot\vec{D}{\rm d}^3\vec{x}=\frac{1}{2}\sum_j\int_{\Omega_j}(\nabla V)\cdot(\varepsilon_j\nabla V){\rm d}^3\vec{x}\\=\frac{1}{2}\sum_j\int_{\Omega_j}[\nabla\cdot(V\varepsilon_j\nabla V)-V\nabla\cdot(\varepsilon_j\nabla V)]{\rm d}^3\vec{x}\\=\frac{1}{2}\sum_j\int_{\Omega_j}[\nabla\cdot(V\varepsilon_j\nabla V)-V\nabla\cdot\vec{D}]{\rm d}^3\vec{x}$$

我们要求了非导体中没有自由电荷，所以 $\nabla\cdot\vec{D}=0$ ，即：
$$W=\frac{1}{2}\sum_j\int_{\Omega_j}\nabla\cdot(V\varepsilon_j\nabla V){\rm d}^3\vec{x}=\frac{1}{2}\sum_j\oint_{\partial\Omega_j}V\varepsilon_j\partial_n V{\rm d}S_j$$
我们将边界分成上述3中边界考虑：

（1）无穷远面上的积分直接为0，直接扔掉。

（2）介质交界面上，有边界条件和连续性条件，两种介质 $\varepsilon_i$ 和 $\varepsilon_j$ 之间有交界处电势相等，且 $\varepsilon_i\partial_{n_i} V=-\varepsilon_j\partial_{nj} V$ ，这是因为边界上没有自由电荷，电位移矢量在法向上连续，同时交界处，两个连通区域在同一点的法向是相反的，有一个符号的差别。再积分进行求和，发现交界面的积分在对介质求和时通通消掉了。

（3）导体界面上，是等势体，电势相同，且导体表面电场方向垂直于导体表面。一样，对于导体区域的法向会与与其接触介质的法向相反。

我们用指标 $j$ 表示介质，指标 $i$ 表示导体。

$$W=-\frac{1}{2}\sum_i\oint_{\partial\Omega_i}V\varepsilon\partial_n V{\rm d}S_i=-\frac{1}{2}\sum_i V_i\oint_{\partial\Omega_i}\varepsilon\partial_n V{\rm d}S_i$$

考虑对导体表面用高斯定理：$\sigma_i=D_{n_i}=\varepsilon(-\partial_nV)$，则：

$$W=\frac{1}{2}\sum_i V_i\oint_{\partial\Omega_i}\sigma_i{\rm d}S_i=\frac{1}{2}\sum_i V_iQ_i$$

这样，整个场被转移到导体表面的性质上去了。这个结果也符合我们的物理预期。

从上面导体组的讨论中，我们收到启发，给出静电唯一性定理的阐述：
>定理1：静电唯一性定理：<br>对于一个空间，其中有若干个导体，导体都有界（保证无穷远电势为0）。导体之外的空间中分块充满了各种线性各向同性介质，且这些空间中可以分布一些自由电荷。给定各导体上的电势或总电荷量，方程的解唯一确定。<br>证明：相当于一个分块满足方程$\nabla^2V=-\frac{\rho_0}{\varepsilon_j}$，并在导体边界上配有$V|_{\partial \Omega_i}=V_i$或$\oint_{\partial\Omega_i}-\varepsilon\partial_nV{\rm d}S_i=Q_i$的边界条件。<br>假设有两个满足这个边值问题的解$V_1, V_2$，由于方程是一个线性方程，且边界条件也是线性的，取$V=V_1-V_2$，则$V$满足的方程为：$$\begin{cases} \nabla^2V=0\\V|_{\partial \Omega_i}=0 \quad{\rm or}\quad\oint_{\partial\Omega_i}-\varepsilon\partial_nV{\rm d}S_i=0\end{cases} $$且介质交界面的没有自由电荷。我们期望此时没有电场，即体系没有电场能。取：$$W=\frac{1}{2}\sum_j\int_{\Omega_j}\varepsilon_j(\nabla V)^2{\rm d}^3\vec{x}=-\frac{1}{2}\sum_i\oint_{\partial\Omega_i}V\varepsilon\partial_n V{\rm d}S_i$$不管是电势边界条件还是总电荷边界条件，对于每一个$i$，$\oint_{\partial\Omega_i}V\varepsilon\partial_n V{\rm d}S_i=0$，所以：$$\sum_j\int_{\Omega_j}\varepsilon_j(\nabla V)^2{\rm d}^3\vec{x}=0$$由 $(\nabla V)^2$的非负性知：$\nabla V\equiv0$，即$\nabla V_1\equiv\nabla V_2$<br>得到两个满足原方程的电场解一定是相同的$\vec{E}_1=\vec{E}_2$

我们证明了，对于我们常见的导体组情况，电场的解一定是唯一的，这就是静电唯一性定理。这说明一件事：对于一个导体组，给定一些边界条件，如果我猜出了它的解，那就不可能有其它解，那我猜的解就是唯一正确的解。以此为基础，可以发展电像法。

---
### 2.4 导体组的静电平衡

本节我们要讨论一个十分深刻的关于导体组静电平衡时的结论。导体组静电平衡时，某个导体所带的电势和总电荷量不是相互独立的。实际上，当你给定了一个导体的电势，这个导体的电荷量就确定了，反过来也是如此。这是静电唯一性定理的直接推论。原因很简单，每个导体带有一个电势或电荷量条件后，用静电唯一性定理就确定了唯一的电场（取无穷远为0时电势场也唯一确定），这时可以用这个解反算导体的另一个没有给定的信息（带电量或电势大小）。

这个结论应该深深地刻进脑海里，我们不能同时对一个导体给两个条件。

更深刻地，静电平衡时各导体的电势和各导体带电量之间是一个线性变换的关系。这本质是线性方程（叠加原理）的结果。这允许我们定义电容系数。

---

### 2.5 用分离变量法求解

实际上，除了猜测解外，我们从来没有给过一个实际的解法。我们现在只论述了导体组静电平衡时，解一定是唯一的而已。现在，我们可以用一些解pde的常用手段解方程。实际上我们在数学物理方法中也知道，我们能手解的pde极其有限，只有在特定形状的边界条件下，pde才能手解出一个级数形式。

大部分情况下，这无非是数学物理方法的习题。不过我们想把某些级数解直接当作结论，或者说，一种通解的形式，裱起来。

这里，我们选取最具有代表性的，物理中最喜欢的球对称性进行求解。

>考虑一个球面（半径为$R$）上有自由电荷（一个面电荷密度的形式给出），空间中其它位置都是真空，那么可以以这个球心为球坐标原点，我们要求电荷分布有一个旋转对称性，即取$\phi$维度上的电荷分布相同，电荷分布完全由$\sigma(\theta)$给出。有电势场$V(r,\theta)$。显然，我们要求解不能发散。

首先分离变量，我们知道球谐函数有$Y_l^m(\theta,\phi)=\sqrt{\frac{2l+1}{4\pi}\frac{(l-|m|)!}{(l+|m|)!}}P^{|m|}_l(\cos\theta)e^{im\phi}$。但是在$\phi$维度上有旋转对称性，解不应该显含$\phi$，这说明只能有：$m=0$此时，$P_l(\cos\theta)$成为了我们解在$\theta$维度上的的完备展开级数表示.

解为:$V(r,\theta)=\sum_{l=0}^\infty R_l(r)P_l(\cos \theta)$

此时径向分离变量结果为：$$\frac{{\rm d}}{{\rm d}r}(r^2\frac{{\rm d}}{{\rm d}r}R(r))-l(l+1)R(r)=0\\\Rightarrow r^2\frac{{\rm d}^2}{{\rm d}r^2}R(r)+2r\frac{{\rm d}}{{\rm d}r}R(r)-l(l+1)R(r)=0$$   

这是一个欧拉方程，在常微分方程中讨论过这一方程的求解办法。令 $t=\ln r$，记$D\equiv\frac{{\rm d}}{{\rm d}t}=\frac{{\rm d}r}{{\rm d}t}\frac{{\rm d}}{{\rm d}r}=r\frac{{\rm d}}{{\rm d}r}$，$y(t)\equiv R(r)$，得：
$$D(D-1)y+2Dy-l(l+1)y=0\\\Rightarrow D^2y+Dy-l(l+1)y=0$$
有本征方程：$\lambda^2+\lambda-l(l+1)=0$，解得$\lambda_1=l\quad \lambda_2=-(l+1)$

即$R(r)=y(t)=C_1e^{l\ln r}+C_2e^{-(l+1)\ln r}=C_1r^l+C_2\frac{1}{r^{l+1}}$

所以方程的级数解为：
$$V(r,\theta)=\sum_{l=0}^\infty A_lr^lP_l(\cos \theta)+\frac{B_l}{r^{l+1}}P_l(\cos \theta)$$

特别地，由于电势场在没有点电荷处不能发散，在球壳内，场不发散，即不能取负幂次项，所以必有$B_l=0$。相似的，在球壳外，也不能发散，不然能量无穷大，不符合物理，场在无穷远要收敛，所以$A_l=0$

通解为:
$$V(r,\theta)=\begin{cases}\sum_{l=0}^\infty A_lr^lP_l(\cos \theta)\quad r<R\\\\\sum_{l=0}^\infty \frac{B_l}{r^{l+1}}P_l(\cos \theta)\quad r>R\end{cases}$$

利用$\sigma(\theta)$来确定这些系数，无非是本征函数展开而已。

这里例解一种极其简单地情况：
>一个带点量为$q$的点电荷激发的电势场。取原点为距离该点电荷$a$的一个空间点，从该空间点到这个点电荷的射线形成$z$轴。求电势分布。

>解：显然绕$z$轴的$\phi$维度上，体系有旋转对称性。可以直接用级数通解表示：$$V(r,\theta)=\begin{cases}\sum_{l=0}^\infty A_lr^lP_l(\cos \theta)\quad r<a\\\\\sum_{l=0}^\infty \frac{B_l}{r^{l+1}}P_l(\cos \theta)\quad r>a\end{cases}$$但实际上，很显然这个解可以用余弦定理和库伦定律直接写出:：$$V(r,\theta)=\frac{q}{4\pi\varepsilon_0\sqrt{a^2+r^2-2ar\cos\theta}}$$考虑$r<a$ 的部分,有：  $$\frac{q}{4\pi\varepsilon_0\sqrt{a^2+r^2-2ar\cos\theta}}=\sum_{l=0}^\infty A_lr^lP_l(\cos \theta)\quad r<a$$ 取 $\cos \theta=1$,有 $$\frac{q}{4\pi\varepsilon_0\sqrt{(a-r)^2}}=\sum_{l=0}^\infty A_lr^lP_l(1)\quad r<a\\\Rightarrow\frac{q}{4\pi\varepsilon_0 (a-r)}=\sum_{l=0}^\infty A_lr^lP_l(1)\quad r<a\\\Rightarrow\frac{q}{4\pi\varepsilon_0a}\frac{1}{1-\frac{r}{a}}=\sum_{l=0}^\infty A_lr^lP_l(1)\quad r<a\\\Rightarrow\frac{q}{4\pi\varepsilon_0a}\sum_{l=0}^\infty(\frac{r}{a})^l=\sum_{l=0}^\infty A_lr^lP_l(1)\quad r<a$$所以对比系数得到：$$A_l=\frac{q}{4\pi\varepsilon_0a^{l+1}}\frac{1}{P_l(1)}$$而由勒让德多项式的Rodrigues公式：$$P_l(x)=\frac{1}{2^l l!}\frac{{\rm d}^l}{{\rm d}x^l}(x^2-1)^l$$取$x=1$时，上述求导的多项式中，凡是留有 $(x^2-1)$ 的多项式的项，一定为0。所以每一次必须求到$(x^2-1)$上（稍微列一下就清楚了）,有：$$P_l(1)=\frac{1}{2^ll!}l!(2x)^l|_{x=1}+0=1$$ 所以 $$A_l=\frac{q}{4\pi\varepsilon_0a^{l+1}}$$即 $$\frac{q}{4\pi\varepsilon_0\sqrt{a^2+r^2-2ar\cos\theta}}=\frac{q}{4\pi\varepsilon_0a}\sum_{l=0}^\infty \frac{r^l}{a^l}P_l(\cos \theta)\quad r<a $$ 我们其实得到了势能场在球壳内的级数解形式。

这里，我们取$a=1\quad q=4\pi\varepsilon_0$，有：
$$\frac{1}{\sqrt{1+r^2-2r\cos\theta}}=\sum_{l=0}^\infty r^lP_l(\cos \theta)$$

这个等式也是所谓的勒让德多项式母函数。

---

### 2.6 多极展开

我们现在退回到无穷大真空空间当中。考虑一个有界区域$\Omega$分布有电荷密度场，这个电荷密度区域会激发什么样的电势场？这个问题解析上我们可以回答：
$$V(\vec{x})=\int_\Omega\frac{\rho(\vec{r'})}{4\pi\varepsilon_0r}{\rm d}^3\vec{r'}$$
实际上，这样的计算是复杂的。因为本质上，$r$是由$\vec{x},\vec{r'}$共同决定的。其实也可以直接写出$r=|\vec{x}-\vec{r'}|$，这也就是余弦定理，可以令$\vec{x},\vec{r'}$夹角为$\alpha$，有：
$$\frac{1}{r}=\frac{1}{\sqrt{x^2+r'^2-2xr'\cos\alpha}}$$
这样的积分式是复杂的，如果能写成$r'$的多项式，看上去会好很多。从2.5中的讨论可以直接有：
$$\frac{1}{\sqrt{x^2+r'^2-2xr'\cos\alpha}}=\sum_{l=0}^\infty\frac{r'^l}{x^{l+1}}P_l(\cos\alpha)$$
所以我们可以写出：
$$V(\vec{x})=\sum_{l=0}^\infty\frac{1}{4\pi\varepsilon_0x^{l+1}}\int_\Omega {r'}^lP_l(\cos \alpha)\rho(\vec{r'}){\rm d}^3\vec{r'}$$

我们本质上其实是对原本精确的积分表达式做了一个洛朗展开。此时可以看出每一项貌似都有一些物理意义。在$\Omega$为一个有界区域时，取下$x>>r'$：

 如果可以略去$(\frac{r'}{x})^l$的高阶项，比如只留第一项（$P_0(x)=1$）：
 $$V(\vec{x})=\frac{1}{4\pi\varepsilon_0 x}\int_\Omega\rho(\vec{r'}){\rm d}^3\vec{r'}$$
 这时相当于带电客体相对于我们考虑的空间来说是极小的，这个表达式即将$\Omega$直看成一个点电荷，电势场就近似是对应带电量点电荷激发的电势场。

 我们显著地看到了对积分的简化。这是一种很好的近似手段，不过这也促使我们好奇其它项有没有什么物理意义。它们其实可以看作对点电荷场的一些修正项。

 考虑保留两项时：（$P_1(x)=x$）
 $$V(\vec{x})=\frac{1}{4\pi\varepsilon_0 x}\int_\Omega\rho(\vec{r'}){\rm d}^3\vec{r'}+\frac{1}{4\pi\varepsilon_0x^2}\int_\Omega r'\rho(\vec{r'})\cos \alpha{\rm d}^3\vec{r'}$$

 这修正项看着像电偶极子激发的电势场。
 
 我们退回简单的两个带相反等大电荷的点电荷情况：
 $$\int_\Omega r'\rho(\vec{r'})\cos \alpha{\rm d}^3\vec{r'}=\int_\Omega r'(q\delta(\vec{r'}-\vec{r_+})-q\delta(\vec{r'}-\vec{r_-}))\cos \alpha{\rm d}^3\vec{r'}\\=q(r_+\cos \alpha_+-r_-\cos \alpha_-)\\=q(r_+(\hat{r}_+\cdot\hat{x})-r_-(\hat{r}_-\cdot\hat{x}))\\=q(\vec{r_+}-\vec{r_-})\cdot\hat{x}=\vec{p}\cdot\hat{x}$$
这时电势场写为:$$V(\vec{x})=\frac{\vec{p}\cdot\hat{x}}{4\pi\varepsilon_0x^2}$$
这和我们之前对 $d<<x$ 情况下的电偶极子推导结果是相同的。

我们认为可以定义一种更加广泛的偶极矩:
$$\vec{p}:=\int_\Omega\vec{r'}\rho(\vec{r'}){\rm d}^3\vec{r'}$$
那么就有$$V(\vec{x})=\frac{q}{4\pi\varepsilon_0x}+\frac{\vec{p}\cdot\hat{x}}{4\pi\varepsilon_0x^2}$$
这种定义下，偶极矩可能会与坐标原点的选取有关。


其余项对应的多极具体意义？

我们可以考虑多极展开的第二项：
$$4\pi\varepsilon_0x^3V_2(\vec{x})=\int _\Omega r'^2\rho(\vec{r'})P_2(\cos \alpha){\rm d}^3\vec{r'}=\frac{1}{2}\int_\Omega r'^2\rho(\vec{r'})(3\cos^2\alpha-1){\rm d}^3\vec{r'}$$

这时我们记$\vec{r'}=(r_1',r_2',r_3')^T$，$\hat{x}=(x_1,x_2,x_3)^T$，显然$x_1^2+x_2^2+x_3^2=x_ix_j\delta_{ij}=1$

这时，可以将第二项写为：
$$4\pi\varepsilon_0x^3V_2(\vec{x})=\frac{1}{2}\int_\Omega \rho(\vec{r'})(3(\vec{r'}\cdot\hat{x})^2-r'^2){\rm d}^3\vec{r'}$$

观察$(3(\vec{r'}\cdot\hat{x})^2-r'^2)=3r'_ix_ir_j'x_j-r'^2x_ix_j\delta_{ij}=(3r'_ir'_j-r'^2\delta_{ij})x_ix_j$

这是一个关于$x_1,x_2,x_3$的二次型，我们期望将其写成矩阵形式。显然可以定义：

$$\hat{A}(\vec{r'}):=\begin{bmatrix} 2r'^2_1-r_2'^2-r_3'^2 & 3r_1'r_2' & 3r'_1r'_3 \\ 3r_2'r_1' & 2r'^2_2-r_3'^2-r_1'^2 & 3r_2'r_3' \\ 3r_3'r_1' & 3r_3'r_2' & 2r'^2_3-r_1'^2-r_2'^2 \end{bmatrix}$$

那么就可以写出：
$$4\pi\varepsilon_0x^3V_2(\vec{x})=\hat{x}^T\Big(\frac{1}{2}\int_\Omega \rho(\vec{r'})\hat{A}(\vec{r'}){\rm d}^3\vec{r'}\Big)\hat{x}$$

进而定义：$$\hat{Q}:=\frac{1}{2}\int_\Omega \rho(\vec{r'})\hat{A}(\vec{r'}){\rm d}^3\vec{r'}$$

或者直接写矩阵元：
$$Q_{ij}:=\frac{1}{2}\int_\Omega \rho(\vec{r'})(3r'_ir_j'-r'^2\delta_{ij}){\rm d}^3\vec{r'}$$

即是带电体的四极矩$\hat{Q}$，可以有：$$V_2(\vec{x})=\frac{\hat{x}^T \hat{Q}\hat{x}}{4\pi\varepsilon_0x^3}$$

可以看出来，这里我是为了不引入张量的概念强行用二次型的方式表述了这一点，将四极矩写成了矩阵的形式。实际上，还有两种处理方式，一种是许多传统电动教材使用并矢来描述四极矩；二是直接引入张量的概念，这是一个(0,2)型张量，与两个矢量作用得到一个数，是一个多重线性映射。

接下来的八极矩、十六极矩就不讨论了。因为许多情况下四极矩已经足够精确，另外一个就是我现在确实不会（

## Chapter 3
