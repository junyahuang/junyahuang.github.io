---
layout: post
title: 离散数学笔记2
date: 2021-03-22
categories: marginalia
tags: [笔记]
description: 离散数学好难搞
header-img: "img/headline4.jpg"
catalog:  true
typora-root-url: ../../junyahuang.github.io
---



## 二元关系



### 序偶和笛卡尔积



#### 有序组的定义

- 由两个元素按照一定的次序组成的二元组称为序偶，记作 $<x, y>,$ 其中 $x$ 是第一元素， $y$ 是第二元素。

  -  张明喜欢离散数学可用序偶表示为：$<$ 张明, 离散数学 $>$
  - 英语课本在书桌上可用序偶表示为 : $<$ 英语课本, 书桌 $>$

- 由定义可见，两个序偶 $<a, b>=<c, d>$ 当且仅当 $a=c$ 且 $ b=d$

  - 若序偶 $<x+y, 2 y-1>=<3 y-4,5>,$ 根据序偶相等的定义有 $x+y=3 y-4,2 y-1=5$

  - 解得 $x=2, y=3$



#### 笛卡尔积

- 设 $A, B$ 是两个集合，称集合 $A \times B=\{<x, y>I \mid(x \in A) \wedge(y \in B)\}$ 为集合 $A$ 与 $B$ 的笛 卡儿积
  - 令 $A$ 为某大学所有学生的集合， $B$ 表示该大学开设的所有课程的集合，则 $A \times B$ 可表示该校学生选课的所有可能情况。
  - 集合 $A=\{1,2\}, B=\{a, b, c\}$ 的笛卡儿积 $A \times B=\{<1, a>,< 1, b>,<1, c>,<2, a>,<2, b>,<2, c>\}$
    而 $B \times A=\{<a, 1>,<b, 1>,<c, 1>,<a, 2>,<b, 2>,<c, 2>\}$

- 由笛卡儿积定义可以看出:
  - 设 $A, B$ 是任意两个集合，则不一定有 $A \times B=B \times A,$ 即**笛卡儿积不满足交换律**
  - $A \times B=\varnothing$ 当且仅当 $A=\varnothing$ 或者 $B=\varnothing$
    - $A \times \varnothing = \varnothing,\varnothing \times A = \varnothing$
  - 设 $A, B, C$ 是任意三个集合，则不一定有 $A \times(B \times C)=(A \times B) \times C,$ 即**笛卡儿积不满足结合律**
  - 当集合 $A, B$ 都是有限集时， $|A \times B|=|B \times A|=|A| \times|B|$
  - **笛卡儿积对并运算和交运算满足分配律**
  - 设$A、B、C、D$ 为非空集合，则$A \subseteq B \cap C \subseteq D \rightleftarrows A\times C = B\times D $
    - $A,B$ 其中一个为空集时只能从左到右，都不是空集或都是空集时两端成立



#### 推广

- 由 $n$ 个元素 $a_{1}, a_{2}, \cdots, a_{n}$ 按照一定次序组成的 $n$ 元组称为 $n$ 重有序组，记 作 $<a_{1}, a_{2}, \cdots, a_{n}>\cdot$ 其中 $a_{1}$ 是第一个元素，a $_{2}$ 是第二个元素， $\cdots, a_{n}$ 是第 $n$ 个元素
- 设 $A_{1}, A_{2}, \cdots, A_{n}$ 是 $n$ 个集合，称集合 $A_{1} \times A_{2} \times \cdots \times A_{n}=\left\{<a_{1}, a_{2}, \ldots, a_{n}>\mid a_{i} \in A_{i}, i=1,2,3, \cdots, n\right\}$ 为集合 $A_{1}, A_{2}, \cdots, A_{n}$
  的笛卡儿积。当 $A_{1}=A_{2}=\cdots=A_{n}=A$ 时 $,$ 可记 $A_{1} \times A_{2} \times \cdots \times A_{n}=A^{n}$ 。

  - 两个 $n$ 重有序组 $<a_{1}, a_{2}, \cdots, a_{n}>=<b_{1}, b_{2}, b_{3}, \cdots, b_{n}>$ 当且仅当$ a_{i}=b_{i}, i=1,2, \ldots, n$
  - 当集合 $A_{1}, A_{2}, \cdots, A_{n}$ 都是有限集时， $\left|A_{1} \times A_{2} \times \cdots \times A_{n}\right|=\left|A_{1}\right| \times\left|A_{2}\right| \times \cdots \times|A n|$



### 关系的定义



#### 二元关系的定义

> ​	今 $A$ 为某大学所有学生的集合， $B$ 表示该大学开设的所有课程的集合，则 $A \times B$ 可表示该 校学生选课的所有可能情况。而真正的选课情况 ( 即选课关系 ) 则会是 $A \times B$ 的某一个子集
> ​	令 $F$ 为某地所有父亲的集合， $S$ 表示该地所有儿子的集合，则 $F \times S$ 可表示父子关系的所有 可能情况。而真正的父子关系则会是 $F \times S$ 的某一个子集

- 任何一个序号的集合确定了一个二元关系
- 设 $A, B$ 为两个非空集合，称 $A \times B$ 的**任意子集** $R$ 为从 $A$ 到 $B$ 的一个二元关系 $,$ 简称**关系** (relation)
  - 其中，$A$ 称为关系 $R$ 的**前域** , $B$ 称为关系 $R$ 的**后域**
  - 如果 $A=B,$ 则称 $R$ 为 $A$上的一个二元关系
  - 解题时，开篇为：设 $R$ 为 $A$ 到 $B$ 的二元关系 —— $R \subseteq A \times B$
    - 或 $R$ 是 $A$ 上的关系 —— $R \subseteq A \times A $
  - 若序偶 $<x, y>\in R,$ 通常把这一事实记为 $x R y$， 读作 " $x$ 对 $y$ 有关系 $R$ "
  - 若序偶 $<x, y>\notin R,$ 通常把这一事实记为 $x \not R y$， 读作 " $x$ 对 $y$ 没有关系 $R$ "
  - 设 $R_{1}$ 为自然数集合上的小于关系 $,$ 则 $<2,3>\in R_{1}\left(\right.$ 或 $\left.2 R_{1} 3\right),$ 但 $<5,5>\notin R_{1}($ 或 $\left.5 \not R_{1} 5\right)$
    - 设 $R_{2}$ 为中国城市的地区归属关系，则 成都R $_{2}$ 四川，但 重庆 $\not R_{2}$ 四川



#### 枚举二元关系

- 假设 $A=\{a, b\} B=\{c, d\},$ 试写出从 $A$ 到 $B$ 的所有不同关系

  解 $\quad$ 首先求两个集合的笛卡儿积： $A \times B=\{<a, c>,<a, d>,<b, c>,<b, d>\}_{0}$
  再求 $A \times B$ 的所有不同子集：

  - 0 元子集：$\varnothing$
  - 1 元子集 : $\{<a, c>\},\{<a, d>\},\{<b, c>\},\{<b, d>\}$
  - 2 元子集 : $\{<a, c>,< a, d>\},\{<a, c>,< b, c>\},\{<a, c>,<b, d>\},\{<a, d>,<b, d>\},$$\{<a, d>,<b, d>\},\{<b, c>,<b, d>\}$
  - 3 元子集：
  $\{<a, c>,< a, d>,< b, c>\},\{<a, c>,<a, d>,< b, d>\},\{<a, c>,< b, c>,<b, d>\}$$\{<a, d>,< b, c>,< b, d>\}$
  - 4 元子集 : $\{<a, c>,<a, d>,< b, c>,<b, d>\}$ (全关系)
  
  所以，上面的 16 个不同子集就是从 $A$ 到 $B$ 的所有不同关系



#### 重要关系

- 当 $R=\varnothing$ 时，称 $R$ 为从 $A$ 到 $B$ 的**空关系**(empty relation)
- 当 $R=A \times B$ 时，称 $R$ 为从 $A$ 到 $B$ 的**全关系**(total relation) 
  - $ A$ 上的全关系通常记 为 $E_{A}$
- 当 $R=I_{A}=\{< x, x>| x \in A\}$ 时，称 $R$ 为 $A$ 上的恒等关系(identity relation)



#### 有限集合的二元关系数量

- 当集合 $A, B$ 都是有限集时， $A \times B$ 共有 $|A| \times|B|$ 个不同的元素，这些元素将会产生 $2^{|A| \times|B|}$ 个不同的子集。即，从 $A$ 到 $B$ 的不同关系共有 $2^{|A| \times|B|}$ 个。



#### 定义域和值域

- 设 $R$ 是从 $A$ 到 $B$ 的二元关系，则 $A$ 为关系 $R$ 的前域 $, B$ 为关系 $R$ 的后域。令： 
  - $C=\{x \mid x \in A, \exists y \in B,<x, y>\in R\}, D=\{y \mid y \in B, \exists x \in A,<x, y>\in R\}$
  - 称 $C$ 为 $R$ 的定义域(domain), 记为 $C=\operatorname{dom} R ; D$ 为 $R$ 的值域(range), 记为 $D=\operatorname{ran} R$; $\operatorname{fld}R $=$ \operatorname{dom}R$ $\cup \operatorname{ran} R$ 为 $R$ 的域(field)
    - $R_{Z}=\{<x, y>\mid(x, y \in Z) \wedge(|x|=|y|=7)\},$ 则
      $\operatorname{dom}R$ $\left._{Z}=\{7,-7\}, \operatorname{ran} R_{Z}=\mathbb{\{} 7,-7\right\},$ $\operatorname{fld}R$ $_{Z}=\{7,-7\}$



#### 二元关系概念的推广

- 设 $A_{1}, A_{2}, \cdots, A_{n}$ 为 $n$ 个非空集合，称 $A_{1} \times A_{2} \times \cdots \times A_{n}$ 的任意子集 $R$ 为 $A_{1}, A_{2}, \cdots, A_{n}$ 的一个 $n$ 元关系(n-ary relation)
  - 在 $n$ 元关系中，最常用的是二元关系，因而，在不引起混淆的情况下，提到的关系均指二元关系



### 关系的表示



#### 集合表示法

- 关系是一种特殊的集合，因此集合的两种基本表示法 (枚举法和叙述法)，可以用 到关系的表示中.
  - 集合 $A=\{1,2,3,4\}$ 上的整除关系 $R$ 可用枚举法表示为：
    $R=\{<1,1>,<1,2>,<1,3>,<1,4>,<2,2>,<2,4>,<3,3>,<4,4>\}$
  - 实数集 $\mathrm{R}$ 上的“相等" 关系 $S$ 可用叙述法表示为 $S=\left\{< x, y> \mid(x, y \in R) \wedge(x=y)\right\}_{0}$



#### 关系图表示法$(A \neq B)$

- 设 $A=\left\{a_{1}, a_{2}, \cdots, a_{n}\right\}, B=\left\{b_{1}, b_{2}, \cdots, b_{m}\right\}, R$ 是从 $A$ 到 $B$ 的一 个关系.
  - 集合中的元素 $a_{1}, a_{2}, \cdots, a_{n}$ 和 $b_{1}, b_{2}, \cdots, b_{m}$ 分别作为图中的结点， 用 "$ \circ$" 表示
  - 如果 $<a_{i}, b_{j}>\in R,$ 则从 $a_{i}$ 到 $b_{j}$ 可用 一有向边 $a_{i} \longrightarrow b_{i}$ 相连。

<img src="/img-post/2021-03-22-Discrete_mathematics2/5iHJpufTCSw5vXPytScYOlkKx_seOTNO0p2dYNDAk-k.original.fullsize.png" style="zoom:50%;" />



#### 关系图表示法$(A = B)$

- 设 $A=\left\{a_{1}, a_{2}, \cdots, a_{n}\right\}, R$ 是 $A$ 上的一个 关系
  - 集合中的元素 $a_{1}, a_{2}, \cdots, a_{n}$ 分别作为 图中的结点，用 "$\circ$" 表示
  - 如果 $<a_{i}, a_{j}>\in R,$ 则从 $a_{i}$ 到 $a_{j}$ 可用一有向边 $a_{i} \longrightarrow a_{i}$ 相连
  - 如果 $<a_{i}, a_{i}>\in R,$ 则从 $a_{i}$ 到 $a_{i}$ 可用 一带箭头的小圆圈中表示，即画一个自环。

<img src="/img-post/2021-03-22-Discrete_mathematics2/tM3O0rvs2ZMlriI41GTZuGNeTO3fZKx__hVKAm5cms0.original.fullsize.png" style="zoom:50%;" />



#### 关系矩阵表示法

- 设 $A=\left\{a_{1}, a_{2}, \cdots, a_{n}\right\}, B=\left\{b_{1}, b_{2}, \cdots, b_{m}\right\}, R$ 是从 $A$ 到 $B$ 的一个二元关系，称矩阵$M_{R}=\left(m_{i j}\right)_{n \times m}$ 为关系 $R$ 的**关系矩阵**(relation matrix)，其中：
  - $m_{i j}=\left\{\begin{array}{l}1 \quad<a_{i}, b_{j}>\in R \\ 0 \quad<a_{i}, b_{j}>\notin R\end{array},(1 \leqslant i \leqslant m, 1 \leqslant j \leqslant n)\right.$ 
  - 又称 $M_{R}$ 为 $R$ 的**邻接矩阵**(adjacency matrix).

<img src="/img-post/2021-03-22-Discrete_mathematics2/qTRoewgmeP66l-_z2_rCsYzhDM0Yx8kdjVMWkbdkKmw.original.fullsize.png" style="zoom:50%;" />



#### 布尔矩阵的并和交运算

- 如果 $A=\left(a_{i j}\right)$ 和 $B=\left(b_{i j}\right)$ 是两个 $m \times n$ 矩阵，则 $A$ 和 $B$ 的并也是一个 $m \times n$ 矩 阵，记为 $A \vee B=C=\left(c_{i j}\right),$ 其中：
  - $c_{i j}=\left\{\begin{array}{ll}1 & \text { if } a_{i j}=1 \text { or } b_{i j}=1 \\ 0 & \text { if } a_{i j}=0 \text { and } b_{i j}=0\end{array}\right.$
- 如果 $A=\left(a_{i j}\right)$ 和 $B=\left(b_{i j}\right)$ 是两个 $m \times n$ 矩阵，则 $A$ 和 $B$ 的交也是一个 $m \times n$ 矩 阵，记为 $A \wedge B=C=\left(c_{i j}\right),$ 其中：
  - $c_{i j}=\left\{\begin{array}{ll}1 & \text { if } a_{i j}=1 \text { and } b_{i j}=1 \\ 0 & \text { if } a_{i j}=0 \text { or } b_{i j}=0\end{array}\right.$



设 $A=\left(\begin{array}{lll}1 & 0 & 1 \\ 1 & 1 & 1 \\ 1 & 0 & 0 \\ 0 & 0 & 1\end{array}\right), B=\left(\begin{array}{lll}0 & 0 & 0 \\ 1 & 0 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1\end{array}\right)$
则

 $A \vee B=\left(\begin{array}{lll}1 & 0 & 1 \\ 1 & 1 & 1 \\ 1 & 1 & 0 \\ 0 & 1 & 1\end{array}\right), A \wedge B=\left(\begin{array}{lll}0 & 0 & 0 \\ 1 & 0 & 1 \\ 1 & 0 & 0 \\ 0 & 0 & 1\end{array}\right) .$



#### 布尔矩阵的积运算

- 如果 $A=\left(a_{i j}\right)$ 是 $m \times p$ 矩阵, $B=\left(b_{i j}\right)$ 是 $p \times n$ 矩阵，则$A$和 $B$ 的积是一个 $m \times n$ 矩 阵，记为 $A \odot B=C=\left(c_{i j}\right)$, 其中：
  - $c_{i j}=\left\{\begin{array}{ll}1 & \exists k, a_{i k}=1 \text { and } b_{k j}=1 \\ 0 & \text { else }\end{array}\right.$
- 行 $\times$ 列，如果全部的对应乘积都是 0，结果就是 0 ，有一项非 0 都取 1

设 $A=\left(\begin{array}{lll}1 & 0 & 1 \\ 1 & 1 & 1 \\ 1 & 0 & 0 \\ 0 & 0 & 1\end{array}\right), B=\left(\begin{array}{llll}0 & 0 & 0 & 1 \\ 1 & 0 & 1 & 1 \\ 1 & 1 & 0 & 0\end{array}\right)$

则 $A \odot B=\left(\begin{array}{llll}1 & 1 & 0 & 1 \\ 1 & 1 & 1 & 1 \\ 0 & 0 & 0 & 1 \\ 1 & 1 & 0 & 0\end{array}\right)$



### 关系的运算



#### 关系的基本运算

- 关系是一种特殊的集合，因此集合的所有基本运算 ( 并、交、差、补 )，都可以应用到关系中，并且同样满足集合的所有运算定律
- 设 $R, S$ 是从 $A$ 到 $B$ 的两个关系，则
  - $R \cup S=\{<x, y>\mid(x R y) \vee(x S y)\}$
  - $R \cap S=\{<x, y>\mid(x R y) \wedge(x S y)\}$
  - $R-S=\{<x, y>\mid(x R y) \wedge(x \not s y)\}$
  - $\bar{R}=\{<x, y>\mid(x \not R y)\}(\text { 即全集为 } A \times B)$



设 $A=\{a, b, c\}, B=\{1,2,3,4\},$ 从 $A$ 到 $B$ 的关系 $R$ 和 $S$ 定义为 $：$ 	$R=\{<a, 1>,<b, 2>,<c, 3>\}, S=\{<a, 1>,<a, 2>,<a, 3>,<a, 4>\}$
计算 $R \cup S, R \cap S, S-R, \bar{R}$.

$R \cup S=\{<a, 1>,<b, 2>,<c, 3>,<a, 2>,<a, 3>,<a, 4>\}$
$R \cap S=\{<a, 1>\} ;$
$S-R=\{<a, 2>,<a, 3>,<a, 4>\} ;$
$\bar{R}=A \times B-R=\{<a, 1>,<a, 2>,<a, 3>$

$,<a, 4>,<b, 1>,<b, 2>,<b, 3>,<b, 4>,$

$<c, 1>,<c, 2>,<c, 3>,<c, 4>\}-\{<a, 1>,<b, 2>,<c, 3>\}$
$=\{<a, 2>,<a,3>,<a, 4>,<b, 1>,<b, 3>,<b, 4>,<c, 1>,<c, 2>,<c, 4>\}$



#### 关系的复合运算

- 设 $A, B, C$ 是三个集合， $R$ 是从 $A$ 到 $B$ 的关系， $S$ 是从 $B$ 到 $C$ 的关系 (即 $R: A \rightarrow B, S: B \rightarrow C),$ 则 $R$ 与 $S$ 的**复合关系** $($ 合成关系 $)($ composite relation）
  - 关系 $R$ 的后域是关系 $S$  的前域
  - $ R \circ S$ 是从 $A$ 到 $C$ 的关系，并且 $: R \circ S=\{<x, z>\mid(x \in A) \wedge(z \in C) \wedge(\exists y)(y \in B \wedge x R y \wedge y S z)\}$
  - 运算 "o" 称为复合运算(composite operation)
    - 设$A=\{a, b, c, d\}, B=\{b, c, d\}, C=\{a, b, d\}, R=\{<a, b>,<c, d>,<b, b>\}$ 是 $A$ 到 $B$ 的关系, $S=\{<d, b>,<b, d>,<c, a>\}$ 是 $B$ 到 $C$ 的关系
    - 则 $R \circ S=\{<a, d>,< c, b>,<b, d>\}$



#### 用关系图和关系矩阵进行复合运算

<img src="/img-post/2021-03-22-Discrete_mathematics2/Y7g_YxLCH4EE62ykyX-YTwGy9QX-Elk4rUTgWIFu3pw.original.fullsize.png" style="zoom:50%;" />

<img src="/img-post/2021-03-22-Discrete_mathematics2/LPk1TAztbnaTTO0EE2Rr_-VLdoRgzK8QMYDHJMS1M7k.original.fullsize.png" style="zoom:50%;" />

​																										布尔积运算

- 集合表示法求复合: 找所有满足 $<x, y>\in R$ 并且 $<y, z>\in S$  的关系, 从而得到$<x, z>\in R \circ S$
- 关系图表示法求复合: 将关系 $R, S$ 的关系图画在一起，然后寻找所有首尾相接的两条有向边，再去掉中间相接的结点 $y$, 可得到 $R \circ S$ 的关系图;
- 关系矩阵表示法求复合: 直接将关系 $R$ 和 $S$ 的关系矩阵做布尔积运算即得 $R \circ S$ 的关系矩阵



#### 关系的逆运算

- 设 $A, B$ 是两个集合， $R$ 是 $A$ 到 $B$ 的关系，则从 $B$ 到 $A$ 的关系$R^{-1}=\{<b, a>\mid<a, b>\in R\}$ 称为 $R$ 的逆关系(inverse relation), 运算 ${ }^{\prime \prime-1} "$ 称为逆运算(inverse operation)。
  - 逆运算直接将关系的序偶调换顺序
  - $\left(R^{-1}\right)^{-1}=R$
  - $\varnothing^{-1}=\varnothing$
  - $(A \times B)^{-1}=B \times A$

<img src="/img-post/2021-03-22-Discrete_mathematics2/WJSdfRRI9wfg1tMV2SytVMVu1trNPwvvRpImaIdVBqU.original.fullsize.png" style="zoom:50%;" />

- 将 $R$ 的关系图中有向边的方向改变成相反方向即得 $R^{-1}$ 的关系图，反之亦然
- 将 $R$ 的关系矩阵转置即得 $R^{-1}$ 的关系矩阵，即 $R$ 和 $R^{-1}$ 的关系矩阵互为 转置矩阵;
- $R^{-1}$ 的定义域和值域正好是 $R$ 的值域和定义域，即 $d o m R=r a n R^{-1},$ $dom R^{-1}=ranR ;$
- $|F|=\left|R^{-1}\right|$



### 关系的运算定律



#### 结合律与同一律

- 设 $A, B, C$ 和 $D$ 是任意四个集合， $R, S$ 和 $T$ 分别是从 $A$ 到 $B, B$ 到 $C$ 和 $C$ 到 $D$ 的二元关 系， $I_{A}$ 和 $I_{B}$ 分别是 $A$ 和 $B$ 上的恒等关系，则
  - $(R \circ S) \circ T=R \circ(S \circ T)$
  - $I_{A} \circ R=R \circ I_{B}=R$

- 二元关系相等的证明方法
  - 目标: 证明两个关系 $R_{1}$ 和 $R_{2}$ 相等
  - 也即: 证明两个集合 $R_{1}$ 和 $R_{2}$ 相等
  - 从而: 
    - 1) $\forall<x, y>\in R_{1}, \cdots,<x, y>\in R_{2} \ldots R_{1} \subseteq R_{2}$
      2) $\forall<x, y>\in R_{2}, \cdots,<x, y>\in R_{1} \ldots R_{2} \subseteq R_{1}$



##### 结合律的证明 : $(R \circ S) \circ T=R \circ(S \circ T)$

​	任取 $<a, d>\in(R \circ S) \circ T, \quad$ 则由复合运算定义知 $,$ 存在 $c \in C,$ 使得
$<a, c>\in R \circ S$ 且 $<c, d>\in T .$
​	又因为 $<a, c>\in R \circ S,$ 所以存在 $b \in B,$ 使得 $<a, b>\in R$ 且 $<b, c>\in S .$
​	因为 $<b, c>\in S,<c, d>\in T,$ 由复合运算定义知 $,$ 有 $<b, d>\in S \circ T ;$
​	又由 $<a, b>\in R$ 且 $<b, d>\in S \circ T$ 有, $<a, d>\in R \circ(S \circ T) .$
​	从而 $(R \circ S) \circ T \subseteq R \circ(S \circ T) .$
​	**同理可证** $: R \circ(S \circ T) \subseteq(R \circ S) \circ T$
​	由以上可知, $(R \circ S) \circ T=R \circ(S \circ T) .$



##### 同一律的证明 $: I_{A} \circ R=R \circ I_{B}=R$

​	任取 $<a, b>\in I_{A} \circ R,$ 其中 $a \in A, b \in B, \quad$ 由复合运算定义可知, 存在 $a \in A,$ 使得 $<a, a>\in I_{A}$ 且 $<a, b>\in R, \quad$ 从而有 $I_{A} \circ R \subseteq R_{o}$
​	反过来，任取 $<a, b>\in R, \quad$ 由 $I_{A}$ 的定义知, $<a, a>\in I_{A},$ 即 从
​	而 $R \subseteq I_{A} \circ R_{0}$
​	由以上可知, $1_{A} \circ R=R$. 同理可证 $R \circ I_{B}=R$. 于是 $I_{A} \circ R=R \circ I_{B}=R$ 得证。



#### 分配律

- 设 $A, B, C$ 和 $D$ 是任意四个集合 $, R$ 是从 $A$ 到 $B$ 的关系, $S_{1}, S_{2}$ 是从 $B$ 到 $C$ 的关系, $T$ 是从 $C$ 到 $D$ 的关系，则
  - $R \circ\left(S_{1} \cup S_{2}\right)=\left(R \circ S_{1}\right) \cup\left(R \circ S_{2}\right)$
  - $R \circ\left(S_{1} \cap S_{2}\right) \subseteq\left(R \circ S_{1}\right) \cap\left(R \circ S_{2}\right)$
  - $\left(S_{1} \cup S_{2}\right) \circ T=\left(S_{1} \circ T\right) \cup\left(S_{2} \circ T\right)$
  - $\left(S_{1} \cap S_{2}\right) \circ T \subseteq\left(S_{1} \circ T\right) \cap\left(S_{2} \circ T\right)$

##### 证明

​	对任意 $<a, c>\in R \circ\left(S_{1} \cap S_{2}\right), \quad$ 则由复合运算定义知，存在 $b \in B,$ 使得$<a, b>\in R$ 且 $< b, c> \in S_{1} \cap S_{2}$
​	根据交运算的定义 $,<b, c>\in S_{1},$ 且 $<b, c>\in S_{2}$. 于是有 $<a, c>\in R \circ S_{1}$ 并且 $<a, c>\in R \circ S_{2},$ 即有 $<a, c>\in\left(R \circ S_{1}\right) \cap\left(R \circ S_{2}\right) .$
​	从而 $, R \circ\left(S_{1} \cap S_{2}\right) \subseteq\left(R \circ S_{1}\right) \cap\left(R \circ S_{2}\right)$



#### 逆运算性质定律

- 设 $A, B, C$ 是三个集合， $R, S$ 分别是从 $A$ 到 $B,$ 从 $B$ 到 $C$ 的关系，则
  
- $(R \circ S)^{-1}=S^{-1} \circ R^{-1}$
  
- 设 $R, S$ 是从集合 $A$ 到集合 $B$ 的关系, 则有

  - $(R \cup S)^{-1}=R^{-1} \cup S^{-1}$
    $(R \cap S)^{-1}=R^{-1} \cap S^{-1}$
    $(R-S)^{-1}=R^{-1}-S^{-1}$（分配性）
  - $(\bar{R})^{-1}=\overline{R^{-1}}$（可换性）
  - $\left(R^{-1}\right)^{-1}=R$
  - $S \subseteq R \Leftrightarrow S^{-1} \subseteq R^{-1}$（单调性）

  

##### 证明$(R \circ S)^{-1}=S^{-1} \circ R^{-1}$

​	任取 $<c, a>\in(R \circ S)^{-1},$ 则 $<a, c>\in R \circ S,$ 由复合运算定义知, 存在 $b \in B,$ 使得 $< a, b>\in R.$ 且 $<b, c>\in S . \quad$ 根据逆运算的定义, 有 $<b, a>\in R^{-1}$ 且 $<c, b>\in S^{-1} .$ 于是得 到 $<c, a>\in S^{-1} \circ R^{-1} .$ 即 $(R \circ S)^{-1} \subseteq S^{-1} \circ R^{-1}$.
​	反之, 任取 $\stackrel{\mathrm{I}}<c, a>\in S^{-1} \circ R^{-1},$ 由复合运算定义知, 存在 $b \in B,$ 使得 $<b, a>\in R^{-1}$ 且 $<c, b>\in S^{-1} .$ 又根据逆运算的定义, 有 $<a, b>\in R$ 且 $<b, c>\in S . \quad$ 从而有 $<a, c>\in R \circ S,$
​	即有 $<c, a>\in(R \circ S)^{-1},$ 故有 $S^{-1} \circ R^{-1} \subseteq(R \circ S)^{-1}$.
​	由以上可知 $,(R \circ S)^{-1}=S^{-1} \circ R^{-1} .$



### 关系的幂运算



#### 幂运算的定义

- 设 $R$ 是集合 $A$ 上的关系，则 $R$ 的 $n$ 次幕，记为 $R^{n},$ 定义如下 :
  - $R^{0}=I_{A}$
  - $R^{1}=R$
  - $R^{n+1}=R^{n} \circ R=R \circ R^{n}$
- $R^{n}$ 仍然是 $A$ 上的关系, 表示 $R$ 多次自我复合的结果;
- $R^{m+n}=R^{m} \circ R^{n}=R^{n} \circ R^{m}=R^{n+m}$
$\left(R^{m}\right)^{n}=R^{m n}, m, n \in \mathbf{N}$



#### 幂运算的性质

- $R^{n}$ 的基数并非随着 $n$ 的增加而增加，而是呈递减趋势
- 当 $n \geqslant|A|$ 时 $,$ 则 $R^{n} \subseteq \bigcup_{i=1}^{|A|} R^{i}$



设 $R=\{<1,1>,<1,2>,<2,3>,<3,4>,<4,5>,<5,6>\}$ 是定义在集合$A=\{1,2,3,4,5,6\}$ 上的关系, 考察 $R^{n}(n=1,2,3, \cdots):$

- $R^{1}=R,$
- $R^{2}=R \circ R=\{<1,1>,<1,2>,<1,3>,<2,4>,<3,5>,<4,6>\}$
- $R^{3}=R^{2} \circ R=\{<1,1>,<1,2>,<1,3>,<1,4>,<2,5>,<3,6>\}$
- $R^{4}=R^{3} \circ R=\{<1,1>,<1,2>,<1,3>,<1,4>,<1,5>,<2,6>\}$
- $R^{5}=R^{4} \circ R=\{<1,1>,<1,2>,<1,3>,<1,4>,< 1,5>,<1,6>\}$
- $R^{6}=R^{5} \circ R=\{<1,1>,<1,2>,<1,3>,<1,4>,<1,5>,<1,6>\}=R^{5}$
- $R^{7}=R^{6} \circ R=R^{5}$
- $R^{n}=R^{5}(n>5)$
  - 幂运算时，关系会趋于一种稳定的状态

设 $S=\{<1,2>,<2,3>,<3,4>,<4,5>,<5,6>\}$ 是定义在集合 $A=\{1,2,3,4,5,6\}$ 上的关系, 考察 $S^{n}(n=1,2,3, \cdots):$

- $S^{1}=S$ 
- $S^{2}=S \circ S=\{<1,3>,<2,4>,<3,5>,<4,6>\}$
- $S^{3}=S \circ S \circ S=S^{2} \circ S=\{<1,4>,<2,5>,<3,6>\}$
- $S^{4}=S^{3} \circ S=\{<1,5>,<2,6>\}$
- $S^{5}=S^{4} \circ S=\{<1,6>\}$
- $S^{6}=S^{5} \circ S=\varnothing$
- $S^{7}=\varnothing$



#### 幂运算的收敛性

- 设 $A$ 是有限集合，且 $|A|=n, R$ 是 $A$ 上的关系，则
  - $\bigcup_{i=1}^{\infty} R^{i}=\bigcup_{i=1}^{n} R^{i} .$



**证明**

​	显然有 $\bigcup_{i=1}^{n} R^{i} \subseteq \bigcup_{i=1}^{\infty} R^{i} . \quad$ 下面仅证明 $\bigcup_{i=1}^{\infty} R^{i} \subseteq \bigcup_{i=1}^{n} R^{i} $

​	因为 $\bigcup_{i=1}^{\infty} R^{i}=\left(\bigcup_{i=1}^{n} R^{i}\right) \cup\left(\bigcup_{i=n+1}^{\infty} R^{i}\right),$ 所以只要证明 $\forall k>n, R^{k} \subseteq \bigcup_{i=1}^{n} R^{i}$ 即可

​	对任意 $<a, b>\in R^{k},$ 由复合运算定义可知，存在 $a_{1}, a_{2}, a_{3}, \cdots, a_{k-1} \in A,$ 使得
$<a, a_{1}>\in R,<a_{1}, a_{2}>\in R,<a_{2}, a_{3}>\in R, \ldots,<a_{k-1}, b>\in R$	

​	由于 $|A|=n,$ 且 $k>n,$ 根据鸽笼原理可知, $k+1$ 个元素 $a=a_{0}, a_{1}, a_{2}, \cdots, a_{k-1}, a_{k}=b$ 中 有两个元素相同

​	不妨假设 $a_{i}=a_{j}(i<j)$, 则可在上式中删去

​	$$<a_{i}, a_{i+1}>\in R,<a_{i+1}, a_{i+2}>\in R,<a_{i+2}, a_{i+3}>\in R, \cdots,<a_{j-1}, a_{j}>\in R$$

​	后仍有
$$
<a_{0}, a_{1}>\in R, \cdots,<a_{i-1}, a_{i}>\in R,<a_{j}, a_{j+1}>\in R, \ldots,<a_{k-1}, a_{k}>\in R
$$
​	由复合运算得 $<a, b>=<a_{0}, a_{k}>\in R^{k^{\prime}},$ 其中 $k^{\prime}=k-(j-i) .$ 此时:

​	若 $k^{\prime} \leqslant n,$ 则 $<a, b>\in \bigcup_{i=1}^{n} R^{i}$

​	若 $k^{\prime}>n,$ 则重复上述做法，最终总能找到 $k^{\prime \prime} \leqslant n,$ 使得 $<a, b>=<a_{0}, a_{k}>\in R^{k^{\prime \prime}}$

​	即有 $<a, b>\in \bigcup_{i=1}^{n} R^{i} .$ 于是得到 $R^{k} \subseteq \bigcup_{i=1}^{n} R^{i}$.




### 关系的性质



#### 自反性和反自反性

- 设 $R$ 是集合 $A$ 上的关系
  - 如果对任意的 $x \in A,$ 都有 $<x, x>\in R,$ 那么称 $R$ 在 $A$ 上是**自反的(reflexive)**, 或称 $R$ 具有**自反性(reflexivity)**
    - 同姓关系，小于等于关系，包含关系，整除关系，相等关系，同余关系都是自反的关系
  - 如果对任意的 $x \in A,$ 都有 $<x, x>\notin R,$ 那么称 $R$ 在 $A$ 上是**反自反的(antireflexive)**, 或称 $R$ 具有**反自反性(antireflexivity)**
    - 父子关系，小于关系，真包含关系都是反自反的关系

- 存在既不是自反的也不是反自反的关系
- 关系 $R$ 是自反的当且仅当 $R$ 的关系图中每个结点内**都有自环**，关系 $R$ 是反自反的当且仅当 $R$ 的关系图中每个结点**都无自环**
- 关系 $R$ 是自反的当且仅当 $R$ 的**关系矩阵的主对角线上全为 1** ，关系 $R$ 是反自反的当且仅当 $R$ 的**关系矩阵的主对角线上全为 0**



设 $A=\{1,2,3\},$ 定义 $A$ 上的关系 $R, S$ 和 $T$ 如下:

- $R=\{<1,1>,<1,2>,<2,2>,<3,3>\}$ ——自反
- $S=\{<1,2>,<2,3>,<3,1>\}$——反自反
- $T=\{<1,1>,<1,2>,<1,3>,<3,1>,< 3,3>\}$——非自反，非反自反

![](/img-post/2021-03-22-Discrete_mathematics2/td5FNmgXq8IPl08jrbJpFdzjLYT_771q7CkycQcv3LU.original.fullsize.png)

- 自反要求全部的元素都有自环，反自反要求远不的元素都没有自环

$M_{R}=\left(\begin{array}{lll}1 & 1 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1\end{array}\right) \quad M_{S}=\left(\begin{array}{lll}0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 0 & 0\end{array}\right) \quad M_{T}=\left(\begin{array}{lll}1 & 1 & 1 \\ 0 & 0 & 0 \\ 1 & 0 & 1\end{array}\right)$



#### 对称性与反对称性

- 设 $R$ 是集合 $A$ 上的关系
  - 如果对任意的 $x, y \in A,$ 如果 $<x, y>\in R,$ 那么 $<y, x>\in R,$ 则称 $R$ 是**对称的(symmetric)**, 或称 $R$ 具有**对称性(symmetry)**
    - 同姓关系，相等关系，朋友关系，同余关系都是对称的关系
  - 如果对任意的 $x, y \in A,$ 如果 $<x, y>\in R$ 且 $<y, x>\in R,$ 那么 $x=y,$ 则称 $R$ 是**反对称的(antisymmetric)**, 或称 $R$ 具有**反对称性(antisymmetry)**
    - 父子关系，小于关系，相等关系，小于等于关系，包含关系，整除关系都是反对称的关系
- 存在既不是对称的也不是反对称的关系，也存在既是对称又是反对称的关系
  - 相关关系既对称，也反对称
  - 自反序偶不会破坏对称性，也不会破坏反对称性



设 $A=\{1,2,3\},$ 定义 $A$ 上的关系 $R, S,T$ 和 $V$ 如下：

- $R=\{<1,1>,<1,3>,<3,1>,<4,4>\}$——对称
- $S=\{<1,1>,<1,3>,<1,4>,<2,4>\}$——反对称
- $T=\{<1, 1>,<1,2>,<1,3>,<3,1>,<1,4>\}$——非对称，非反对称
- $V=\{<1, 1>,<2,2>,<3,3>,<4,4>\}$——既对称，又反对称

![](/img-post/2021-03-22-Discrete_mathematics2/2dNL2i6t6zGvrg9rUSy76YKDH1FqMBeWmiV_mNYScnI.original.fullsize.png)

- 关系图判定法 : 
  - 关系 $R$ 是对称的当且仅当 $R$ 的关系图中, 任何一对结点之间, 要么有方向相反的两条边, 要么无边
  - 关系 $R$ 是反对称的当且仅当 $R$ 的关系图中, 任何一对结点之间至多只有一条边

$M_{R}=\left(\begin{array}{cccc}1 & 0 & 1 & 0 \\ 0 & 0 & 0 & 0 \\ 1 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1\end{array}\right) \quad M_{S}=\left(\begin{array}{cccc}1 & 0 & 1 & 1 \\ 0 & 0 & 0 & 1 \\ 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0\end{array}\right) \quad M_{V}=\left(\begin{array}{cccc}1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1\end{array}\right)$

- 关系矩阵判定法：关系 $R$ 是对称的当且仅当 $R$ 的关系矩阵 $\left(r_{i j}\right)_{n \times n}$ 为对称矩阵, 关系 $R$ 是反对称的当且仅当 $R$ 的关系矩阵 $\left(r_{i j}\right)_{n \times n}$ 满足 $i \neq j$ 时, $r_{i j}=0$ 或 $r_{j i}=0$
  - 反对称时连线两边不能同时为 1 

<img src="/img-post/2021-03-22-Discrete_mathematics2/8oqAwYh2aTI82VI_GDznoueIVzrMJPhgIHytcBoLu84.original.fullsize.png" style="zoom:50%;" />



#### 传递性

- 设 $R$ 是集合 $A$ 上的关系. 对任意的 $x, y, z \in A,$ 如果 $<x, y>\in R$ 且 $<y, z>\in R,$ 那么 $<x, z>\in R,$ 则称 $R$ 是**传递的(transitive)**, 或称 $R$ 具有**传递性(transitivity)**
  - 同姓关系，小于等于，相等关系，小于关系，包含关系，整除关系，飞机航线的可到达关系都是传递的关系
  - 父子关系，朋友关系，婚姻关系，飞机航线的直达关系都不是传递的关系



设 $A=\{1,2,3\},$ 定义 $A$ 上的关系 $R, S, T$ 和 $V$ 如下:

- $R=\{<1,1>,<1,2>,<2,3>,<1,3>\}$——传递
- $S=\{<1,2>\}$——传递
  -  $<x, y>\in R$ $ \wedge <y, z>\in R \rightarrow$  $<x, z>\in R$
  -  $<y,z>\in R$为假，故前件为假，故蕴含式必然为真
  -  传递是自然成立的
  -   $R \circ R \subseteq R$
- $T=\{<1,1>,<1,2>,<2,3>\}$——非传递​
- $V=\{<1,2>,<2,3>,<1,3>,<2,1>\}$——非传递

![](/img-post/2021-03-22-Discrete_mathematics2/_cw7eLW9Xg3aFTSzlv5Nw7GR4TGGGflCtk3_q80RaUA.original.fullsize.png)

- 找到两个序偶应该传递但是没有传递



$M_{R}=\left(\begin{array}{lll}1 & 1 & 1 \\ 0 & 0 & 1 \\ 0 & 0 & 0\end{array}\right), M_{S}=\left(\begin{array}{lll}0 & 1 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{array}\right), M_{T}=\left(\begin{array}{lll}1 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0\end{array}\right), M_{V}=\left(\begin{array}{lll}0 & 1 & 1 \\ 1 & 0 & 1 \\ 0 & 0 & 0\end{array}\right)$

- 关系 $R$ 是传递的当且仅当在 $R$ 的关系图中, 任何三个不同结点 $x, y, z$ 之间, 若从 $x$ 到 $y$ 有一条边存在, 从 $y$ 到 $z$ 有一条边存在, 则从 $x$ 到 $z$ 一定有一条边存在;
- 关系 $R$ 是传递的当且仅当在 $R$ 的关系矩阵中, 对任意 $i, j, k \in\{1,2, \cdots, n\},$ 若 $r_{i j}=1$ 且 $r_{j k}=1,$ 必有 $r_{i k}=1 .$



#### 关系性质的判定定理

- 对具体集合上的具体关系，我们可根据关系图和关系矩阵等方法来判定关系的性质，但对于抽象集合上的抽象关系，则存在一定的局限性。为此，我们从集合运算的观点，给出相应的判定定理

- 设 $R$ 是集合 $A$ 上的关系，则

  - $R$ 是自反的 $\Leftrightarrow I_{A} \subseteq R$
  - $R$ 是反自反的 $\Leftrightarrow R \cap I_{A}=\varnothing$
  - $R$ 是对称的 $\Leftrightarrow R=R^{-1}$
  - $R$ 是反对称的 $\Leftrightarrow R \cap R^{-1} \subseteq I_{A}$
  - $R$ 是传递的 $\Leftrightarrow R \circ R \subseteq R$

  

##### 判定定理的证明

证明：$R$ 是对称的 $\Leftrightarrow R=R^{-1}$
	

​	**先证必要性**：对任意 $<a, b>\in R,$ 由于 $R$ 是对称的 $,$ 所以 $<b, a>\in R,$ 即 $<a, b>\in R^{-1}$ ，从而 $R \subseteq R^{-1} ;$

​	反过来，若任意 $<a, b>\in R^{-1},$ 则有 $<b, a>\in R,$ 由于 $\mathrm{R}$ 的对称性，得到 $<a, b>\in R,$ 从而 $R^{-1} \subseteq R_{\circ}$ 即有 $R=R^{-1}$ 

​	再证充分性：对任意 $a, b \in A,$ 若 $<a, b>\in R,$ 由于 $R=R^{-1}$,
则有 $<a, b>\in R^{-1},$ 即 $<b, a>\in R$。 由对称性的定义可知, $R$ 是对称的

  

证明：$R$ 是传递的 $\Leftrightarrow R \circ R \subseteq R$



​	**先证必要性**: 对任意 $<a, c>\in R \circ R,$ 根据复合运算定义, 则必存在 $b \in A,$ 使得 $<a, b>\in R$ 并且 $<b, c>\in R_{\circ}$ 由于 $R$ 是传递的 $,$ 因此有 $<a, c>\in R,$ 即 $R \circ R \subseteq R$

​	**再证充分性**: 对任意 $a, b, c \in A,$ 若 $<a, b>\in R$ 并且 $<b, c>\in R,$ 则有 $<a, c>\in R \circ R_{\circ}$ 因为 $R \circ R \subseteq R,$ 所以 $<a, c>\in R,$ 即 $R$ 是传递的



##### 总结：关系性质的判定方法

![](/img-post/2021-03-22-Discrete_mathematics2/OD0KczuipvHzz2IhX7aSxXSxkohfaia2oKOY-ePDKoE.original.fullsize.png)



#### 关系性质判定

一个关系可能满足多种性质，如

- 非空集合 $A$ 上的全关系 $E_{A} $        自反、对称 (前件为0)、传递
- 非空集合 $A$ 上的空关系 $\varnothing$          反自反、对称 （前件为0）、反对称、传递
- 非空集合 $A$ 上的恒等关系 $I_{A}$     自反、对称、反对称、传递
- 实数集 $R$ 上的等于关系 $=$          自反、对称、反对称、传递
- 幕集上的真包含关系 $\subset$               反自反、反对称、传递



假设 $A=\{a, b, c, d\}, R$ 是定义在 $A$ 上的关系. $R=\{<a, a>,<a, b>,<b, a>,<c, d>\}$

- 非自反, 非反自反, 非对称, 非反对称, 非传递



#### 关系性质的保守性

设 $R,S$ 是集合 $A$ 上的关系，则

- $R, S$ 是**自反的**, 则 $R^{-1}, R \cup S, R \cap S, R \circ S$ 也是自反的
- $R, S$ 是反自反的, 则 $R^{-1}, R \cup S, R \cap S, R-S$ 也是反自反的
- $R, S$ **是对称**的, 则 $R^{-1}, R \cup S, R \cap S, R-S，\sim R$ 也是对称的
- $R, S$ 是反对称的, 则 $R^{-1}, R \cap S, R-S$ 也是反对称的
- $R, S$ 是**传递的**, 则 $R^{-1}, R \cap S$ 也是传递的
  - 逆运算和交运算一定能保持关系的特性



- 设 $A=\{1,2,3\}, R, S$ 是集合 $A$ 上的关系
  -  $R=\{<1,2>,<2,3>,<1,3>\}$,反自反, 反对称, 传递
  - $S=\{<3,2>,<3,1>,<2,1>\}$.反自反, 反对称, 传递
    - 但 $R \circ S=\{<1,1>,<2,2>,<2,1>,<1,2>\}$,非反自反, 非反对称
    - $R \cup S=\{<1,2>,<2,3>,<1,3>,<2,1>,<3,2>,<3,1>\}$,非传递, 非反对称;
  - $R=\{<1,1>,<2,2>,<3,3>,<1,2>,<2,1>\}$,自反, 对称, 传递
  - $S=\{<1,1>,<2,2>,<3,3>,<3,2>,<2,3>\}$.自反, 对称, 传递
    - 但 $R \circ S=\{<1,1>,<2,2>,<3,3>,<2,3>,<3,2>,<1,2>,<2,1>,<1,3>\}$,非传递, 非对称
    - $R - S=\{<1,2>,<2,1>\}$,非自反, 非传递.



### 关系的闭包

​	一个关系可能不具备某一特殊性质。但是，如果希望它有我们希望它具备的某一个性质，应该如何操作呢？

​	我们可以通过添加一些元素, 使得关系具备我们想要的性质。例如，对给定集合 $A=\{1,2,3\}$ 上的关系 $R=\{<1,1>,<1,2>,<2,1>\},$ 它不具有自反性。根据自 反性的定义，在关系 $R$ 中添加 $<2,2>,<3,3>$ 这两个元素后, 所得到的新关系 $R^{\prime}$ 就具 有自反性。 另外, 还可以添加 $<2,2><3,3><1,3>,$ 得到的新关系 $R^{\prime \prime}$ 仍然具有 自反性

​	如何在给定关系中添加最少的元素，使其具有需要的特殊性质，这就是关系的闭包问题

​	反自反性、反对称性需要通过删除特定元素得到，在这里我们并不讨论



#### 闭包定义

- 设 $R$ 是集合 $A$ 上的关系, 若存在 $\mathrm{A}$ 上的另一个关系 $R^{\prime},$ 满足：
  - $R^{\prime}$ 是**自反**的 (**对称**的, 或**传递**的)
  - 对任何自反的 $($ 对称的, 或传递的 $)$ 关系 $R^{\prime \prime}$,如果 $R \subseteq R^{\prime \prime},$ 就有 $R^{\prime} \subseteq R^{\prime \prime},$ 则称 $R^{\prime}$ 为 $\mathrm{R}$ 的自反闭包(reflexive closure) (对称闭包(symmetric closure), 或传递闭包(transitive closure)), 分别记为 $r(R)(s(R)$ 或 $t(R))$.

- 设定义在整数集 $Z$ 上的“ $<$ "关系为 $R,$ 则 $r(R)=“ \leqslant ”, s(R)=“ \neq ", t(R)=“<"$
- 设定义在整数集 $Z$ 上的“恒等"关系为 $S,$ 则 $r(S)=“=", s(S)=“=", t(S)=“="$



#### 利用直接观察和关系图法闭包

设集合 $A=\{1,2,3,4\}, R=\{<1,2>,<2,2>,<2,3>,<3,4>\}$ 是定义在 $A$ 上的二元关系，则

- $r(R)=\{<1,2>,<2,2>,<2,3>,<3,4>,<1,1>,<3,3>,<4,4>\}$
- $s(R)=\{<1,2>,<2,2>,<2,3>,<3,4>,<2,1>,<3,2>,<4,3>\}$
- $t(R)=\{<1,2>,<2,2>,<2,3>,<3,4>,<1,3>,<1,4>,<2,4>\}$

直接观察可以得到

![](/img-post/2021-03-22-Discrete_mathematics2/Wq-qdWD6K8OvskRtxnMlQxSiHc1983OWV-H-mMVsAgU.original.fullsize.png)

- 检查 $R$ 的关系图，在没有自环的结点处加上自环，可得 $r(R)$ 的关系图
- 检查 $R$ 的关系图，将每条单向边全部改成双向边，可得 $s(R)$ 的关系图
- 检查 $R$ 的关系图，从每个结点出发，找到其终点，如果该结点到其终点没 有边相连，就加上此边，可得 $t(R)$ 的关系图



#### 利用关系运算求闭包

设 $R$ 是集合 $A$ 上的关系, 则

- $r(R)=R \cup I_{A}$
- $s(R)=R \cup R^{-1} $
- $t(R)=\bigcup_{i=1}^{\infty} R^{i},$ 若 $|A|=n,$ 则 $t(R)=\bigcup_{i=1}^{n} R^{i}$





设 $P=\left\{P_{1}, P_{2}, P_{3}, P_{4}\right\}$ 是四个程序 $, R=\left\{<P_{1}, P_{2}\right>,\left< P_{1}, P_{3}>,\left< P_{2}, P_{4}>,<P_{3}, P_{4}>\right\}\right.$ 是
定义在 $P$ 上的调用关系, 则 $R$ 的闭包为:

$r(R)=R \cup I_{A}$

$=\left\{< P_{1}, P_{2}>,< P_{1}, P_{3}>,< P_{2}, P_{4}>< P_{3}, P_{4}>\right\} \cup\left\{<P_{1}, P_{1}>,<P_{2}, P_{2}>,< P_{3}, P_{3}>,<P_{4}, P_{4}>\right\}$
$=\left\{< P_{1}, P_{2}>,< P_{1}, P_{3}>,< P_{2}, P_{4}>,<P_{3}, P_{4}>,<P_{1}, P_{1}>,< P_{2}, P_{2}>,< P_{3}, P_{3}>,<P_{4}, P_{4}>\right\}$



$s(R)=R \cup R^{-1}$
$=\left\{<P_{1}, P_{2}>,<P_{1}, P_{3}>,<P_{2}, P_{4}>,<P_{3}, P_{4}>\right\} \cup\left\{<P_{2}, P_{1}>,<P_{3}, P_{1}>,<P_{4}, P_{2}>,<P_{4}, P_{3}>\right\}$
$=\left\{<P_{1}, P_{2}>,<P_{1}, P_{3}>,<P_{2}, P_{4}>,<P_{3}, P_{4}>,<P_{2}, P_{1}>,<P_{3}, P_{1}>,<P_{4}, P_{2}>,<P_{4}, P_{3}>\right\}$



$t(R)=R \cup R^{2} \cup R^{3} \cup R^{4}$
$=\left\{<P_{1}, P_{2}>,<P_{1}, P_{3}>,<P_{2}, P_{4}>,<P_{3}, P_{4}>\right\} \cup\left\{<P_{1}, P_{4}>\right\}\cup \varnothing \cup \varnothing$
$=\left\{<P_{1}, P_{2}>,<P_{1}, P_{3}>,<P_{2}, P_{4}>,<P_{3}, P_{4}>,<P_{1}, P_{4}>\right\}$





## 特殊关系



### 等价关系

- 设 $R$ 是非空集合 $A$ 上的关系, 如果 $R$ 是**自反的、对称的、传递的**，则称 $R$ 为 $A$ 上的等价关系(equivalent relation)
  - 同姓关系，等于关系都是等价关系
  - 而朋友关系，包含关系都不是等价关系
  - 在所有的英文单词中建立关系 $R, a R b$ 当且仅当 $a$ 和 $b$ 的长度相同, 则关系 $R$ 是等价关系
  - 在包含各种颜色的球的集合中建立关系 $S, a S b$ 当且仅当 $a$ 和 $b$ 的颜色相同, 则关系 $S$ 是等 价关系.

在集合 $A=\{0,1,2,4,5,8,9\}$ 上定义一个以 4 为模的同余关系, 即 $R=\{<x, y>|4|(x-y)\}$

- $R=\{<0,0>,<0,4>,<0,8>,<4,4>,<4,0>,<4,8>,<8,8>,$

  $<8,0>,<8,4>,<1,1>,<1,5>,<1,9>,<5,5>,<5,1>,<5,9>,$

  $<9,9>,<9,1>,<9,5>,<2,2>\}$

  则 $R$ 满足自反, 对称, 传递的性质, 从而 $R$ 是等价关系

- 集合 $\mathrm{A}$ 被分成三个子集: $\{0,4,8\},\{1,5,9\},\{2\} ;$
- 每个子集内的元素都具有与 $\mathrm{R}$ 相关的共同性质: 0,4,8 除以 4 的余数都是 0 , 而 $1,5,9$ 除以 4 的余数都是 1 , 同时 2 除以 4 的余数是 2
	
	- 此例子可以推广到整数集上的以 $n$ 为模的同余关系.



#### 以 n 为模的同余关系

- 设 $n$ 为正整数，定义整数集合 $\mathrm{Z}$ 上的以 $\mathrm{n}$ 为模的同余关系 $R=\{<\mathrm{x}, y>|n|(x-y)\}$, 证明 $R$ 是一个等价关系
  - 自反性: 对任意 $x \in \mathbf{Z}$, 有 $n \mid(x-x)$, 所以 $<x, x>\in R$, 即 $R$ 是自反的
  - 对称性: 对任意 $x, y \in \mathbf{Z}$, 若 $<x, y>\in R$, 则有 $n \mid(x-y)$, 因为 $(y-x)=-(x-y)$, 所以 $n \mid(y-x)$, 从而 $<y, x>\in R$, 即 $R$ 是对称的
  - 传递性: 对任意 $x, y, z \in \mathbf{Z}$, 若 $<x, y>\in R$ 且 $<y, z>\in R$, 则有 $n \mid(x-y)$ 且 $n \mid(y-z)$ 。因 为 $(x-z)=(x-y)+(y-z) $ 所以 $n \mid(x-z)$, 从而 $< x, z>\in R$, 即 $R$ 是传递的
  - 综上所述，$R$ 是 $\mathrm{Z}$ 上的等价关系




- 在 $\mathbf{Z}$ 上以 $n$ 为模的同余关系 $R$ 中, 一般记 $x R y$ 为 $x \equiv y(\bmod n)($ 即同余式 $)$
  或 $\operatorname{Res}_{n}(x)=\operatorname{Res}_{n}(y) .$ 其中, $\operatorname{Res}_{n}(x)$ 表示 $x$ 除以 $n$ 的余数;
  
  - 在此关系下, 整数集 $ \mathbf{Z}$ 被分成了 $n$ 个子集:
    $\{\cdots,-3 n,-2 n,-n, 0, n, 2 n, 3 n, \cdots\}$
    $\{\cdots,-3 n+1,-2 n+1,-n+1,1, n+1,2 n+1,3 n+1, \cdots\} ;$
    $\{\cdots,-3 n+2,-2 n+2,-n+2,2, n+2,2 n+2,3 n+2, \cdots\}$
    :
    $\{\cdots,-2 n-1,-n-1,-1, n-1,2 n-1,3 n-1,4 n-1, \cdots\} .$
  - 这些子集称作由 $R$ 产生的等价类



#### 等价类

- 设 $R$ 是非空集合 $A$ 上的等价关系，对任意 $x \in A$, 称集合 $[x]_{R}=\{y \mid y \in A,<x, y>\in R\}$ 为 $x$ 关于 $R$ 的等价类(equivalence class)，或叫作由 $x$ 生成的一个 $R$ 等价类, 其中 $x$称为 $[x]_{R}$ 的生成元(代表元或典型元) (generator).



在集合 $A=\{0,1,2,4,5,8,9\}$ 上定义的以 4 为模的同余关系中,

- $[0]_{R}=[4]_{R}=[8]_{R}=\{0,4,8\} $
- $[1]_{R}=[5]_{R}=[9]_{R}=\{1,5,9\}$
- $[2]_{R}=\{2\}$



#### 等价类的性质

设 $R$ 是非空集合 $A$ 上的等价关系，则
- 对任意 $x \in A,[x]_{R} \neq \varnothing$;
- 对任意 $x, y \in A$, 如果 $y \in[x]_{R}$, 则有 $[x]_{R}=[y]_{R}$, 否则 $[x]_{R} \cap[y]_{R}=\varnothing$;
- $\bigcup_{x \in A}[x]_{R}=A$.



- 第一条的证明：

  对 $\forall x \in A$, 因为 $R$ 是等价关系，所以 $R$ 是自反的, 从而 $<x, x>\in R$, 即 $x \in[x]_{R}$, 故 $[x]_{R} \neq \varnothing$

- 第二条的证明：

  $\forall x, y \in A$,
  a) 若 $y \in[x]_{R}$, 则 $<x, y>\in R .$ 对任意 $z \in[x]_{R}$, 则有 $<x, z>\in R .$ 因为 $\mathrm{R}$ 是等价关系, 所以 $R$ 对具有对称性和传递性. 由 $R$ 的对称性有 $<y, x>\in R$, 由 $R$ 的传递性有 $<y, z>\in R .$ 所 以 $z \in[y]_{R}$, 即 $[x]_{R} \subseteq[y]_{R} .$ 同理可证, $[y]_{R} \subseteq[x]_{R}$ 从而, 有 $[x]_{R}=[y]_{R}$;
  b) 若 $y \notin[x]_{R}$, 设 $[x]_{R} \cap[y]_{R} \neq \varnothing$, 则存在 $z \in[x]_{R} \cap[y]_{R}$, 即 $z \in[x]_{R}, z \in[y]_{R}$, 因此有
  $< x, z>\in R,<y, z>\in R .$ 由 $R$ 的对称性有 $<z, y>\in R$, 由 $R$ 的传递性有 $<x, y>\in R$, 所 以 $y \in[x]_{R}$, 与假设 $y \notin[x]_{R}$ 矛盾. 从而, 有 $[x]_{R} \cap[y]_{R}=\varnothing ;$

- 第三条的证明：

  对任意 $x \in A,[x]_{R} \subseteq A$, 所以 $\bigcup_{x \in A}[x]_{R} \subseteq A ;$ 又对任意 $x \in A$, 因 $R$ 是自反的, 所以
  $<x, x>\in R$, 即 $x \in[x]_{R .}$ 所以 $x \in \bigcup_{x \in A}[x]_{R}$, 即 $A \subseteq \bigcup_{x \in A}[x]_{R .}$ 故 $\bigcup_{x \in A}[x]_{R}=A .$



#### 商集

- 设 $R$ 是非空集合 $A$ 上的等价关系，由 $R$ 确定的一切等价类的集合，称为集合 $A$ 上关于 $R$ 的商集(quotient set)，记为 $A / R$, 即 $A / R=\left\{[x]_{R} \mid x \in A\right\}$.



设集合 $A=\{0,1,2,4,5,8,9\}$, 则

- 在 $A$ 上定义的以 4 为模的同余关系 $R$ 中,
  $A / R=\left\{[0]_{R},[1]_{R},[2]_{R}\right\}=\{\{0,4,8\},\{1,5,9\},\{2\}\} ;$
- 在 $A$ 上定义的以 3 为模的同余关系 $S$ 中, $A / S=\left\{[0]_{s},[1]_{S},[2]_{s}\right\}=\{\{0,9\},\{1,4\},\{2,5,8\}\} .$



- 计算商集的通用过程
  - 任选 $A$ 中一个元素 a，计算 $[a]_{R} $
  - 如果 $[a]_{R} \neq A$, 任选一个元素 $b \in A-[a]_{R}$, 计算 $[b]_{R} $
  - 如果 $[a]_{R} \cup[b]_{R} \neq A$, 任选一个元素 $c \in A-[a]_{R}-[b]_{R}$, 计算 $[c]_{R}$
  - 以此类推，直到 $A$ 中所有元素都包含在计算出的等价类中



### 集合的划分



#### 定义

​	在等价关系中我们已经发现，同一个等价类中的元素具有相同的属性，因而可将集合中的元素分成不同的类别，对应于集合的划分

- 给定一个非空集合 $A$, 设有集合 $\pi=\left\{S_{1}, S_{2}, \cdots, S_{m}\right\}_{0}$ 如果满足:
  - $S_{i} \subseteq A, S_{i} \neq \varnothing, i=1,2, \cdots, m $
  - $S_{i} \cap S_{j}=\varnothing, \ddot{y} \neq j, i, j=1,2, \cdots, m $
  - $\bigcup_{i-1}^{m} S_{i}=A$
  - 则集合 $\pi$ 称作集合 $A$ 的一个划分 (partition), 而 $S_{1}, S_{2}, \cdots, S_{m}$ 叫做这个划分的块 (block) 或类 (class)



#### 等价划分

- 设 $R$ 是非空集合 $A$ 上的等价关系，则 $A$ 对 $R$ 的商集 $A / R$ 是 $A$ 的一个划分，称为由 $R$ 所导出 的等价划分
- 同一个集合有多种不同的划分，不同的等价关系导出不同的划分
- 给定集合 $A$ 的一个划分 $\pi=\left\{S_{1}, S_{2}, \cdots, S_{m}\right\}$, 则由该划分确定的关系 $R=\left(S_{1} \times S_{1}\right) \cup\left(S_{2} \times S_{2}\right) \cup \cdots \cup\left(S_{m} \times S_{m}\right)$ 是 $A$ 上的等价关系。我们称该关系 $R$ 为由划分 $\pi$ 所导出的等价关系。



设集合 $A=\{0,1,2,4,5,8,9\}$, 则

- $A$ 上以 4 为模的同余关系 $R$ 导出的划分为,
  $A / R=\left\{[0]_{R},[1]_{R},[2]_{R}\right\}=\{\{0,4,8\},\{1,5,9\},\{2\}\}$
- $A$ 上以 3 为模的同余关系 $S$ 导出的划分为,
  $A / S=\left\{[0]_{s},[1]_{s},[2]_{s}\right\}=\{\{0,9\},\{1,4\},\{2,5,8\}\}$



设 $A=\{a, b, c, d, e, f\}, \pi=\{\{a, b\},\{c, e, f\},\{d\}\}$ 是 $A$ 的一个划分, 则 $\pi$ 对应的等价关系 $R$ 为:

$R=(\{a, b\} \times\{a, b\}) \cup(\{c, e, f\} \times\{c, e, f\}) \cup(\{d\} \times\{d\})$

$=\{<a, a>,< b, b>,<a, b>,<b, a>\}$
$\cup\{<c, c>,<e, e>,<f, f>,<c, e>,<e, c>,<c, f\>,<f, c>$
$<e, f>,<f, e>\} \cup\{<d, d>\}$

$\begin{aligned}=&\{<a, a>,<b, b>,<a, b>,<b, a>,<c, c>,<e, e>,<f, f\> \\ &<c, e>,<e, c>,< c, f>,< f, c>,<e, f>,< f, e>,< d, d>\} \end{aligned}$



###  偏序关系的定义



### 哈斯图和特殊元素





## 函数



### 函数的定义



#### 函数的基本定义



- 设 $f$ 是集合 $A$ 到 $B$ 的关系， 如果对每个 $，x \in A$ 都存在惟一的 $，y \in B$ 使得 $<x, y>\in f$ 则称关 系 $f$ 为 $A$ 到 $B$ 的函数或映射，记为 $f: A \rightarrow B $
  - $ A$ 为函数 $f$ 的定义域,，记为 $d o m f=A $；$ f(A)$ 为 函数 $f$ 的值域, 记为 $ranf$
  - 当 $<x, y>\in f$ 时，通常记为 $y=f(x)，$ 这时称 $x$ 为函数 $f$ 的自变量 (或原像)， $y$ 为 $x$ 在 $f$ 下的函数值 (或像)
  -  注意区分 $f$ 和 $f(x)$, 二者是不同的
    - 后者不是一个关系或函数，$y=f(x)$ 才是



- 如果关系 $f$ 具备下列两种情况之一，那么 $f$ 就不是函数：
  - 存在元素 $a \in A$, 在 $B$ 中**没有像** 
  - 存在元素 $a \in A$, **有两个及两个以上的像**



设 $A=\{1,2,3,4\}, B=\{a, b, c, d\}$, 则.
- $\left.f_{1}=\{<1, a>,<2, a>,<3, d>,<4, c>\right\} ;$ 函数
- $\left.f_{2}=\{<1, a>,<2, a>,<2, d>,<4, c>\right\} ;$ 非函数
- $\left.f_{3}=\{<1, a>,<2, b>,< 3, d>,<4, c>\right\} ;$ 函数
- $\left.f_{4}=\{<2, b>,<3, d>,<4, c>\right\} .$ 非函数



#### 函数的数量

- 设函数 $f: A \rightarrow B,|A|=m,|B|=n$, 对 $A$ 中的每个元素而言, 其序偶的第二元素都 有 $n$ 种可能的选择, 因而总共有 $n^{m}$ 种选法, 也就是有 $n^{m}$ 个不同的函数



设 $A=\{a, b, c\}, B=\{1,2\}$, 则 $A$ 到 $B$ 的所有不同函数有: $2^3=8$ 种



#### 关系和函数的差别

- 当 $A$ 和 $B$ 都是有限集合时, 函数和一般关系具有如下差别:
  - 关系和函数的数量不同: 从 $A$ 到 $B$ 的不同关系有 $2^{|A| \times|B|}$ 个, 从 $A$ 到 $B$ 的 不同函数却仅有 $|B|^{|A|}$ 个;
  - 关系和函数的基数不同: 每一个关系的基数可以从零一直到 $|A| \times|B|$, 每一 个函数的基数都为 $|A|$ 个;
  - 关系和函数的第一元素存在差别: 关系的第一个元素可以相同, 函数的第 元素一定是互不相同的



### 函数的类型



#### 类型

- 设 $f$ 是从集合 $A$ 到 $B$ 的函数
  - 对任意 $x_{1}, x_{2} \in A$, 如果 $x_{1} \neq x_{2}$, 都有 $f\left(x_{1}\right) \neq f\left(x_{2}\right)$, 则称 $f$ 为从 $A$ 到 $B$ 的单射;

  - 如果 $\operatorname{ranf}=B$, 则称 $f$ 为从 $A$ 到 $B$ 的满射（值域等于 $B$）

  - 如果 $f$ 既是单射又是满射, 则称 $f$ 为从 $A$ 到 $B$ 的双射

    

- 设 $A=\{1,2,3,4,5\}, B=\{a, b, c, d\} $
	
	- $ f: A \rightarrow B$ 定义为:$\{< 1, a>,< 2, c>,< 3, b>,<4, a>,<5, d>\} ;$ 满射
- 设 $A=\{1,2,3\}, B=\{a, b, c, d\} $
	
	- $ f: A \rightarrow B$ 定义为: $f=\{<1, a>,< 2, c>,<3, b>\} ;$ 单射
- 设 $A=\{1,2,3\}, B=\{a, b, c\} $
	
	- $ f: A \rightarrow B$ 定义为: $f=\{<1, b>,< 2, c>,<3, a>\}$双射





#### 必要条件

- 若 $f$ 是从有限集 $A$ 到有限集 $B$ 的函数，
则有
	- $f$ 是单射的必要条件为 $|A| \leqslant|B|$
	- $f$ 是满射的必要条件为 $|A| \geqslant|B|$
	- $f$ 是双射的必要条件为 $|A|=|B|$



#### 数学化描述

- $f: A \rightarrow B$ 是单射当且仅当对 $\forall x_{1}, x_{2} \in A$, 若 $x_{1} \neq x_{2}$, 则 $f\left(x_{1}\right) \neq f\left(x_{2}\right)$
- $f$ : $A \rightarrow B$ 是满射当且仅当对 $\forall y \in B$, 一定存在 $x \in A$, 使得 $f(x)=y$
- $f: A \rightarrow B$ 是双射当且仅当满足以上两点



- 设 $A=B=\mathbf{R}$, 试判断下列函数的类型。
  - $f_{1}=\left\{< x, x^{2}>| x \in \mathbf{R}\right\} $一般函数 
  - $f_{2}=\{<x, x+1>\mid x \in \mathbf{R}\} $ 双射
  - $f_{3}=\left\{< x, e^{x}>| x \in \mathbf{R}\right\}$ 单射



#### 证明



##### 典型(自然)映射

设 $R$ 是集合 $A$ 上的一个等价关系, $g: A \rightarrow A / R$ 称为 $A$ 对商集 $A / R$ 的典型 $($自然) 映射, 其定义为 $g(a)=[a]_{R, a} \in A .$ 证明典型映射是一个满射

​	由等价类的定义, 对任意 $[a]_{R} \in A / R$, 都有 $a \in A$, 使得 $g(a)=[a]_{R},$ 即任意 $A / R$ 中的元 素都有原像, 根据满射的定义知, 典型映射是满射



##### 函数类型证明

设 $<A, \leqslant>$ 是偏序集, 对任意 $a \in A$, 令 $f(a)=\{x \mid x \in A, x \leqslant a\} .$ 证明 $f$ 是从 $A$ 到 $P(A)$ 的单射函数, 并且 $f$ 保持 $<A, \leqslant>$ 与 $<P(A), \subseteq>$ 的偏序关系, 即对任意 $a, b \in A$, 若 $a \leqslant b$, 则 $f(a) \subseteq f(b) $



- 证明 $f$ 是函数:
  	任取 $a \in A$, 由于 $f(a)=\{x \mid x \in A, x \leqslant a\} \subseteq A$, 所以 $f(a) \in P(A)$, 即 $f$ 是从 $A$ 到 $P(A)$ 的函 数

- 证明 $f$ 是单射:

  对任意 $a, b \in A, a \neq b$,
  	1) 若 $a, b$ 存在偏序关系, 不妨设 $a \leqslant b($ 或 $b \leqslant a)$, 由于 "$\leqslant$" 是反对称的, 所以 $b \not \leq a($ 或 $a \neq b)$, 从而 $b \notin f(a)=\{x \mid x \in A, x \leqslant a\}$, 而 " $\leqslant$ "是自反的, 所以 $b \leqslant b$, 即 $b \in f(b)$, 所以 $f(a) \neq f(b)$, 此时, $f$ 是单射;
  	2) 若 $a, b$ 不存在偏序关系, 则有 $a \notin b$, 从而 $a \notin f(b)=\{x \mid x \in A, x \leqslant b)\}$, 而 $"$ "是自反的, 所以 $a \leqslant a$, 即 $a \in f(a)$, 所以 $f(a) \neq f(b)$, 此时, $f$ 仍是单射. 因此对任意 $a, b \in A$, 当 $a \neq b$, 总有 $f(a) \neq f(b) .$ 从而 $f$ 是从 $A$ 到 $P(A)$ 的单射函数.

- 证明保序性:

  ​	对任意 $a, b \in A$, 若 $a \leqslant b$, 则任取 $y \in f(a)$, 则 $y \leqslant a$, 由 $a \leqslant b$, 根据" $\leqslant$ "的传 递性, 有 $y \leqslant b$, 从而 $y \in f(b)$, 所以 $f(a) \subseteq f(b)$, 即保序性成立



### 函数的运算



#### 函数的复合运算

- 设 $f: A \rightarrow B, g: B \rightarrow C$ 是两个函数
  - 则 $f$ 与 $g$ 的复合关系 $f\circ g=\{<x, z>\mid x \in A, z \in C, \exists y \in B$, 使得 $y=f(x)$ 且 $z=g(y)\}$ 是从 $A$ 到 $C$ 的函数
  - 称为函数 $f$ 与 $g$ 的复合函数(composition function), 记为 $f \circ g: A \rightarrow C$

- 注意
  - 函数 $f$ 和 $g$ 可以复合的前提条件是 $\operatorname{ranf} \subseteq$ domg ;
  - $\operatorname{dom}(f \circ g)=d o m f, r a n(f \circ g) \subseteq$ rang
  - 对任意 $x \in A$, 有 $f \circ g(x)=g(f(x)) ;$
  - $I_{A} \circ f=f \circ I_{B}=f$

- 函数的交或并运算的结果不一定是函数，但是上面的运算方法能保证结果一定是函数
- 函数的复合不满足交换率
- 函数的复合满足结合律



#### 复合运算的保守性

- 设 $f$ 和 $g$ 分别是从 $A$ 到 $B$ 和从 $B$ 到 $C$ 的函数，则
	- 若 $f, g$ 是满射，则 $f \circ g$ 也是从 $A$ 到 $C$ 的满射
	- 若 $f, g$ 是单射，则 $f \circ g$ 也是从 $A$ 到 $C$ 的单射
	- 若 $f, g$ 是双射，则 $f \circ g$ 也是从 $A$ 到 $C$ 的双射
- 逆定理不成立
	- 若 $f \circ g$ 是双射，则 $f$ 是单射， $g$ 是满射，前单后满
	
- 对 $\forall c \in C$, 由 $g$ 是满射, 所以 $\exists b \in B$, 有 $g(b)=c .$ 又 $f$ 是满射, 所以 $\exists a \in A$, 有 $f(a)=b, 从$ 而 $f \circ g(a)=g(f(a))=g(b)=c$. 即 $\exists a \in A$, 使得 $f \circ g(a)=c$, 所以 $f \circ g$ 是满射
- 对 $\forall a_{1}, a_{2} \in A, a_{1} \neq a_{2} .$ 由于 $f$ 是单射, 所以 $f\left(a_{1}\right) \neq f\left(a_{2}\right) .$ 令 $b_{1}=f\left(a_{1}\right), b_{2}=f\left(a_{2}\right)$, 所以
$g\left(b_{1}\right) \neq g\left(b_{2}\right)$, 即 $g\left(f\left(a_{1}\right)\right) \neq g\left(f\left(a_{2}\right)\right) .$ 从而有 $f \circ g\left(a_{1}\right) \neq f \circ g\left(a_{2}\right)$, 所以 $f \circ g$ 是单;



#### 函数的逆

- 设 $f: A \rightarrow B$ 是函数, 如果 $f^{-1}=\{<y, x>\mid x \in A, y \in B, y=f(x)\}$ 是从 $B$ 到 $A$ 的函数, 则称 $f^{-1}: B \rightarrow A$ 为函数 $f$ 的逆函数(inverse function)
  - 逆运算后不一定是函数
  - 函数 $f^{-1}$ 存在当且仅当 $f$ 是双射, 此时 $f^{-1}$ 也是双射
  - $f \circ f^{-1}=I_{A} \quad ; \quad f^{-1} \circ f=I_{B}$

