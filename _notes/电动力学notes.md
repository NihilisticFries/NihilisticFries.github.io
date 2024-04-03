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
$$\vec{F}=Q(\sum_i\frac{q_i}{4\pi\varepsilon_0r_i^2})$$

由于力的矢量合原理，我们直接得到了电场的叠加原理：

$$\vec{E}=\sum_i\frac{q_i}{4\pi\varepsilon_0r_i^2}$$

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
$$I  :=\frac{{\rm d}q}{{\rm d}t}$$

即单位时间经过线上某点的电荷量，一般由稳恒电流假设，认为线上各处（没有分支）电流是相等的。这时可以确定这条线上有一个不随时间变化的电荷线密度$\lambda$，这时考虑一个电流线的受力情况：

$$\vec{F}=\int_{\Gamma}\vec{v}\times\vec{B}{\rm d}q=\int_{\Gamma}  (\lambda\vec{v})\times\vec{B}{\rm d}l$$

而 $I=\frac{{\rm d}q}{{\rm d}t}=\frac{{\rm d}q}{{\rm d}l}\frac{{\rm d}l}{{\rm d}t}=\lambda v$ ，则可取：

$$\vec{F}=I\int_\Gamma {\rm d}\vec{l}\times\vec{B}$$

这就是电流线在磁场中受安培力的表达式。

如果考虑一个二维面上有运动的电荷，可以看作在二维面上有一个矢量场 $\vec{K}$ ，为表征流向（一维的时候不用定方向，因为线的切矢已经定义好方向了）所以定义成了矢量，本质上是二维面上的切空间中的矢量。

可以这样表征流过面上某个线段元的电荷量：

$${\rm d}q=\vec{K}\cdot{\rm d}\vec{l}{\rm d}t$$

$\vec{K}$ 被称为面电流密度，有 ${\rm d}a$ 是小面元：

---
