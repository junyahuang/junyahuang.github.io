---
layout: post
title: 离散数学笔记废案
date: 2021-01-29
categories: marginalia
tags: [课堂笔记]
description: 网课网课网课
header-img: "img/headline7.jpg"
catalog:  true
typora-root-url: ../../junyahuang.github.io
---

# 谓词逻辑



## 基本推理形式和蕴含关系



### 推理的基本形式

- 所谓推理，是指从已租前提合乎逻辑的推出结论的思维过程。在这里，我们使用命题公式来表达前提和结论
- 设 $G_{1}, G_{2}, \cdots, G_{n},$ $H$ 是公式，称 $H$ 是 $G_{1}, G_{2}, \cdots, G_{n}$ 的逻辑结果当且仅当对任意解释 $I$, 如果 $I$ 使得G $_{1} \wedge G_{2} \wedge \cdots \wedge G_{n}$ 为真，则 $I$ 也会使 H为真。记为$G_{1}, G_{2}, \cdots, G_{n} \Rightarrow H_{0}$ “ $\Rightarrow$ ”称为蕴涵关系。此时称 $G_{1}, G_{2}, \cdots, G_{n} \Rightarrow H$ 为有效的, 否则称为无效的。 $G_{1}, G_{2}, \cdots, G_{n}$称为一组前提，有时用集合 $\Gamma$  (伽马) 来表示，记为 $\Gamma=\left\{G_{1}, G_{2}, \cdots, G_{n}\right\}, H$ 称为结论。此时 也称 $H$ 是前提集合 $\Gamma$ 的逻辑结果。记为 $\Gamma \Rightarrow H_{0}$
  - 有效的推理不一定是正确的推理

### 推理的判定定理

- 公式 $H$ 是前提集合 $\Gamma=\left\{G_{1}, G_{2}, \cdots, G_{n}\right\}$ 的逻辑结果当且仅当 $\left(G_{1} \wedge G_{2} \wedge \cdots \wedge G_{n}\right) \rightarrow H$为永真公式。

- 判定方法
  - 真值表技术
  - 公式转换法
  - 主析取范式法

#### 实例

- 判断推理 $P \rightarrow Q, P \Rightarrow Q$ 是否有效？

- 方法一：真值表技术

| $P$  | $Q$  | $((P \rightarrow Q) \wedge P) \rightarrow Q$ |
| :--: | :--: | :------------------------------------------: |
|  0   |  0   |                      1                       |
|  0   |  1   |                      1                       |
|  1   |  0   |                      1                       |
|  1   |  1   |                      1                       |

- 方法二：公式转换法

​	$((P \rightarrow Q) \wedge P) \rightarrow Q$

$=\neg((\neg P \vee Q) \wedge P) \vee Q$

$=\neg(\neg P \vee Q) \vee \neg P \vee Q$

$=\neg(\neg P \vee Q) \vee(\neg P \vee Q)$

$=1$

- 方法三：主析取范式法

​	$((P \rightarrow Q) \wedge P) \rightarrow Q$

$=\neg((\neg P \vee Q) \wedge P) \vee Q$

$=\neg(\neg P \vee Q) \vee \neg P \vee Q$

$=(P \wedge \neg Q) \vee \neg P \vee Q$

$=(P \wedge \neg Q) \vee(\neg P \wedge(\neg Q \vee Q)) \vee((\neg P \vee P) \wedge Q)$

$=(\neg P \wedge \neg Q) \vee(\neg P \wedge Q) \vee(P \wedge \neg Q) \vee(P \wedge Q)\left(m_{0} \vee m_{1} \vee m_{2} \vee m_{3}\right)$

包括了所有的极小项，故为永真公式



### 推理定律——基本蕴含关系



设 $G, H, I$ 为任意的命题公式
以下，左侧为真则右侧为真：

- $I_{1}: G \wedge H \Rightarrow G ; \quad I_{2}: G \wedge H \Rightarrow H$（简化规则）
- $I_{3}: G \Rightarrow G \vee H ; \quad I_{4}: H \Rightarrow G \vee H$（添加规则）
- $I_{5}: G, H \Rightarrow G \wedge H$（合取引入规则）
- $I_{6}: G \vee H, \neg G \Rightarrow H ; \quad I_{7}: G \vee H, \neg H \Rightarrow G$（选言三段论）
- $I_{8}: G \rightarrow H, G \Rightarrow H$（假言推理规则）
  - “假如天气晴朗，则我们去旅游”，若“天气确实晴朗”，则推出“我们去旅游”为真 
- $I_{9}: G \rightarrow H, \neg H \Rightarrow \neg G$（否定后件事）
  - “假如天气晴朗，则我们去旅游”，若“天气不晴朗”，则推出“我们不去旅游”为真 
- $I_{10}: G \rightarrow H, H \rightarrow I \Rightarrow G \rightarrow I$（假言三段论）
  - 如果有 $G$ 则有 $H$，如果有 $H$ 则有 $I$，推出如果有 $G$，必然有 $I$
- $I_{11}: G \vee H, G \rightarrow I, H \rightarrow I \Rightarrow A$（二难推论）
  - $G$ 析取 $H$ 为真，有 $G$ 则有 $I$，有 $H$ 则有 $I$，推出 $I$ 为真 	



#### 实例

- 如果 a 是偶数，则 a 能被 2 整除：a 是偶数。所以，a 能被 2 整除
  - 可描述为 $: P \rightarrow Q, P \Rightarrow Q$（假言推理规则）
- 如果一个人是单身汉，则他不幸福：如果一个人不幸福，则他死得旱。所以，单身汉死得早
  - 可描述为 $: P \rightarrow Q, Q \rightarrow R \Rightarrow P \rightarrow R$（假言三段论）
- 若你发电子邮件告诉我密码，则我将完成程序的编写：我没有完成程序的编写。所以，你没 有发电子邮件告诉我密码
  - 可描述为 $: P \rightarrow Q, \neg Q \Rightarrow \neg P \quad$（否定后件式）
- 这个案件的凶手肯定是王某或陈某 ; 经过调查，王某不是凶手。所以，陈某是凶手 
  - 可描述为 $: P \vee Q, \neg P \Rightarrow Q$（选言三段论） 



## 自然演绎法推理



### 推理规则

- 规则 $P$ (称为前提引用规则)：在推导的过程中，可随时引入前提集合中的任意一个前提
- 规则 $T$ (称为逻辑结果引用规则)：在推导的过程中，可以随时引入公式 $S,$ 该公式 $S$ 是由其 前的一个或多个公式推导出来的逻辑结果
- 规则 $C P$ (称为附加前提规则)：如果能从给定的前提集合 $\Gamma$ 与公式 $P$ 推导出 $S,$ 则能从此 前提集合 $\Gamma$ 推导出 $P \rightarrow S_{\circ}$
  - 原理 $: P \rightarrow(Q \rightarrow R)=(P \wedge Q) \rightarrow R$
  - 使用场合：当结论公式是**蕴含式或析取式**时使用
- 三个推理规则加上全部的基本等价公式和基本蕴含公式，可作为推理与演绎的基础，从而构造一个完整的命题验算推理系统。即所有命题逻辑的定理都可以用这些规则严格地证明出来



### 演绎法推理

- 从前提集合 $\Gamma$ 推出结论 $H$ 的一个演支是构造命题公式的一个有限序列：
  - $H_{1}, H_{2}, H_{3}, \cdots, H_{n-1}, H_{n}$
  - 其中，$H_{i}$ 或者是 $\Gamma$ 中的某个前提，或者是前面的某些 $H_{j}(j<i)$ 的**有效结论**，并且 $H_{n}$ 就是 $H$ ，则称公式 $H$ 为该演支的有效结论，或者称从前提 $\Gamma$ 能够演支出结论 $H$ 来。 	

#### 演绎：直接证明法

设前提集合 $\Gamma=\{P \vee Q, Q \rightarrow R, P \rightarrow S, \neg S\},$ 结论 $H=R \wedge(P \vee Q)$
证明 $\Gamma \Rightarrow H$

| 结论                            | 推理条件和方法 |
| ------------------------------- | -------------- |
| $(1)\quad$ $P \rightarrow S$    | $P$            |
| $(2)\quad$ $\neg S$             | $P$            |
| $(3)\quad$ $\neg P$             | $T,(1),(2),I$  |
| $(4)\quad$ $P \vee Q$           | $P$            |
| $(5)\quad$ $Q$                  | $T,(3),(4), I$ |
| $(6)\quad$ $Q \rightarrow R$    | $P$            |
| $(7)\quad$ $R$                  | $T,(5),(6), I$ |
| $(8)\quad$ $R \wedge(P \vee Q)$ | $T,(4),(7), I$ |

- $I$ 表示使用基本蕴含关系
- $E$ 表示使用基本等价关系



- 思考步骤：
  - 先考虑得到 $R$，已经条件 $Q \rightarrow R$，则需要知道 $Q$  为真
  - 与 $Q$ 有关的条件为 $P \vee Q$，则需要知道 $\neg P$ 为真
  - 与 $\neg P$ 有关的条件为 $P \rightarrow S$、$\neg S$
  - 则知 $\neg P$ 为真，随后一步步倒推即可



#### 演绎：规则 $CP$ 证明法

设前提集合 $\Gamma=\{P \rightarrow(Q \rightarrow S), \neg R \vee P, Q\},$ 结论 $H=R \rightarrow S$
证明 $\Gamma \Rightarrow H_{\circ}$

| 结论                                       | 推理条件和方法  |
| ------------------------------------------ | --------------- |
| $(1)\quad R$                               | $P$（附加前提） |
| $(2)\quad \neg R \vee P$                   | $P$             |
| $(3)\quad P$                               | $T,(1),(2), I$  |
| $(4) \quad P \rightarrow(Q \rightarrow S)$ | $P$             |
| $(5)\quad Q \rightarrow S$                 | $T,(3),(4), I$  |
| $(6)\quad Q$                               | $P$             |
| $(7)\quad S$                               | $T,(5),(6), I$  |
| $(8)\quad R \rightarrow S$                 | $C P,(1),(7)$   |

- 思考步骤：
  - 和 $S$ 相关的条件只有 P \rightarrow(Q \rightarrow S)
  - 子公式为 $Q \rightarrow S$，要得到 $S$ 需知道 $Q$，而 $Q$ 为给定前提
  - 提取 $Q \rightarrow S$ 需要有 $P$，与 $P$ 有关的条件为 $\neg R \vee P$
  - 如果 $\neg R \vee P = P$ 成立，则 $\neg R$ 不成立才可以，则需证明 $R$ 成立
  - 而 $R$ 为附加条件



#### 演绎：间接证明法（反证法、归谬法）

- 要证明 $: G_{1}, G_{2}, \cdots, G_{n} \Rightarrow H$

  ​	根据判定定理 $:\left(G_{1} \wedge G_{2} \wedge \cdots \wedge G_{n}\right) \rightarrow H$ 为永真公式

  ​	即 $: G_{1} \wedge G_{2} \wedge \cdots \wedge G_{n} \wedge \neg H$ 是矛盾式

  ​	因此 $: G_{1} \wedge G_{2} \wedge \cdots \wedge G_{n} \wedge \neg H \Rightarrow R \wedge \neg R$ 

- 方法：将**结论的否定**加入前提集合中，证明出矛盾即可



设前提集合 $\Gamma=\{P \vee Q, P \rightarrow R, Q \rightarrow R\},$ 结论 $H=R_{\circ}$ 证明 $\Gamma \Rightarrow H$

| 结论                         | 推理条件和方法   |
| ---------------------------- | ---------------- |
| $(1)\quad$ $\neg R$          | $P$ （附加前提） |
| $(2)\quad$ $P \rightarrow R$ | $P$              |
| $(3)\quad$ $\neg P$          | $T,(1),(2), I$   |
| $(4)\quad$ $Q \rightarrow R$ | $P$              |
| $(5)\quad$ $\neg Q$          | $T,(1),(4), I$   |
| $(6)\quad$ $P \vee Q$        | $P$              |
| $(7)\quad$ $P$               | $T,(5),(6), I$   |
| $(8)\quad$ $P \wedge \neg P$ | $T,(3),(7), I$   |



- 反证法在逻辑推理中有时也十分方便
  - 当结论的信息非常丰富（长）的时候，并且此时前提条件非常简单
  - 此时将结论取反，作附加前提使用时，无形中增加很多条件
- 然而，总可以不使用它而用规则 $CP$ 证明法来代替它。因为，它实际上本身就是规则 $CP$ 的一种变型。。


### 命题演绎实例

#### 实例一

符号化下面的语句，并使用演绎法证明：
	

​	若数 $a$ 是实数，则它不是有理数就是无理数。若 $a$ 不能表示成分数，则它不是有理数。 $a$ 是实数且它不能表示成分数。所以，$a$ 是无理数。



解：

​	设命题：$P:$ $a$ 是实数
​					$Q:$ $a$ 是有理数
​					$R:$ $a$ 是无理数
​					$S:$ $a$ 能表示成分数

​	则推理符号化成为：

​					$P \rightarrow(Q \vee R), \neg S \rightarrow \neg Q, P \wedge \neg S \Rightarrow R$


| 结论                                   | 推理条件和方法 |
| -------------------------------------- | -------------- |
| $(1)\quad$ $P \wedge \neg S$           | $P$            |
| $(2)\quad$ $P$                         | $T,(1), I$     |
| $(3)\quad$ $\neg S$                    | $T,(1), I$     |
| $(4)\quad$ $P \rightarrow(Q \vee R)$   | $P$            |
| $(5)\quad$ $Q \vee R$                  | $T,(2),(4), I$ |
| $(6)\quad$ $\neg S \rightarrow \neg Q$ | $P$            |
| $(7)\quad$ $\neg Q$                    | $T,(3),(6), I$ |
| $(8)\quad$ $R$                         | $T,(5),(7), I$ |

- 思维步骤：
  - 想得到 $R$，只有 $P \rightarrow(Q \vee R)$ 含有 $R$
  - 若 $Q \vee R = R$，则需要得到 $\neg Q$
  - 从 $\neg S \rightarrow \neg Q$ 入手，则需要得到 $\neg S$ 成立
  - $\neg S$ 在 $P \wedge \neg S$ 中，则 $P$ 和 $\neg S$都成立



#### 实例二

符号化下面的语句，并使用演绎法证明：
	

​	如果马会飞或羊吃草，则母鸡就会是飞鸟；如果母鸡是飞鸟，那么烤熟的鸭子还会跑；烤熟的鸭子不会跑。所以羊不吃草。

​	注意：**推理的有效性和真实性是不同的**，推理本身是有效的，但是结论是错误的。因为前提中有假，但是这并不妨碍我们做正确的推理。

解：

​	设命题：$P:$ 马会飞
​					$Q:$ 羊吃草
​					$R:$ 母鸡是飞鸟
​					$S:$ 烤熟的鸭子会跑

​	则推理符号化成为：

​					$(P \vee Q) \rightarrow R, R \rightarrow S, \neg S \Rightarrow \neg Q$

| 结论                                  | 推理条件和方法 |
| ------------------------------------- | -------------- |
| $(1)\quad$ $\neg S$                   | $P$            |
| $(2)\quad$ $R \rightarrow S$          | $P$            |
| $(3)\quad$ $\neg R$                   | $T,(1),(2)I$   |
| $(4)\quad$ $(P \vee Q) \rightarrow R$ | $P$            |
| $(5)\quad$ $\neg(P \vee Q)$           | $T,(3),(4), I$ |
| $(6)\quad$ $\neg P \wedge \neg Q$     | $T .(5), E$    |
| $(7)\quad$ $\neg Q$                   | $T,(6), I$     |

- 第五步到第六步为德摩根律的等价变换，为 $E$

- 思维步骤

  - $\neg Q$ 无法直接得到，所以需要变形，可以从前提中最简单的前提开始着手
  - 最简单的前提为 $\neg S$，与之相关的还有 $R \rightarrow S$
  - 由否定后件式可以得到 $\neg R$，而$\neg R$ 和 $(P \vee Q) \rightarrow R$ 可以得到 $\neg(P \vee Q)$ 为真
  - $\neg(P \vee Q)$ 根据德摩根律等于 $\neg P \wedge \neg Q$
  - 所以 $\neg P$ 和 $\neg Q$ 均成立，所以结论 $\neg Q$ 成立





## 谓词的引入



### 命题逻辑的局限性

- 苏格拉底三段论
  - 所有的人都是要死的；苏格拉底是人。所以，苏格拉底是要死的。
- 含变量的语句
  - x$ > 3$ $x=y+3；$$x+y=z$ ...等等
- 为了研究简单命题句子内部的逻辑关系，我们需要对简单命题进行分解，利用**个体词、谓词和量词**来描述它们，并研究个体与总体的内在联系和数量关系，这就是**谓词逻辑**或**一阶逻辑**



### 个体词和谓词



#### 简单命题分解

- 命题是具有真假意义的陈述句，从语法上分析，一个陈述句由主语和谓语两部分组成

- 在原子命题中，可以独立存在的客体（**句子中的主语、宾语等**），称为个体词，而用以**刻画客体的性质或客体之间的关系**即是**谓词**



- 考虑如下两个命题
  - 陈华是东北师范大学的学生
  - 张强是东北师范大学的学生
  - 设 $P(x): x$ 是东北师范大学的学生
    - 则上述两个句子可写为：
      - $\mathrm{P}$(陈华)
      - $\mathrm{P}$(张强)

- 语句 “x 大于 3" 可用 $Q(x)$ 表示
  - $Q(x)$ 无固定真值，一旦给变量 $x$ 赋一个值，则成为命题，具有一个或真或假的真 值。如 $x=5,$ 则 $Q(5)=1$ 
- 吾句 " $x=\mathrm{y}+3 "$ 可用 $R(x, y)$ 表示
  -  $R(x, y)$ 无固定真值，一旦给变量 $x, y$ 赋一个值，则成为命题，具有一个或真或假的 真值。如 $x=5, y=3,$ 则 $R(5,3)=0$ 



### 个体词

- 个体词可分为两种， 个体常量和个体变量，均在个体域内取值
  - 表示具体或特定的个体词称为个体常量。一般用带或不带下标的小写英文字母$a, b, c, \cdots, a_{1}, b_{1}, c_{1}, \cdots$ 等表示
  - 表示抽象的或泛指的个体词称为个体变量。一般用带或不带下标的小写英文字母 $x, y, z, \cdots, x_{1}, y_{1}, z_{1}, \cdots$ 等表示
  - 个体词的取值范围称为个体域 (或论域)，常用 $D$ 表示
  - 宇宙间的所有个体域聚集在一起所构成的个体域称为全总个体域。若无特别说明 均使用全总个体域



### 谓词

- 设 $D$ 为非空的个体域，定义在D^n(表示 n 个个体都在个体域 $D$ 上取值) 上取值于 \{0,1\} 上的 n 元 函数，称为 $n$ 元命题函数或 $n$ 元谓词，记为$P\left(x_{1}, x_{2}, \cdots, x_{n}\right)$ 。其中，个体变量 $x_{1}, x_{2}, \cdots, x_{n} \in D$
  - 表示具体性质或关系的谓词称为谓词常量
  - 表示抽象的或泛指的性质或关系的谓词称为谓词变量
- 谓词均使用大写英文字母 $P, Q, R, \cdots, F, G, H, \cdots$ 来表示



- 小张和小李同岁。可描述为： $F(a, b)$, 其中 $a:$ 小张， $b:$ 小李，这里的 $F$ 是谓词常量
- $x$ 与 $y$ 具有关系 $L$。可描述为 $: L(x, y),$ 这里的 $L$ 是谓词变量



### 复合命题的谓词符号化

- 如果王童是一个三好学生，那么她的学习成绩一定很好

  - 设 $S(x): x$ 是一个三好学生

    ​	$H(x): x$ 学习成绩好，$a$ : 王童

  - 则该命题符号化为 $: S(a) \rightarrow H(a)$

- 李新华是李兰的父亲并且李兰和张三是同班同学

  - 设 $F(x, y): x$ 是 $y$ 的父亲 

    ​	$M(x, y): x$ 与 $y$ 是同班同学

    ​	$b:$ 李新华，$c:$ 李兰， $d:$ 张三 

  - 则该命题符号化为 $: F(b, c) \wedge M(c, d)$

- 北京是中国的首都当且仅当 2 是偶数

  - 设 $C(x): x$ 是中国的首都

    ​	$E(x): x$ 是偶数

    ​	 $b:$ 北京，$c:2$ 

  - 则该命题符号化为 $: C(b) \leftrightarrow E(c)$



### 说明和总结

- 谓词中个体词的顺序是十分重要的，不能随意变更。 $F(b, c) \neq F(c, b)$
- 一元谓词用以描述某一个个体的某种**特性**，而 $n$ 元谓词 $(n \geqslant 2)$ 则用以描述 $n$ 个个体之间的**关系**
- 谓词 $P\left(x_{1}, x_{2}, \cdots, x_{n}\right)$ 包含了个体变量，因而本身并不是命题，只有用谓词常量取代 $P$, 用个体常量取代 $x_{1}, x_{2}, \cdots, x_{n}$ 后才会成为命题 
  - 谓词本身不是命题，下了定义之后才是命题
- 一般将没有任何个体变量的谓词称为 $0$ 元谓词，如$F(a), G(a, b), H\left(a_{1}, a_{2}, \cdots, a_{n}\right)$ 等。当 $F, G, H$ 为谓词常量时， $0$ 元谓词就成为了命题。此时，**命题逻辑中的所有命题都可以表示成 $0$ 元谓词**



## 量词



### 量词的引入

- 虽然目前有了个体词和谓词，但对于有些命题而言，还是无法准确描述
  - **所有的**老虎都要吃人
  - **每一个**大学生都会说英语
  - **有一些**人登上过月球
  - **存在**自然数是素数



### 量词的定义

- 全称量词 $(\forall x):$ 所有的 $x ;$ 任意的 $x ;$ 一切的 $x ;$ 每一个 $x; \ldots$
- 存在量词 $(\exists x):$ 有些 $x ;$ 至少有一个 $x ;$ 某一些 $x ;$ 存在 $x ; \cdots$
- 其中的 $x$ 称为作用变量。一般将其量词加在其谓词之前，记为 $(\forall x) F(x), (\exists x) F(x) 。$ 此时，$F(x)$ 称为全称量词和存在量词的辖域

  - **所有的**老虎都要吃人
    - $\mathrm{P}(x): x$ 要吃人。 $(\forall x) P(x), x \in\{$ 老虎 $\}$
  - **每一个**大学生都会说英语
    - $Q(x): x$ 会说英语。 $(\forall x) Q(x), x \in\{$ 大学生 $\}$
  - **有一些**人登上过月球
    - $\mathrm{R}(x): x$ 登上过月球。 $(\exists x) R(x), x \in\{$ 人 $\}$
  - **存在**自然数是素数
  	- $S(x): x$ 是素数 $\alpha(\exists x) S(x), x \in\{$ 自然数 $\}$



### 个体域符号化

- 以上符号化必须要特别注明个体域，在表达比较复杂的命题时会容易混淆。下面引入更准确的表达方式：
  - **所有的**老虎都要吃人
    - $T(x): x$ 是老虎 $, P(x): x$ 要吃人。 $\quad(\forall x)(T(x) \rightarrow P(x))$
    - $x$ 如果是老虎，$x$ 就要吃人
  - **每一个**大学生都会说英语
    - $C(x): x$ 是大学生 $, Q(x): x$ 会说英语。 $(\forall x)(C(x) \rightarrow Q(x))$
  - **有一些**人登上过月球
    - $H(x): x$ 是人 $, R(x): x$ 登上过月球。 $(\exists x)(H(x) \wedge R(x))$
    - $x$ 是人和 $x$ 登上月球同时成立，至少存在 $x$ 满足两个条件
  - **存在**自然数是素数
    - $N(x): x$ 是自然数 $, S(x): x$ 是素数。 $(\exists x)(N(x) \wedge S(x))$
    - 至少存在一个 $x$ 使得自然数和素数两个条件同时成立 



#### 谓词逻辑符号化的两条规则

- 统一个体域为**全总个体域**，而对每一个句子中个体变量的变化范围用一元**特性谓词**刻划之。这种特性谓词在加入到命题函数中时必定遵循如下原则：
  - 对于**全称量词** $(\forall x),$ 刻划其对应个体域的特性谓词作为**蕴涵式之前件**加入
  - 对于**存在量词** $(\exists x)$, 刻划其对应个体域的特性谓词作为**合取式之合取项**加入
- 上述做法只是通常操作，有时根据用法不同，也可以注明 $x$ 为某特定个体域，如研究微积分时，只研究 $x$ 为实数的情况，这样可以简化问题的推导和处理



### 量词相关的真值确定

“有些同学通过了离散数学考试” 的真值如何确定？

- $(\forall x) G(x):$ 对 $\forall x \in D, G(x)$ 都成立
  - $(\forall x) G(x)$ 取值为 1 当且仅当对任意 $x \in D, G(x)$ 都取值为 1 
  - $(\forall x) G(x)$ 取值为 0 当且仅当存在 $x_{0} \in D,$ 使得 $G\left(x_{0}\right)$ 取值为 0
- $(\exists x) G(x):$ 存在一个 $x_{0} \in D,$ 使得 $G\left(x_{0}\right)$ 成立
  - $(\exists x) G(x)$ 取值为 1 当且仅当存在 $x_{0} \in D,$ 使得 $G\left(x_{0}\right)$ 取值为 1
  - $(\exists x) G(x)$ 取值为 0 当且仅当对任意 $x \in D, G(x)$ 都取值为 0

#### 实例

设 $\mathrm{P}(x): x$ 是素数 $; \mathrm{I}(x): x$ 是整数 $; \mathrm{Q}(x, y):x+y=0$ 。用语句描述下述句子，并判断其真假值

- $(\forall x)(I(x) \rightarrow P(x))$
  - "所有的整数都是素数"，真值为假
- $(\exists x)(I(x) \wedge P(x))$
  - “存在整数是素数”，真值为真
- $(\forall x)(\forall y)(I(x) \wedge I(y) \rightarrow Q(x, y))$
  - "对任意整数 $x,y$，都有$x+y=0$ "，真值为假
- $(\forall x)(I(x) \rightarrow(\exists y)(I(y) \wedge Q(x, y)))$
  - "对任意整数 $x$ 都存在整数 $y$，使得 $x+y=0$ "，真值为真
- $(\exists x)(\forall y)(I(x) \wedge(I(y) \rightarrow Q(x, y)))$
  - "存在整数 $x$，对任意整数 $y$ 都使得 $x+y=0$ "，真值为假



#### 个体域有限的情况下

- 特别的，当个体域 $D=\left\{x_{0}, x_{1}, \cdots, x_{n}\right\}$ 是有限集合时， $(\forall x) G(x)$ 和 $(\exists x) G(x)$ 的 真值可以用与之等价的命题公式来进行表示。
  - $(\forall x) G(x)=G\left(x_{0}\right) \wedge G\left(x_{1}\right) \wedge \cdots \wedge G\left(x_{n}\right)$
  - $(\exists x) G(x)=G\left(x_{0}\right) \vee G\left(x_{1}\right) \vee \cdots \vee G\left(x_{n}\right)$

- 设个体域 $D=\{1,2,3,4,5\}, P(x): x$ 是素数，则

  - $(\forall x) P(x)=P(1) \wedge P(2) \wedge P(3) \wedge P(4) \wedge P(5)=0 \wedge 1 \wedge 1 \wedge 0 \wedge 1=0$
  - $(\exists x) P(x)=P(1) \vee P(2) \vee P(3) \vee P(4) \vee P(5)=0 \vee 1 \vee 1 \vee 0 \vee 1=1$

  

## 谓词符号化距离



### 谓词逻辑符号化示例一

- **没有人**登上过木星
  - 令 $H(x): x$ 是人, $M(x): x$ 登上过木星
  - 则命题符号化为 $\neg(\exists x)(H(x) \wedge M(x))$ 或 $(\forall x)(H(x) \rightarrow \neg M(x))$
- 在美国留学的学生**未必**都是亚洲人
  - 令 $A(x): x$ 是亚洲人， $H(x): x$ 是在美国留学的学生
  - 则命题符号化为 $\neg(\forall x)(H(x) \rightarrow A(x))$ 或 $(\exists x)(H(x) \wedge \neg A(x))$
  - 否定“在美国留学的学生都是亚洲人”，或“存在非亚洲人是在美国留学的学生”
- **尽管**有人很聪明，**但**未必一切人都聪明
  - 令$M(x): x$ 是人 $; C(x): x$ 很聪明
  - 则命题符号化为 $(\exists x)(M(x) \wedge C(x)) \wedge \neg(\forall x)(M(x) \rightarrow C(x))$
  - "尽管...但" 是一种合取关系



### 谓词逻辑符号化示例二

- 天下乌鸦一般黑

  - 令 $F(x): x$ 是乌鸦 $; G(x, y): x$ 与 $y$ 一般黑
  - 则命题符号化为 $(\forall x)(\forall y)(F(x) \wedge F(y) \rightarrow G(x, y))$ 或$\neg(\exists x)(\exists y)(F(x) \wedge F(y) \wedge \neg G(x, y))$
  - 任意两只乌鸦都是一样黑的，或不存在两只不一样黑的乌鸦

- 每个实数都存在比它大的另外的实数

  - 令 $R(x): x$ 是实数 $; L(x, y):x$ 小于 $y$
  - 则命题符号化为 $(\forall x)\left(R(x) \rightarrow(\exists y)(R(y) \wedge L(x, y))\right)$
- 若假定个体域为所有实数，则命题符号化为 $(\forall x)(\exists y) L(x, y)$
  
- 两次对变元的约束往往与量词的次序有关。不同的量词次序，可以产生不同的真值。因此，当多个量词同时出现时，不能随意颠倒它们的顺序，否则会改变原有的含义。

  

### 谓词逻辑符号化示例三

符号化下面一组语句：

​	所有狮子都是凶猛的；有些狮子不喝咖啡；有些凶猛的动物不喝咖啡。

- 令 $\mathrm{P}(\mathrm{x}): \mathrm{x}$ 是狮子 $; Q(\mathrm{x}): \mathrm{x}$ 是凶猛的 $: \mathrm{R}(\mathrm{x}): \mathrm{x}$ 喝咖啡

  假定所有动物的集合为个体域 , 则命题符号化为

  - $(\forall x)(P(x) \rightarrow Q(x))$
  - $(\exists x)(P(x) \wedge \neg R(x))$
  - $(\exists x)(Q(x) \wedge \neg R(x))$

所有的个体都是动物，所以令动物的集合为个体域能简化问题



### 谓词逻辑符号化示例四

符号化下面一组句子

​	所有的蜂鸟都五彩斑斓；没有大鸟以蜜为生；不以蜜为生的鸟都色彩单调；蜂鸟都是小鸟。

- 令$P(x): x$ 是蜂鸟 $; Q(x): x$ 是大鸟 $; R(x): x$ 是以蜜为生的鸟 $; S(x): x$ 五彩斑斓

  假定所有鸟的集合为个体域，则命题符号化为

  - $(\forall x)(P(x) \rightarrow S(x))$

  - $\neg(\exists x)(Q(x) \wedge R(x))$

  - $(\forall x)(\neg R(x) \rightarrow \neg S(x))$

  - $(\forall x)(P(x) \rightarrow \neg Q(x))$

    

## 谓词合成公式



### 四类符号

在基于谓词的形式化中，我们将使用如下四种符号：

- 常量符号：指所属个体域 D 中的某个元素，用带或不带下标的小写英文字母 $a, b, c, \cdots, a_{1}, b_{1}, c_{1}, \cdots$ 来表示。
- 变量符号：指所属个体域D 中的任意元素，用带或不带下标的小写英文字母 $x, y, z, \cdots, x_{1}, y_{1}, z_{1}, \cdots$ 来表示。
- 函数符号： $\mathrm{n}$ 元函数符号 $f\left(x_{1}, x_{2}, \cdots, x_{n}\right)$ 可以是所属个体域集合 $D^{n} \rightarrow D$ 的任意一个函数，用带或不带下标的小写英文字母 $f, g, h, \cdots, f_{1}, g_{1}, h_{1}, \cdots$ 来表示。
  - 值域是个体域
- 词符号：n 元谓词符号 $P\left(x_{1}, x_{2}, \cdots, x_{n}\right)$ 可以是所属个体域集合 $D^{n} \rightarrow\{0,1\}$ 的任意一个谓词，用带或不带下标的大写英文字母 $P, Q, R, \cdots, P_{1}, Q_{1}, R_{1}, \cdots$ 来表示
  - 值域是$\{0,1\}$



#### 实例

命题 “周红的父亲是教授”：

- 若令 $f(x): x$ 的父亲 $; P(x): x$ 是教授 $; c:$ 周红，则该命题符号化为 $P(f(c))$
- 若令 $P(x): x$ 是教授 $; F(x, y): x$ 是 $y$ 的父亲 $; c:$ 周红，则该命题符号化为 $(\forall x)(F(x, c) \rightarrow P(x))$

从上面的例子可以看出，函数可用于表达个体词之间的转换关系，给谓词逻辑中的个体词带来了很大的方便



### 项

- 谓词逻辑中的项 ( Term )，被递归地定义为：
  - 任意的常量符号或任意的变量符号是项
  - 若 $f\left(x_{1}, x_{2}, \cdots, x_{n}\right)$ 是 $\mathrm{n}$ 元函数符号， $t_{1}, t_{2}, \cdots, t_{n}$ 是项，则 $f\left(t_{1}, t_{2}, \cdots, t_{n}\right)$ 是项
  - 仅由有限次使用以上两个规则产生的符号串才是项
    - 命题 “周红的父亲是教授" 可表示为 $P(f(c)),$ 这里的 $f(c)$ 是项
    - $f(g(x, y), h(a, g(x, y), z))$ 是项



### 合成公式

- 若 $P\left(x_{1}, x_{2}, \cdots, x_{n}\right)$ 是 $\mathrm{n}$ 元谓词, $t_{1}, t_{2}, \cdots, t_{n}$ 是项，则称 $P\left(t_{1}, t_{2}, \cdots, t_{n}\right)$ 为原子谓语公式，简称原子公式。
- 满足下列条件的表达式, 称为合式公式(well-formed formulae/wff)，简称公式
  - 原子公式是合式公式
  - 若 $G, H$ 是合式公式, 则 $(\neg G),(\neg H),(G \vee H),(G \wedge H),(G \rightarrow H),(G \leftrightarrow H)$ 也是合式公式
  - 若 $G$ 是合式公式， $x$ 是个体变量，则 $(\forall x) G_{、}(\exists x)$ G也是合式公式
  - 由有限次使用以上三个规则产生的表达式才是合式公式

- 公式的最外层括号可省略
- 量词后面的括号省略方式为：一个量词的辖域中仅出现一个原子公式，则此辖域的 外层括号可省略，否则不能省略
- 一个个体词只能受一个量词的约束，否则就是没有意义的

#### 实例

- $- (\forall x)(\exists y)(P(x, y) \rightarrow(Q(x, y) \vee R(x, a, f(z)))),$$(\forall x)(P(x) \rightarrow R(x))$ 等都是公式

- $(\forall x)(P(x) \rightarrow R(x)$，$(\exists y)(\forall x)(\vee P(x, y))$ 等则不是公式



## 自由变元与约束



### 定义

- 给定一个合式公式 $G$, 若变元 $x$ 出现**在使用变元的量词的辖域之内**，则称变元 $x$ 的出现为**约束出现**，此时的变元 $x$ 称为**约束变元**。若 $x$ 的出现**不是约束出现**，则称它为**自由出现**，此时的变元 $x$ 称为自由变元

- 量词辖域的确定
  - 若量词后有括号，则括号内的子公式就是该量词的辖域$(\forall x)(\cdots)$
  - 若量词后无括号，则与量词邻接的子公式为该量词的辖域。 $(\forall x) F(x)$

### 判定

确定一下公式各两次的辖域以及各个体变量为自由变元还是约束变元

- $(\forall x)(P(x) \rightarrow(\exists y) R(x, y))$
  - $P(x)$ 中的 $x,R(x, y)$ 的 $x, y$ 都为约束变元
- $(\exists x) P(x) \wedge Q(x, y)$
  - $P(x)$ 中的 $x$ 为约束变元 $, Q(x, y)$ 中的 $x, y$ 是自由变元
- $(\forall x)(\exists y) P(y, z) \vee Q(x, y)) \wedge(\exists x) R(x, y)$
  - $P(y, z),Q(x, y)$ 中的 $x, y$ 都为约束变元， $z$ 为自由变元 $; R(x, y)$ 中的 $x$ 为约束变元，$y$ 为自由变元。
- $(\forall x)(P(x) \rightarrow R(x)) \wedge(\exists y) Q(x, y)$

	- $P(x), R(x)$ 中的 $x$ 为约束变元 $,Q(x, y)$ 中的 $x$ 为自由变元、$y$ 为约束变元



### 两个规则

- 在上面的公式 $(\forall x)(P(x) \rightarrow R(x)) \wedge(\exists y) Q(x, y)$ 中， $P(x), R(x)$ 中的 $x$ 和 $Q(x, y)$ 中的 $x$ 不同，一个是约束变元，一个是自由变元，二者完全不同
- 为了更明确的区分，我们可以 不同的变量符号来表示，可将公式改为
  -  $(\forall z)(P(z) \rightarrow R(z)) \wedge(\exists y) Q(x, y)$ 或 $(\forall x)(P(x) \rightarrow$
  $R(x)) \wedge(\exists y) Q(z, y)$

- 规则1：约束变元的改名规则
  - 将量词中的变元以及该量词辖域中此变量之所有约束出现都用新的个体变元替换
  - 新的变元一定要有别于改名辖域中的所有其它变量
- 规则2：自由变元的代入规则
  - 将公式中出现该自由变元的每一处都用新的个体变元替换
  - 新的变元不允许在原公式中以任何约束形式出现。也可用个体常量代入
    - 用个体常量代入后，公式的含义发生了变化，使公式具有普遍意义的变为仅对该个体常量有意义

将公式$(\forall x)(P(x) \rightarrow Q(x, y)) \wedge R(x, y)$ 中的约束变元 $x$ 进行改名

- $(\forall z)(P(z) \rightarrow Q(z, y)) \wedge R(x, y)$

将公式 $(\forall x)(P(x) \rightarrow Q(x, y)) \wedge R(x, y)$ 中的自由变元 $y$ 进行代入

- $(\forall x)(P(x) \rightarrow Q(x, z)) \wedge R(x, z)$



### 闭式

- 设 $G$ 是任意一个公式，若 $G$ 中无自由出现的个体变元，则称 $G$ 为封闭的合式公式，简 称闭式。
  - $(\forall x)(P(x) \rightarrow(\exists y) R(x, y))$ 是闭式
  - $(\exists x) P(x) \wedge Q(x, y)$ 不是闭式
- 显然，闭式是一个命题
  - $x=0$不是一个闭式，所以不是一个命题



## 公式的解释与分类



### 公式的解释

谓词逻辑中公式 $G$ 的每一个解释 $I$ 由如下四部分组成 $：$

- $(\forall x) F(x)$
- 非空的个体域集合 $D$
- $G$ 中的每个常量符号，指定 $D$ 中的某个特定的元素
- $G$ 中的每个 $n$ 元函数符号，指定 $D^{n}$ 到 $D$ 中的某个特定的函数
- $G$ 中的每个 $n$ 元谓词符号，指定 $D^{n}$ 到 \{0,1\} 中的某个特定的谓词
  - 规定：公式中无自由变元，或将自由变元看成是常量符号



#### 实例

设有解释 $I$ 为：

- 个体域为 $D=\{\alpha, \beta\}$

- $a$ 指定为： $\alpha$
- $f(\alpha)=\beta, f(\beta)=\alpha$
- $P(\alpha)=1, P(\beta)=0, Q(\alpha, \alpha)=0, Q(\alpha, \beta)=1, Q(\beta, \alpha)=1, Q(\beta, \beta)=1$

判断公式 $(\exists x)(P(f(x)) \wedge Q(x, f(a)))$ 在解释 I 下的真值结果

解：

​	当 $x=\alpha$ 时 ，

​	$ P(f(x)) \wedge Q(x, f(a))=P(f(\alpha) \wedge Q(\alpha, f(\alpha)))=P(\beta) \wedge Q(\alpha, \beta)=0 \wedge 1=0$

​	当 $x=\beta$ 时，

​	$P(f(x)) \wedge Q(x, f(a))=P(f(\beta) \wedge Q(\beta, f(\alpha)))=P(\alpha) \wedge Q(\beta, \beta)=1 \wedge 1=1$

​	可见原公式的真值结果为真



### 公式的分类

- 如果公式 $G$ 在它所有的解释下都取值为真，则称 $G$ 为有效公式
  - 这里的有效称为“逻辑上的有效”
  - $(\forall x)(\forall y)(P(x, y) \wedge Q(x, y) \rightarrow P(x, y))$
  - $(\forall x)(\forall y)(\neg P(x, y) \vee P(x, y))$
- 如果公式 $G$ 在它所有的解释下都取值为假，则称 $G$ 为矛盾公式
  - $(\forall x)(\forall y)(\neg P(x, y) \wedge P(x, y))$
- 如果至少有一种解释使得公式 $G$ 取值为真，则称 $G$ 为可满足公式



### 公式的判定问题

- 谓词逻辑是不可判定的
  - 谓词公式通常无法给出全部的解释
- 只含有一元谓词变项的公式是可判定的
- 如下形式的公式
  - $\left(\forall x_{1}\right)\left(\forall x_{2}\right) \cdots\left(\forall x_{n}\right) P\left(x_{1}, x_{2}, \cdots, x_{n}\right)$
  - $\left(\exists x_{1}\right)\left(\exists x_{2}\right) \cdots\left(\exists x_{n}\right) P\left(x_{1}, x_{2}, \cdots, x_{n}\right)$
  - 若 $P$ 中无量词和其它自由变元时，也是可判定的
- 个体域有穷时的谓词公式是可判定的



## 公式的等价关系



### 等价

- 如果公式 $G \leftrightarrow H$ 是有效公式，则公式 $G, H$ 称为等价的，记为 $G=H$
- 设 $G\left(P_{1}, P_{2}, \cdots, P_{n}\right)$ 是命题演算中的命题公式, $P_{1}, P_{2}, \cdots, P_{n}$ 是出现在 $G$ 中的命题变元，当用 任意的谓词公式 $G_{i}(1 \leqslant i \leqslant n)$ 分别代入 $P_{i}$ 后，得到的新谓词公式 $G\left(G_{1}, G_{2}, \cdots, G_{n}\right)$ 称为原公式 的代入实例
  - 永真公式的任意一个代入实例必为有效公式
  - 命题演算中的基本等价公式 $E_{1}-E_{24}$ 在谓词演算中仍然成立



### 谓词演算中的基本等价公式

假设 $G(x), H(x)$ 是只含自由变元 $x$ 的公式, $S$ 是不含 $x$ 的公式，则在全总个体域中，有

- 改名规则

    $E_{25}:(\exists x) G(x)=(\exists y) G(y)$
    $E_{26}:(\forall x) G(x)=(\forall y) G(y)$

- 量词转换率 / 量词否定等价式

  $E_{27}: \neg(\exists x) G(x)=\left(\forall^{\prime} x\right) \neg G(x)$
  $E_{28}: \neg(\forall x) G(x)=(\exists x) \neg G(x)$

- 量词辖域的扩张和收缩率

  $E_{29}:(\forall x)\left(G(x) \vee S\right)=(\forall x) G(x) \vee S$
  $E_{30}:(\forall x)(G(x) \wedge S)=(\forall x) G(x) \wedge S$
  $E_{31}:(\exists x)(G(x) \vee S)=(\exists x) G(x) \vee S$
  $E_{32}:(\exists x)(G(x) \wedge S)=(\exists x) G(x) \wedge S$

- 量词分配率

  $\left.E_{33}:(\forall x) ( G(x) \wedge H(x)\right)=(\forall x) G(x) \wedge(\forall x) H(x)$

  - "全称量词" 只对 "合取" 满足分配率

  $E_{34}:(\exists x)(G(x) \vee H(x))=(\exists x) G(x) \vee(\exists x) H(x) $

  - "存在量词" 只对 "析取" 满足分配率

- 改名分配率

  $E_{35}:(\forall x) G(x) \vee(\forall x) H(x)=(\forall x)(\forall y)(G(x) \vee H(y))$

  - 全称量词 $+$ 析取

  $E_{36}:(\exists x) G(x) \wedge(\exists x) H(x)=(\exists x)(\exists y)(G(x) \wedge H(y))$

   - 存在量词 $+$ 合取

- 对于多个量词的公式，设 $G(x, y)$ 是含有自由变元 $x, y$ 的谓词公式，则有

  $E_{37}:(\forall x)(\forall y) G(x, y)=(\forall y)(\forall x) G(x, y)$
  $E_{38}:(\exists x)(\exists y) G(x, y)=(\exists y)(\exists x) G(x, y)$

  ​	- 都是全称量词或存在量词，可以交换顺序

#### 实例

设 $P(x): x$ 今天来上课， 个体域为某班全体同学的集合。则

​	$\neg(\forall x) P(x) :$ 不是所有的同学今天来上课了

​	$(\exists x) \neg P(x):$ 今天有的同学没来上课

​	同样，$\neg(\exists x) P(x)$ 与 $(\forall x) \neg P(x)$ 意义也相同

2、设 $G(x): x$ 勤奋学习， $H(x): x$ 喜欢体育活动， 个体域是大学里的学生

​	$(\forall x)(G(x) \wedge H(x)):$ 大学里所有学生既勤奋学习又喜欢体育活动

​	$(\forall x) G(x) \wedge(\forall x) H(x):$ 大学所有学生都勤奋学习且大学所有的学生都喜欢体育活动

3、利用谓词之间的等价关系证明 $: \neg(\exists x)(M(x) \wedge F(x))=(\forall x)(M(x) \rightarrow \neg F(x))$

​	$\neg(\exists x)(M(x) \wedge F(x))$

​	$=(\forall x) \neg(M(x) \wedge F(x))$

​	$=(\forall x)(\neg M(x) \vee \neg F(x))$$

​	$=(\forall x)(M(x) \rightarrow \neg F(x))$



## 前束范式



### 定义

- 在命题逻辑里，每一公式都有与之等值的范式，范式是一种统一的表达形式，当研究一个公式的特点（如永真、永假）时，范式起着重要作用。对谓词逻辑的公式来说，也有范式，其中前束范式与原公式是等值的，而其他范式与原公式只有较弱的关系
- 称公式 $G$ 是一个前束范式，如果 $G$ 中的一切量词都位于该公式的最前端 (不含否定词) 且这些量 词的辖域都延伸到公式的仅端。其标准形式如下：
  - $\left(Q_{1} x_{1}\right)\left(Q_{2} x_{2}\right) \cdots\left(Q_{n} x_{n}\right) M\left(x_{1}, x_{2}, \cdots, x_{n}\right)$
  - 其中 $Q_{i}$ 为量词 $\forall$ 或 $\exists(i=1, \cdots n), M$ 称作公式 $G$ 的**母式 $($ 基式** $), \mathrm{M}$ 中不再有量词
    - 所有的量词都在公式 $M$ 的前面，且不能有否定词
    - 前束范式的意思是“在前面进行约束”



### 前束范式的求解步骤

- 消去公式中的联结词“ $\rightarrow$ "，" $\leftrightarrow$ " (如果有的话)

- 反复运用量词转换律，德摩根律和双重否定律，直到将所有的“ $\neg$ "都**内移**到原子谓词公式的前端

  - $\neg(\exists x) G(x)=(\forall x) \neg G(x) ; \quad \neg(\forall x) G(x)=(\exists x) \neg G(x)$
    - 量词转换率
    - 在 $G(x)$ 处的 " $\neg$ " 若是合取或析取的形式，使用德摩根律处理

- 使用谓词的等价公式将所有量词提到公式的**最前端**并保证其辖域直到公式的末端

  - $(\exists x) G(x)=(\exists y) G(y) ; \quad(\forall x) G(x)=(\forall y) G(y)$
    - 改名规则
  - $(\forall x)(G(x) \wedge H(x))=(\forall x) G(x) \wedge(\forall x) H(x)\\(\exists x)(G(x) \vee H(x))=(\exists x) G(x) \vee(\exists x) H(x)$
    - 量词分配率
  - $(\forall x) G(x) \vee(\forall x) H(x)=(\forall x)(\forall y)(G(x) \vee H(y))\\(\exists x) G(x) \wedge(\exists x) H(x)=(\forall x)(\forall y)(G(x) \wedge H(y))$
  - $(\forall x)(G(x) \vee S)=(\forall x) G(x) \vee S ; \quad(\forall x)(G(x) \wedge S)=(\forall x) G(x) \wedge S ;$
  $(\exists x)(G(x) \vee S)=(\exists x) G(x) \vee S ; \quad(\exists x)(G(x) \wedge S)=(\exists x) G(x) \wedge S .$ 
    - 量词辖域的扩张与收缩率

  

#### 实例

求 $\neg((\forall x)(\exists y) P(a, x, y) \rightarrow(\exists x)(\neg(\forall y) Q(y, b) \rightarrow R(x)))$ 的前束范式



1. 消去联结词 $" \rightarrow ", " \leftrightarrow ",$ 得 

   $\neg(\neg(\forall x)(\exists y) P(a, x, y) \vee(\exists x)(\neg \neg(\forall y) Q(y, b) \vee R(x)))$
   
2. " $\neg$ " 消除和内移，得

   ​	$(\forall x)(\exists y) P(a, x, y) \wedge \neg(\exists x)((\forall y) Q(y, b) \vee R(x))$

   $=(\forall x)(\exists y) P(a, x, y) \wedge(\forall x)((\exists y) \neg Q(y, b) \wedge \neg R(x))$

3. 量词左移，得

   ​	$(\forall x)((\exists y) P(a, x, y) \wedge(\exists y) \neg Q(y, b) \wedge \neg R(x))$

   $=(\forall x)((\exists y) P[\vec{\mu}, x, y) \wedge(\exists z) \neg Q(z, b) \wedge \neg R(x))$

   $=(\forall x)(\exists y)(\exists z)(P(a, x, y) \wedge \neg Q(z, b) \wedge \neg R(x))$

   $=(\forall x)(\exists y)(\exists z) S(a, b, x, y, z)$

即 $:((\forall x)(\exists y)(\exists z) S(a, b, x, y, z)$ 为原公式的前束范式，这里 $S(a, b, x, y, z)=P(a, x, y) \wedge \neg Q(z, b) \wedge \neg R(x)$是母式




## 推理形式和推理规则



### 推理形式

- 设 $G_{1}, G_{2}, \cdots, G_{n}, H$ 是公式，称 $H$ 是 $G_{1}, G_{2}, \cdots, G_{n}$ 的逻辑结果(或称 $G_{1}, G_{2}, \cdots, G_{n}$ 共同蕴涵 $H)$ 当且仅当对任意解释 $I,$ 若 $I$ 同时满足 $G_{1}, G_{2}, \cdots, G_{n},$ 则 $I$ 满足 $H$
  - 记为 $G_{1}, G_{2}, \cdots, G_{n} \Rightarrow H,$ 此时称 $G_{1}, G_{2}, \cdots, G_{n} \Rightarrow H$ 是有效的，否则称为无效的
  -  $G_{1}, G_{2}, \cdots, G_{n}$称为一组前提 (premise)，有时用集合 $\Gamma$ 来表示
    - 记 $\Gamma=\left\{G_{1}, G_{2}, \cdots, G_{n}\right\}, H$ 称为结论 (conclusion)，又称 $\mathrm{H}$ 是前提集合 $\Gamma$ 的逻辑结果，记为 $\Gamma \Rightarrow H_{0}$

- 设 $G_{1}, G_{2}, \cdots, G_{n}, H$ 是公式，公式 $H$ 是前提集合 $\Gamma=\left\{G_{1}, G_{2}, \cdots, G_{n}\right\}$ 的逻辑结果当且仅 当 $G_{1} \wedge G_{2} \wedge \cdots \wedge G_{n} \rightarrow H$ 为有效公式
  - 根据代入实例的特性，命题演算中的基本蕴涵公式 $I_{1}-l_{11}$ 在谓词演算中仍然成立



### 推理规律

假设 $G(x), H(x)$ 是只含自由变元 $x$ 的公式，则在全总个体域中，有

- $I_{12}:(\forall x) G(x) \Rightarrow(\exists x) G(x)$
- $I_{13}:(\forall x) G(x) \vee(\forall x) H(x) \Rightarrow(\forall x)(G(x) \vee H(x))$
  $I_{14}:(\exists x)(G(x) \wedge H(x)) \Rightarrow(\exists x) G(x) \wedge(\exists x) H(x)$
  - 注意 "全称量词" 对 "析取“，"存在量词" 对 "合取"
- $I_{15}:(\forall x)(G(x) \rightarrow H(x)) \Rightarrow(\forall x) G(x) \rightarrow(\forall x) H(x)$
  $I_{16}:(\forall x)(G(x) \rightarrow H(x)) \Rightarrow(\exists x) G(x) \rightarrow(\exists x) H(x)$

对于多个量词的公式，设 $G(x, y)$ 是含有自由变元 $x, y$ 的谓词公式，则有

- $I_{17}:(\exists x)(\forall y) G(x, y) \Rightarrow(\forall y)(\exists x) G(x, y)$
  $I_{18}:(\forall x)(\forall y) G(x, y) \Rightarrow(\exists y)(\exists x) G(x, y)$
  $I_{19}:(\forall y)(\forall x) G(x, y) \Rightarrow(\exists x)(\forall y) G(x, y)$
  $I_{20}:(\exists y)(\forall x) G(x, y) \Rightarrow(\forall x)(\exists y) G(x, y)$
  $I_{21}:(\forall x)(\exists y) G(x, y) \Rightarrow(\exists y)(\exists x) G(x, y)$
  $I_{22}:(\forall y)(\exists x) G(x, y) \Rightarrow(\exists x)(\exists y) G(x, y)$



### 推理规则



#### 全称特指规则

- US ( 全称特指规则)
  -  $(\forall x) G(x)_{1} \Rightarrow G(y)$， $y$ 不在 $G(x)$ 中约束出现
  - 或 $:(\forall x) G(x) \Rightarrow G(c)$， $c$ 为**任意**个体常量



设实数集中，语句 “不存在最大的实数" 可符号化为 $:(\forall x)(\exists y) G(x, y) $

​	其中 $: G(x, y): y>x$

如下推导正确吗？为什么？

|步骤|条件|
|-|-|
| (1) $(\forall x)(\exists y) G(x, y)$ | $P$  |
| (2) $(\exists y) G(y, y)$       | $US,(1)$ |

解: 以上推导不正确，正确的推导应为：
|步骤|条件|
|-|-|
| (1) $(\forall x)(\exists y) G(x, y)$ | $P$  |
| (2) $(\exists y) G(z, y)$       | $US,(1)$ |



#### 存在特指规则

- ES ( 存在特指规则 ) 
  - $(\exists x) G(x) \Rightarrow G(c), c$ 为使得 $G(c)$ 为 ”**真**“ 的**特定**的个体常量
  -  当 $G(x)$ 中还有除 $x$ 之外的自由变元，则必须用关于这些变元的函数符号来取代 $c$



设实数集中，语句 “不存在最大的实数" 可符号化为 $:(\forall x)(\exists y) G(x, y) $

​	其中 $: G(x, y): y>x$

如下推导正确吗？为什么？

|步骤|条件|
|-|-|
| (1) $(\forall x)(\exists y) G(x, y)$ | $P$  |
| (2) $(\exists y) G(z, y)$       | $US,(1)$ |
|(3) $G(z, c)$|$ES,(2)$|

解: 以上推导不正确，正确的推导应为：
|步骤|条件|
|-|-|
| (1) $(\forall x)(\exists y) G(x, y)$ | $P$  |
| (2) $(\exists y) G(z, y)$       | $US,(1)$ |
|(3) $G(z, f(z))$|$ES,(2)$|

- $z$ 改变时， $y$ 应随着 $z$ 而改变，而不是一个常量



#### 全称推广规则

- UG（全称推广规则$: G(y) \Rightarrow(\forall x) G(x), G(y)$ 中无变元 $x$



设实数集中，语句 “不存在最大的实数" 可符号化为 $:(\forall x)(\exists y) G(x, y) $

​	其中 $: G(x, y): y>x$

如下推导正确吗？为什么？

|步骤|条件|
|-|-|
| (1) $(\forall x)(\exists y) G(x, y)$ | $P$  |
| (2) $(\exists y) G(z, y)$       | $US,(1)$ |
|(3) $(\forall y)(\exists y) G(y, y)$|$UG,(2)$|

解: 以上推导不正确，正确的推导应为：
|步骤|条件|
|-|-|
| (1) $(\forall x)(\exists y) G(x, y)$ | $P$  |
| (2) $(\exists y) G(z, y)$       | $US,(1)$ |
|(3) $(\forall z)(\exists y) G(z, y)$|$ES,(2)$|

- $y$ 已经出现过，不能再次用 $y$ 换元，应用不相关的字母



#### 存在推广规则

- EG ( 存在推广规则)
  - $G(c)  \Rightarrow(\exists x) G(x),$ c 为特定个体常量
  - 或 $: G(y) \Rightarrow(\exists x) G(x), G(y)$ 中无变元 $x$



设 $: G(x, y): y>x$
如下推导正确吗？为什么 ?

| 步骤                     | 条件     |
| ------------------------ | -------- |
| (1)$G(x,c)$              | $P$      |
| (2)$(\exists x) G(x, x)$ | $EG,(1)$ |


解: 以上推导不正确，正确的推导应为：
| 步骤                     | 条件     |
| ------------------------ | -------- |
| (1)$G(x,c)$              | $P$      |
| (2)$(\exists y) G(x, y)$ | $EG,(1)$ |



## 综合推理方法