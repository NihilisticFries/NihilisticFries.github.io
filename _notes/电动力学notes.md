---

title: "电动力学note"
collection: notes
type: "Ungraduated course"
permalink: /teaching/电动力学notes
venue: " Wuhan University, 教三楼402"
date: 2024-04-03
location: "Wuhan, China"

---

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
