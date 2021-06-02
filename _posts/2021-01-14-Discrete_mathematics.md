---
layout: post
title: 离散数学笔记
date: 2021-01-14
categories: marginalia
tags: [课堂笔记]
description: 网课网课网课
header-img: "img/headline7.jpg"
catalog:  true
typora-root-url: ../../junyahuang.github.io
---


# 命题逻辑



## 什么是命题


### 定义

- 数理逻辑研究的中心问题是**推理**，而推理的前提和结论都是命题，因而**命题**是推理的**基本单位**

- 具有确切真值的陈述句称为**命题(proposition)**。该命题可以取一个 "值"，称为**真值**。真值只有 "真" 和“假" 两种，分别用 "T" (或 "1" ) 和 "F" (或 "0" )表示



### 实例

1. 成都是一个旅游城市。真值：T
2. 北京是中国的首都。真值：T
3. 3 能被 2 整除。真值：F

- 一切没有判断内容的句子，如**命令句（或祈使句）、感叹句、疑问句、二义性的陈述句**都不能作为命题

  1. 这个语句是假的 ; 

     - 如果这是假命题，则”这个语句是真的“，矛盾
     - 如果这是真命题，则”这个语句是假的“，矛盾
     - 所以这个语句是矛盾的，不是一个命题

  2. x + y > 0 ;

     - 带变量的句子没有给出变量具体的情况，我们无法判断
     - 无法确定真假，不是一个命题
     - 带变量而没有对变量加以限制的都不是命题

  3. 把门关上 ;

  4. 滚出去！

  5. 你要出去吗？

- 有时还需依靠环境、条件、时间、地点、实际情况才能确定命题的真值。而一个句子本身是否能分辨真假与我们是否知道它的真假是两回事，也就是说，对于一个句子，有时我们 可能无法判断它的真假，但这个句子本身却是有真假的
  1. 我喜欢踢足球；
     - 取决于个人，有真假
     - 是真命题
  2. 今天是晴天；
     - 取决于天气，有真假
     - 是真命题
  3. 地球外的星球上也有人;
  4. 1+1=10；
     - 依赖于这是二进制还是十进制
     - 我们不知道是真是假，但是我们知道这是有真假的
     - 这是真命题



### 复合命题

- 原子命题 (简单命题) : 不能再分解为更为简单命题的命题。
- 复合命题：可以分解为更为简单命题的命题。这些简单命题之间是通过如“或者"、“并且"、"不"、"如果......则....."、"当且仅当" 等这样的关联词和标
  点符号复合而成。
  1. 四川不是一个国家
  2. 3既是素数又是非素数
  3. 张谦是大学生或是运动员
  4. 如果周末天气晴朗，则我们将到郊外旅游
  5. 两个三角形全等当且仅当三角形的三条边全部相等

- 约定：通常用大写带或不带下标的英文字母表示命题 (包括原子命题和复合命题)。
  - $A, B, C, \cdots, P, Q, R, \cdots, A_{i}, B_{i}, C_{i}, \cdots, P_{i}, Q_{i}, R_{i}, \cdots$



## 命题联结词



### 否定联结词

- 设 $P$ 是任意一个命题，复合命题“ 非 $P$ ” ( 或 " $P$ 的否定 "  ) 称为 $P$ 的**否定式**(negation)，记作$\neg P$， **" $\neg$ " **为否定联结词。
-  $P$ 为真当且仅当 $\neg P$ 为假。。
	- $\neg P:$ 四川不是一个国家。
  - $P:$ 四川是一个国家。
- "$\neg$" 是自然语言中的“非”、“不”、“没有”等的逻辑抽象



### 合取联结词

- 设 $P 、 Q$ 是任意两个命题，复合命题“ $P$ 并且 $Q$ "(或 " $P$ 和 $Q$ “ )称为 $P$ 与 $Q$ 的**合取式**(conjunction)，记作 $P \wedge Q,$ **“ $\wedge$ "** 为合取联结词。
-  $P \wedge Q$ 为真当且仅当 $P, Q$ 同为真。
  - $P: 3$ 是素数：
  - $Q: 3$ 是奇数。
  - $P \wedge Q: 3$ 既是素数又是奇数。

$$
\begin{array}{cc|c}
P & Q & P \wedge Q \\
\hline 0 & 0 & 0 \\
\hline 0 & 1 & 0 \\
\hline 1 & 0 & 0 \\
\hline 1 & 1 & 1
\end{array}
$$

- “ $\wedge$ "是自然语言中的 “并且”、“既...又...”、**“但”**、“和”、“与”、“不仅...而且”、**“虽然...但是...”**、“一面...，一面...”等的逻辑抽象
    -	今天天气很冷，**但**室内很暖和
        -	天气冷 $\wedge$ 室内暖和
    -	但不是所有的"和"，“与”都要使用合取联结词表示，要根据句子的语义进行分析
        -	2 **和** 3 的最小公倍数是 6；
            -	简单命题不可拆分
        -	点 a 位于点 b **与**点 c 之间
            -	简单命题不可拆分



### 析取联结词

- 设$P 、 Q$ 是任意两个命题，复合命题“ $P$ 或 $Q$ "称为 $P$ 与 $Q$ 的**析取式**(disjunction)，记作 $P \vee Q$， **" $\vee$ "** 为析取联结词。
-  $P \vee Q$ 为真当且仅当 $P, Q$ 至少有一个为真。

$$
\begin{array}{cc|c}
P & Q & P \vee Q \\
\hline 0 & 0 & 0 \\
\hline 0 & 1 & 1 \\
\hline 1 & 0 & 1 \\
\hline 1 & 1 & 1 \\
\hline
\end{array}
$$

- 联结词 “$\vee$” 是自然语言中的 **“或"**、**“或者"** 等的逻辑抽象。自然语言中的 “或" 有 “**可兼或**"(或称为同或)、“**不可兼或**"(即异或) 两种。
- 严格来讲，析取联结词实际上代表的是可兼或，**异或**有时会使用单独的异或联结词 “ $\oplus "$ 或 “ $\overline{\vee}$ " 来表示。
  - 命题：张红生于1982年或1983年，令
    - $P$: 张红生于 1982 年;
    - $Q$: 张红生于 1983 年;
  - $P$ 与 $Q$ 不能同时为真，即为 “不可兼或"
  - 这门课中并没有引入异或联结词，所以不会很严格要求，使用或即可



### 蕴含联结词

- 设 $P 、 Q$ 是任两个命题，复合命题 “如果 $P,$ 则 $Q$ " 称为 $P$ 与 $Q$ 的**蕴涵式**(implication)，记作$P \rightarrow Q$， " $\rightarrow$ " 为蕴涵联结词。
- $P \rightarrow Q$ 为假当且仅当 $P$ 为真且 $Q$ 为假。
- 一般把蕴涵式 $P \rightarrow Q$ 中的 $P$ 称为该蕴涵式的前件，Q 称为蕴涵式的后件
  - $P:$ 周末天气晴朗
  - $Q$ : 我们将到郊外旅游
  - $P \rightarrow Q$ : 如果周末天气晴朗，则我们将到郊外旅游

$$
\begin{array}{cc|c}
P & Q & P \rightarrow Q \\
\hline 0 & 0 & 1 \\
\hline 0 & 1 & 1 \\
\hline 1 & 0 & 0 \\
\hline 1 & 1 & 1
\end{array}
$$

- 在自然语言中，前件为假，不管结论真假，整个语句的意义，往往无法判断。但对于数理逻辑中的蕴涵联结词来说，**当前件 $\mathrm{P}$ 为假时**，不管 $Q$ 的真假如何，则 **$P \rightarrow Q$ 都为真**。此时称为“**善意推定**"。
  - 命题：如果角 A 和角 B 是对顶角，则角 A 等于 角 B。
    - 这个命题是我们非常熟悉的一个定理，当然是真命题
    - 当前件为假时，这个定理依然成立

#### 实例

- 设 $P$：约翰学习微积分，$Q$：约翰是大学一年级学生。则以下的复合命题均可用 $P \rightarrow Q$ 表示。
1. 如果约翰学习微积分，则他是大学一年级学生。**如果 $P$，所以$Q$**
  2. 因为约翰学习微积分，所以他是大学一年级学生。**因为 $P$，所以$Q$**
  3. 只要约翰学习微积分，他就是大学一年级学生。**只要 $P$，就$Q$**
  4. 约翰学习微积分仅当他是大学一年级学生。**$P$ 仅当 $Q$**
  5. 只有约翰是大学一年级学生，他才能学习微积分。**只有 $Q$， 才 $P$**
  6. 除非约翰是大学一年级学生，他才能学习微积分。**除非 $Q$，才 $P$**
  7. 除非约翰是大学一年级学生，否则他不学习微积分。**除非 $Q$， 否则$\neg P$**



### 等价联结词

- 设 $P 、 Q$ 是任两个命题，复合命题“ $P$ 当且仅当 $Q$ "称为 $P$ 与 $Q$ 的**等价式**(equivalence)，记 作 $P \leftrightarrow Q，$ "$\leftrightarrow$“ 为等价联结词(也称作双条件联结词)。
-  $P \leftrightarrow Q$ 为真当且仅当 $P 、 Q$ 同为真假。
  - $P:$ 两个三角形全等
  - $Q:$ 三角形的三条边全部相等
  - $P \leftrightarrow Q:$ 两个三角形全等当且仅当三角形的三条边全部相等

$$
\begin{array}{cc|c}
P & Q & P \leftrightarrow Q \\
\hline 0 & 0 & 1 \\
\hline 0 & 1 & 0 \\
\hline 1 & 0 & 0 \\
\hline 1 & 1 & 1
\end{array}
$$

- "$\leftrightarrow$"是自然语言中的”等价“、”充分必要条件“、”当且仅当“等的逻辑抽象



### 总结


$$
\begin{array}{cc|c|c|c|c|c}
P & Q & \neg P & \text { P } \wedge Q & P \vee Q & P \rightarrow Q & P \leftrightarrow Q \\
\hline 0 & 0 & 1 & 0 & 0 & 1 & 1 \\
\hline 0 & 1 & 1 & 0 & 1 & 1 & 0 \\
\hline 1 & 0 & 0 & 0 & 1 & 0 & 0 \\
\hline 1 & 1 & 0 & 1 & 1 & 1 & 1 \\
\hline
\end{array}
$$

- 联结词是**两个命题真值之间的联结**，而不是命题内容之间的连接，因此符合命题的真值只取决于构成他们的各简单命题的真值，而与它们的内容无关，与二者之间是否有关系无关
  - 雪是白的当且仅当北京是中国的首都
    - 真 $\rightarrow$ 真，结果为真
  - 如果2是偶数，则天上就可以掉馅饼
    - 真 $\rightarrow$ 假，结果为假



### 命题联结词的优先级

- 所有五个联结词的优先顺序为：否定，合取，析取，蕴含，等价
  - 单目＞双目
  - && > \|\|
  - 等价最后
- 同级的联结词，按其出现的先后次序（从左到右）
- 若运算要求与优先次序不一致时，可使用括号；同级符号相邻时，也可以使用括号
  - 括号中的运算为最高优先级



## 命题符号化及其应用


$$
{\Large 设命题}
\begin{cases}
   P:你陪伴我;
 \\Q:你代我叫辆车子;
 \\R:我将出去;
\end{cases}
$$

- 符号化下属语句：

  - **如果**你陪伴我**并且**代我叫辆车子，**则**我将出去
- 符号化为：$(P \wedge Q) \rightarrow R$
  - **如果**你**不**陪伴我**或不**代我叫辆车子，我将**不**出去
    - 符号化为：$(\neg P \vee \neg Q) \rightarrow \neg R$
  - 除非你陪伴我或代我叫辆车子，否则我将不出去
    - 符号化为：$R \rightarrow(P \vee Q) \text { 或 }(\neg P \wedge \neg Q) \rightarrow \neg R$
    - 前者为，”如果我出去，你就要陪伴我或代我叫车子“，”否则“本应为''$\neg$“，但命题中本来就是$\neg R$，双重否定变肯定，结果是$R$
    - 后者为，”如果你不陪伴**并且**不代我叫辆车子，则我将不出去“



### 逻辑电路应用

- 命题联结词" $\wedge$ "、"$ \vee $"、” $\neg$ “ 对应与门、或门和非门电路，从而命题逻辑是计算机硬件电路的表示、分析和设计的重要工具



### 网页检索应用

- 在**布尔检索**中，联接词 “ $\wedge$ " ( 一般用 AND 表示 ) 用于匹配包含两个检索项的记 录，联接词 “ $\vee$ " ( 一般用 OR 表示 ) 用于匹配包含两个检索项至少一个的记录， 而联接词 “ $\neg$ "（一般用 NOT 表示 ) 用于排除某个特定的检索项。

### 位运算应用

- 计算机中的信息采用二进制的方式来表达。每个二进制位只能是 1 和 0 ，可对应于某一个布尔变量的真值。当我们需要判断该布尔变量的真值时，就可以利用**按位与**(bitwise AND)或**按位或**(bitwise OR)以及**按位取反**(bitwise NOT)等来操作



## 命题公式和真值表



### 命题变元

- 一个特定的命题的一个常值命题，它不是具有值" T " (" 1 ")，就是具有值 " F " (" 0 ")
- 一个任意的没有赋予具体内容的**原子命题**是一个变量命题，常称它为**命题变量（或命题变元）**，该命题变量**无具体的真值**，它的变域是集合{ T , F }（或 { 0 , 1 }）
- 复合命题是由原子命题与联结词构成的命题。所以，当其中的原子命题是命题变元时，此复合命题也即为命题变元的函数，且该函数的值仍为”真“或”假“值，这样的函数可形象地称为”真值函数“或”命题公式“，此命题公式没有确切的真值。
  - 例如：$G=P \wedge Q \rightarrow \neg R$



### 命题公式

- 命题验算的合成公式，又称命题公式（简称公式），按如下规则生成：
  1. 命题变元本身是一个公式；
     - $P, Q, R, \cdots$
  2. 如 $G$ 是公式, 则 $(\neg G)$ 也是公式
     -  $\neg P, \neg Q, \neg R, \cdots$
  3. 如 $G, H$ 是公式, 则 $(G \wedge H)$，$(G \vee H)$，$(G \rightarrow H)$，$(G \leftrightarrow H)$ 也是公式；
     - $P \wedge Q,(\neg Q) \rightarrow R, \cdots$
  4. 仅由**有限步使用规则** (1) 、(2)、(3) 后所得到的包含命题变元、联结词和括号的符号串才是命题公式
     -  $\neg(P \wedge Q) \leftrightarrow R,(\neg Q \vee(P \wedge \neg R)) \rightarrow R, \cdots$

- 如果 $G$ 是含有 $n$ 个命题变元 $P_{1}, P_{2}, P_{3}, \cdots, P_{n}$ 的公式，可记为 
- $G\left(P_{1}, P_{2}, P_{3}, \cdots, P_{n}\right)$ 或简写为 $G$。



### 关于命题公式的说明

- 原子命题变元是最简单的合成公式，称为原子合成公式，简称原子公式
- 命题公式没有真值，只有对其命题变元进行真值指派后，方可确定命题公式的真值
- 整个公式的最外层括号可以省略；公式中不影响运算次序的括号也可以省略
- 在实际应用中，为了便于存储和运算，命题公式常用二元树的方式来表达



### 公式的解释

- 设 $P_{1}, P_{2}, P_{3}, \cdots, P_{n}$ 是出现在公式 $G$ 中的**所有命题变元**，指定 $P_{1}, P_{2}, P_{3}, \cdots, P_{n}$ 一组真值，则这组真值称为 $G$ 的一个**解释**，常记为 $I$
- 设有公式 $: G=P \rightarrow(\neg Q \wedge R)$
   - $I_{1}: P=0, Q=1, R=0$ 是 $G$ 的一个解释，使得 $G$ 的真值为 1 
   - $I_{2}: P=1, Q=0, R=0$ 是 $G$ 的一个解释，使得 $G$ 的真值为 0 

- 如果公式 $G$ 在解释 $I$ 下是真的，则称 $I$ 满足 $G$，此时 $I$ 是 $G$ 的成真赋值；如果 $G$ 在解释 $I$ 下是假的，则称 $I$ 弄假于 $G$，此时 $I$ 是 $G$ 成假赋值



### 真值表

#### 定义

- 一般来说，若有 $n$ 个命题变元，则应有 $2^{n}$ 个不同的解释
- 利用真值表，可得到公式的所有成真赋值和成假赋值



- 由公式 $G$ 在其所有可能的解释下所取真值构成的表，称为 $G$ 的真值表(truth table)。
  - 一般我们将公式中的命题变元放在真值表的左边，将公式的结果放在真值表的右边
  - 有时为了清楚起见，可将求公式的中间结果也放在真值表中



#### 实例

- 设有公式 $: G=(P \rightarrow((\neg P \leftrightarrow Q) \wedge R)) \vee Q,$ 则 $G$ 的真值表为：

|$P$|$Q$|$R$|$\neg P$|$\neg P \leftrightarrow Q$|$(\neg P \leftrightarrow Q) \wedge R$|$P \rightarrow((\neg P \leftrightarrow Q) \wedge R)$|$G$|
|-|-|-|-|-|-|-|-|
|0|0|0|1|0|0|1|1|
|0|0|1|1|0|0|1|1|
|0|1|0|1|1|0|1|1|
|0|1|1|1|1|1|1|1|
|1|0|0|0|1|0|0|0|
|1|0|1|0|1|1|1|1|
|1|1|0|0|0|0|0|1|
|1|1|1|0|0|0|0|1|



## 命题公式的分类和等价



### 命题公式和分类

- 公式 $G$ 称为**永真公式**(重言式, tautology)，如果在它的所有解释之下其真值都为 "真"。
- 公式 $G$ 称为**永假公式**(矛盾式, contradiction)，如果在它的所有解释之下其真值都为“假"。 有时也称永假公式为**不可满足公式**。

- 公式 $G$ 称为**可满足公式**(satisfiable)，如果它不是永假的。



- 三种特殊公式之间的关系
  - $G$ 是永真的当且仅当 $\neg G$ 是永假的 ;
  - $G$ 是可满足的当且仅当至少有一个解释 $I$ 使 $G$ 在 $ I$ 下为真。
  - 若 $G$ 是永真式, 则 $G$ 一定是可满足式，但反之可满足公式不一定是永真式



### 公式的等价

- 设 $G, H$ 是两个命题公式, $P_{1}, P_{2}, P_{3}, \ldots, P_{n}$ 是出现在 $G, H$ 中所有的命题变元，如果对于 $P_{1}, P_{2}, P_{3}, \cdots, P_{n}$ 的 $2^{n}$ 个解释，G 与 $H$ 的真值结果都相同，则称公式 $G$ 与 $H$ 是等价的， 记作 $G=H_{0} \quad($ 或 $G \Leftrightarrow H)$

  - 此处的双箭头双向符是一个表示关系的符号，并不是计算符号

- 永真公式 $，G_{1}=(P \rightarrow Q) \leftrightarrow(\neg P \vee Q)$，将这个公式拆开，令
  $$
  G=P \rightarrow Q, H=\neg P \vee Q
  $$
  从而 $G_{1}=G \leftrightarrow H,$ 由于 $G_{1}$ 是永真公式，根据等价联接词的定义可知 $G, H$ 必同为真或者 同为假。此时我们称公式 $G, H$ 具有逻辑等价关系

  - 此处的单箭头双向符是一个运算公式



### 公式等价的充分必要调教

- 对于任意两个公式 $G$ 和 $H$，$G=H$ 的充分必要条件是公式 $G \leftrightarrow H$ 是永真公式

- 证明
  - 必要性：假定 $G=H$, 则 $G, H$ 在其任意解释 $I$ 下或同为真或同为假，于是由 “ $\leftrightarrow$ "的意义知，公式 $G \leftrightarrow H$ 在其任何的解释 $I$ 下，其真值为 “真"，即 $G \leftrightarrow H$ 为永真公式。
  - 充分性：假定公式 $G \leftrightarrow H$ 是永真公式， $I$ 是它的任意解释，在 $I$ 下，IG\leftrightarrowH 为真，因此，G, H$ 或同为真，或同为假，由于 $I$ 的任意性，故有 $G=H_{\circ}$
- 命题公式的可判定性
  - 可判定性: 能否给出一个可行方法，完成对任意公式的判定类问题。( 类型或等价判定 ) 命题公式是可判定的。



## 基本等价关系及其应用



### 基本等价关系



设 $G, H, S$ 为任意的命题公式

#### 幂等律

$E_{1}: G \vee G=G$
$E_{2}: G \wedge G=G$

#### 交换律

$E_{3}: G \vee H=H \vee G$
$E_{4}: G \wedge H=H \wedge G$

#### 结合律

$E_{5}: G \vee(H \vee S)=(G \vee H) \vee S$
$E_{6}: G \wedge(H \wedge S)=(G \wedge H) \wedge S $

#### 同一律

$E_{7}: G \vee 0=G$
$E_{8}: G \wedge 1=G$

#### 零律

- 多用于化简

$E_{9}: G \vee 1=1$
$E_{10}: G \wedge 0=0$

#### 分配率

- 多用于公式的变形

$E_{11}: G \vee(H \wedge S)=(G \vee H) \wedge(G \vee S)$
$E_{12}: G \wedge(H \vee S)=(G \wedge H) \vee(G \wedge S)$

#### 吸收律

- 多用于化简、证明

$E_{13}: G \vee(G \wedge H)=G$
$E_{14}: G \wedge(G \vee H)=G$

#### 矛盾律

- 常与同一律放一起使用

$E_{15}: \neg G \wedge G=0$

#### 排中律

- 常与同一律一起使用

$E_{16}: \neg G \vee G=1$

#### 双重否定律

$E_{17}: \neg(\neg G)=G$

#### 德摩根律

- 用于公式的变形

$E_{18}: \neg(G \vee H)=\neg G \wedge \neg H$
$E_{19}: \neg(G \wedge H)=\neg G \vee \neg H .$

#### 蕴含式

- 用于公式的变形，常用

$E_{20}: G \rightarrow H=\neg G \vee H$

#### 假言易位

- 即为逆否命题的形式
- 原命题和逆否命题等价

$E_{21}: G \rightarrow H=\neg H \rightarrow \neg G$

#### 等价式

$E_{22}: G \leftrightarrow H=(G \rightarrow H) \wedge(H \rightarrow G)=(\neg G \vee H) \wedge(\neg H \vee G) $

#### 等价否定式

$E_{23}: G \leftrightarrow H=\neg G \leftrightarrow \neg H_{I}$

#### 归谬论

- 即为反证法

$E_{24}:(G \rightarrow H) \wedge(G \rightarrow \neg H)=\neg G$



### 判断公式类型

利用命题公式的基本等价关系，证明 $(P \rightarrow Q) \wedge P \rightarrow Q$ 是重言式

证明：

$=(\neg P \vee Q) \wedge P \rightarrow Q=\neg((\neg P \vee Q) \wedge P) \vee Q \quad$( 蕴含式 $)$

$=(\neg(\neg P \vee Q) \vee \neg P) \vee Q=((P \wedge \neg Q) \vee \neg P) \vee Q \quad($ 德摩根律 $)$

$=((P \vee \neg P) \wedge(\neg Q \vee \neg P)) \vee Q$（ 分配率 ）

$=(1 \wedge(\neg Q \vee \neg P)) \vee Q$ $（$ 排中律 $）$

$=(\neg Q \vee \neg P) \vee Q \quad$ ( 同一律 $)$

$=(\neg Q \vee Q) \vee \neg P$ ( 结合律，交换律 )

$=1 \vee \neg P \quad($ 排中律 $)$

$=1$（ 零律 ）



### 证明公式等价

利用命题公式的基本等价关系，证明 $P \rightarrow(Q \rightarrow R)=(P \wedge Q) \rightarrow R$

证明：

$P \rightarrow(Q \rightarrow R)$

$=\neg P \vee(Q \rightarrow R)$（ 蕴含式 ）

$=\neg P \vee(\neg Q \vee R)$（ 蕴含式 ）

$=(\neg P \vee \neg Q) \vee R$（ 结合律 ）

$=\neg(P \wedge Q) \vee R$（ 德摩根律）

$=(P \wedge Q) \rightarrow R$（ 蕴含式 ）



### 开关电路化简

利用命题公式的基本等价关系，化简如下所示开关电路

![](/img-post/2021-01-14-Discrete_mathematics/s8Y3Q6trXiU4dZBP6QSAwviaW-xHqSqz5K_zoR_XkwY.original.fullsize.png)

- 解：

  $\begin{aligned} &((P \wedge Q \wedge R) \Psi(P \wedge Q \wedge S)) \wedge((P \wedge R) \vee(P \wedge S)) \\=&(P \wedge Q \wedge(R \vee S)) \wedge(P \wedge(R \vee S)) \\=& P \wedge Q \wedge(R \vee S) \wedge P \wedge(R \vee S) \\=& P \wedge Q \wedge(R \vee S) \end{aligned}$

- 化简

![](/img-post/2021-01-14-Discrete_mathematics/gVPgmIdMeItkg1XPP7wSDSM8Bj-Xts4gtYI-mkNmaj0.original.fullsize.png)



### 逻辑电路化简

利用命题公式的基本等价关系，化简如下所示逻辑电路

![](/img-post/2021-01-14-Discrete_mathematics/i8GiScTDO78i_5T82CewrUW5pKmcD1GqpxQVQTOYdk8.original.fullsize.png)

- 解

  $\begin{aligned} &((P \wedge Q \wedge R) \vee(P \vee Q \vee S)) \wedge(P \wedge S \wedge T) \\=&(P \vee Q \vee S) \wedge(P \wedge S \wedge T) \\=& P \wedge S \wedge T \end{aligned}$

- 化简

![](/img-post/2021-01-14-Discrete_mathematics/jaItru6mCJvYOSu3up9N_yb5hIrRnMJTcj9oB6KtClE.original.fullsize.png)



### 智力游戏

侦探调查了罪案的四位证人。从证人的话侦探得出的结论是：如果男管家说的是真话，那么時师说的也是真话 ; 厨师和园丁说的不可能都是真话 ; 园丁和杂役不可能都在说慌：如果杂役说真话，那么厨师在说慌。侦探能判定这四位证人分别是在说慌还是在说真话吗？解释你的推理。

解： 

​	令命题 $P:$ 男管家说的是真话 $; Q:$ 廚师说的是真话 $; R ：$ 园丁说的是真话： S：杂役说的是真话。则将上述已知条件符号化并列出真值表，选区真值结果全为真的行如下表：

| $P$  | $Q$  | $R$  | $S$  | $P \rightarrow Q$ | $\neg(Q \wedge R)$ | $\neg(\neg R \wedge \neg S)$ | $S \rightarrow \neg Q$ |
| ---- | ---- | :--: | :----: | :---------------: | :----------------: | :----------------------------: | :----------------------: |
| 0    | 0    |  0   | 1    |         1         |         1          | 1                            | 1                      |
| 0    | 0    |  1   | 0    |         1         |         1          | 1                            | 1                      |
| 0    | 0    |  1   | 1    |         1         |         1          | 1                            | 1                      |

​	可见，我们能确定 $P$, $Q$ 必然为假，但无法确定 $R$ 和 $S$ 的值，因而侦探只能判定男管家和時师在说慌，但 无法判定园丁与杂役谁在说真话。



## 范式



### 范式定义

真值表能够方便的给出命题公式的真值情况，但真值表的规模随命题变元的数量 呈指数形式增长，因而我们考虑一种真值表的替代方法，这种方法是基于命题公 式的一种标准形式。

- 引入范式
  - 命题变元或命题变元的否定称为文字。 $P, \neg P, Q, \neg Q, \cdots$
  - **有限个**文字的析取称为简单析取式(或子句)。 $P \vee Q \vee \neg R, \cdots \quad P, \neg P$
  - **有限个**文字的合取称为简单合取式(或短语)。 $\neg P \wedge Q \wedge R, \cdots \quad P, \neg P$
    - 有限个包括一个，只有一个时不需要联结词
  - $P$ 与 $\neg P$ 称为**互补对**

- **有限个**简单合取式（短语 $)$ 的析取式称为**析取范式**(disjunctive normal form)
  - 如 $(P \wedge Q) \vee(\neg P \wedge Q),$ 又如 $P \wedge \neg Q, P, \neg P$
- **有限个**简单析取式 ( 子句 ) 的合取式称为**合取范式**(fconjunctive normal form)
  - 如 $(P \vee Q) \wedge(\neg P \vee Q),$ 又如 $P \vee \neg Q, P, \neg P$
- 单独的短语和字句也可以构成范式
  - $P, \neg P$ 是文字，短语，子句，析取范式，合取范式
  - $P \vee Q \vee \neg R$ 是子句，合取范式，析取范式; 
    - $(P \vee Q \vee \neg R)$ 是子句，合取范式
    - 整体为一个子句，不能被当成有限个短语的析取式了
  - $\neg P \wedge Q \wedge R$ 是短语，析取范式，合取范式
    -  $(\neg P \wedge Q \wedge R)$ 是短语，析取范式。
    - 整体为一个短语
  - $P \vee(Q \vee \neg R)$ 即不是析取范式也不是合取范式
    - 但转换为 $P \vee Q \vee \neg R$ 后，即是析取范式和合取范式

- 总结
  - 范式关注的是命题公式的当前书写形式
    - 一种强制统一的形式
  - 单个的文字是子句、短语、析取范式、合取范式
  - 析取范式、合取范式仅含联结词集 $\{\neg, \Lambda, \vee\},$ 且否定联接词仅出现在命题 变元之前



### 范式存在定理

- 对于任意命题公式，都存在与其等价的析取范式和合取范式



### 范式求解

由于联结词之间可以通过命题公式的基本等价关系进行相互的转换，所以可通过逻辑等价公式求出等价于它 的析取范式和合取范式，具体步骤如下：

1. 将公式中的 $\rightarrow, \leftrightarrow$ 用联结词 $\neg, \wedge, \vee$ 来取代：
   - $E_{20}: G \rightarrow H=\neg G \vee H$（蕴含式）
   - $E_{22}: G \leftrightarrow H=(G \rightarrow H) \wedge(H \rightarrow G)=(\neg G \vee H) \wedge(\neg H \vee G)$（等价式）

2. 将否定联结词移到各个命题变元的前端，并消去多余的否定号：
   - $E_{17}: \neg(\neg G)=G$（双重否定率）
   - $E_{18}: \neg(G \vee H)=\neg G \wedge \neg H$（德摩根律）
   - $E_{19}: \neg(G \wedge H)=\neg G \vee \neg H$
3. 利用分配律，可将公式化成一些合取式的析取，或化成一些析取式的合取：
   - $E_{11}: G \vee(H \wedge S)=(G \vee H) \wedge(G \vee S)$（分配率）
   - $E_{12}: G \wedge(H \vee S)=(G \wedge H) \vee(G \wedge S)$

对任意一个公式，经过以上步骤，必能化成与其等价的析取范式和合取范式



#### 实例

求公式 $(P \rightarrow \neg Q) \vee(P \leftrightarrow R)$ 的析取范式和合取范式

解：

​	$(P \rightarrow \neg Q) \vee(P \leftrightarrow R)$

$=(\neg P \vee \neg Q) \vee((\neg P \vee R) \wedge(\neg R \vee P))$

$=((\neg P \vee \neg Q) \vee(\neg P \vee R)) \wedge((\neg P \vee \neg Q) \vee(\neg R \vee P))$

$=(\neg P \vee \neg Q \vee \neg P \vee R) \wedge(\neg P \vee \neg Q \vee \neg R \vee P)$

$=((\neg P \vee \neg P) \vee \neg Q \vee R) \wedge((\neg P \vee P) \vee \neg Q \vee \neg R)$

$=(\neg P \vee \neg Q \vee R) \wedge(1 \vee \neg Q \vee \neg R)$

$=(\neg P \vee \neg Q \vee R) \wedge 1$

$=(\neg P \vee \neg Q \vee R)$（合取范式）

$=\neg P \vee \neg Q \vee R$（析取范式）



#### 总结

1. 命题公式的析取范式可以指出公式何时为真，而合取范式可以指出公式何时 为假，从而能够替代真值表。 $((\neg P \vee Q) \wedge(P \vee \neg R), \neg P \vee(\neg Q \wedge R))$
   - $(\neg P \vee Q) \wedge(P \vee \neg R)$
     - 左侧为假，即 $P$ 真 $Q$ 假时，整个公式为假，此时不用关注 $R$ 的值
     - 右侧为假，即 $P$ 假 $R$ 真时，整个公式为假，此时不管关注 $Q$ 的值
   - $\neg P \vee(\neg Q \wedge R)$
     - 左侧为真，即 $P$ 为假时，整个公式为真，不需要关注右侧
     - 右侧为真，即 $Q$ 假 $R$ 真时，整个公式为真，不需要关注左侧
2. 命题公式的范式表达并不唯一，比如对公式 $(P \vee Q) \wedge(P \vee R)$ 而言，对应的 析取范式有很多：
   - $P \vee(Q \wedge R)$
   - $(P \wedge P) \vee(Q \wedge R)$
   - $P \vee(Q \wedge \neg Q) \vee(Q \wedge R)$
   - $P \vee(P \wedge R) \vee(Q \wedge R)$
3. 一半而言，求解范式时，需要进行最后的化简步骤



## 主范式

### 引入

- 由于范式的不唯一性，我们考虑对构成范式的子句或短语进一步规范化，从而形成唯一的主析取范式和主合取范式

### 极小项和极大项

#### 定义

- 在含有 $n$ 个命题变元 $P_{1}, P_{2}, P_{3}, \cdots, P_{n}$ 的**短语或子句**中，若每个命题变元与其否定不同时存在， 但二者之一恰好出现一次且仅一次，并且出现的次序与 $P_{1}, P_{2}, P_{3}, \cdots, P_{n}$ 一致，则称此短语或 子句为关于 $P_{1}, P_{2}, P_{3}, \cdots, P_{n}$ 的一个**极小项或极大项**
- 一般来说，若有 $n$ 个命题变元，则应有 $2^{n}$ 个不同的极小项和 $2^{n}$ 个不同的极大项

| $P$  |  $Q$ | $\neg P \wedge \neg Q$ | $\neg P \wedge Q$ | $P \wedge \neg Q$ | $P \wedge Q$ |
| :----: | :---: | :----------------------: | :-----------------: | :-----------------: | :------------: |
| 0    |    0 | 1                      | 0                 | 0                 | 0            |
| 0    |    1 | 0                      | 1                 | 0                 | 0            |
| 1    |    0 | 0                      | 0                 | 1                 | 0            |
| 1    |    1 | 0                      | 0                 | 0                 | 1            |
| / | / | $m_{00}\left(m_{0}\right)$ | $m_{01}\left(m_{1}\right)$ | $m_{10}\left(m_{2}\right)$ | $m_{11}\left(m_{3}\right)$ |

- 没有两个不同的极小项是等价的
- 每个极小项只有一组成真赋值，因此可用于给极小项编码
  - 编码规律为：命题变元 与 1 对应，命题变元的否定与 0 对应
  - 括号外为二进制，括号内为十进制，常用十进制表示

| $P$  | $Q$  |    $\neg P \vee \neg Q$    |      $\neg P \vee Q$       |      $P \vee \neg Q$       |         $P \vee Q$         |
| :--: | :--: | :------------: | :------------------------: | :------------------------: | :------------------------: |
|  0   |  0   |             1              |             1              |             1              |             0              |
|  0   |  1   |             1              |             1              |             0              |             1              |
|  1   |  0   |             1              |             0              |             1              |             1              |
|  1   |  1   |             0              |             1              |             1              |             1              |
|  /   |  /   | $M_{11}\left(M_{3}\right)$ | $M_{10}\left(M_{2}\right)$ | $M_{01}\left(M_{1}\right)$ | $M_{00}\left(M_{0}\right)$ |

- 没有两个不同的极大项是等价的。
- 每个极大项只有一组成假赋值，因此可用于给极大项编码
  - 编码规律为：命题变元与 0 对应，命题变元的否定与 1 对应

#### 实例

- 设有 $P, Q, R$ 三个命题变元，给出以下极小项和极大项的编码：
	- $ \neg P \wedge Q \wedge R: \quad m_{011}\left(m_{3}\right)$
	- $P \wedge \neg Q \wedge R: \quad m_{101}\left(m_{5}\right)$
	- $\neg P \vee Q \vee R: \quad M_{100}\left(M_{4}\right)$
	- $P \vee \neg Q \vee R: \quad M_{010}\left(M_{2}\right)$

- 根据编码给出相应的极小项或极大项：
  - $m_{6}=m_{110}=P \wedge Q \wedge \neg R$
  - $M_{6}=M_{110}=\neg P \vee \neg Q \vee R$

- 注意：极小项和极大项的编码方式刚好相反，不要混淆



#### 极小项和极大项的性质

| $P$  | $Q$  | $R$  |                   极小项                   |                 极大项                 |
| :--: | :--: | :--: | :----------------------------------------: | :------------------------------------: |
|  0   |  0   |  0   | $m_{0}=\neg P \wedge \neg Q \wedge \neg R$ |        $M_{0}=P \vee Q \vee R$         |
|  0   |  0   |  1   |   $m_{1}=\neg P \wedge \neg Q \wedge R$    |      $M_{1}=P \vee Q \vee \neg R$      |
|  0   |  1   |  0   |   $m_{2}=\neg P \wedge Q \wedge \neg R$    |      $M_{2}=P \vee \neg Q \vee R$      |
|  0   |  1   |  1   |      $m_{3}=\neg P \wedge Q \wedge R$      |   $M_{3}=P \vee \neg Q \vee \neg R$    |
|  1   |  0   |  0   |   $m_{4}=P \wedge \neg Q \wedge \neg R$    |      $M_{4}=\neg P \vee Q \vee R$      |
|  1   |  0   |  1   |      $m_{5}=P \wedge \neg Q \wedge R$      |   $M_{5}=\neg P \vee Q \vee \neg R$    |
|  1   |  1   |  0   |      $m_{6}=P \wedge Q \wedge \neg R$      |   $M_{6}=\neg P \vee \neg Q \vee R$    |
|  1   |  1   |  1   |        $m_{7}=P \wedge Q \wedge R$         | $M_{7}=\neg P \vee \neg Q \vee \neg R$ |

1. $m_{i} \wedge m_{j}=0$
$M_{i} \vee M_{j}=1$
$(i \neq j)$

2. $m_{i}=\neg M_{i}$
   $M_{i}=\neg m_{i}$

3. $\bigvee_{i=0}^{2^n-1}m_i=1$

   $\bigwedge_{i=0}^{2^n-1}M_i=0$



### 主范式定义

- 在给定的析取范式中，若每一个短语都是极小项，且按照编码从小到大的顺序排 列，则称该范式为**主析取范式**(principal disjunctive normal form)
- 在给定的合取范式中，若每一个子句都是极大项，且按照编码从小到大的顺序排 列，则称该范式为**主合取范式**(principal conjunctive normal form)
- 如果一个主析取范式不包含任何极小项，则称该主析取范式为“空" ; 如果一个主 合取范式不包含任何极大项，则称主合取范式为 “空"
- 任何一个公式都有与之等价的主析取范式和主合取范式



### 主范式求解定理

#### 公式转换法

1. 求出该公式所对应的**析取范式和合取范式**
2. 消除重复出现的**命题变元、矛盾式或重言式**
   - $E_{1}: G \vee G=G ; E_{2}: G \wedge G=G .($ 肯等律 $) E_{15}: \neg G \wedge G=0 .$ (矛盾律)
     $E_{7}: G \vee 0=G ; E_{8}: G \wedge 1=G .($ 同一律 $) E_{16}: \neg G \vee G=1 .$ (排中律 $)$
     $E_{9}: G \vee 1=1 ; E_{10}: G \wedge 0=0 .$ (零律)
3. 若析取 ( 合取) 范式的某一个短语 ( 子句 ) $B_{i}$ 中缺少命题变元 $P$, 则可用如下方式将 $P$ 补进去**（缺谁补谁）**：
   - $B_{i}=B_{i} \wedge 1=B_{i} \wedge(\neg P \vee P)=\left(B_{i} \wedge \neg P\right) \vee\left(B_{i} \wedge P\right) $
   - $B_{i}=B_{i} \vee 0=B_{i} \vee(\neg P \wedge P)=\left(B_{i} \vee \neg P\right) \wedge\left(B_{i} \vee P\right)$
   - 重复至所有短语或子句都是标准的极小项或极大项为止

4. 利用**幂等律**将重复的**极小项和极大项合并**，并利用交换律进行顺序调整，由此可转换成标准的主析取范 式和主合取范式
   - $E_{1}: G \vee G=G ; E_{2}: G \wedge G=G$ （幂等律）
   - $E_{3}: G \vee H=H \vee G ; E_{4}: G \wedge H=H \wedge G$（交换律）​

#### 实例

求公式 $(P \rightarrow Q) \rightarrow(Q \wedge R)$ 的主析取范式和主合取范式

解

 1. 求主析取范式

    ​	$(P \rightarrow Q) \rightarrow(Q \wedge R)$

    $=\neg(\neg P \vee Q) \vee(Q \wedge R)$

    $=(P \wedge \neg Q) \vee(Q \wedge R)$	—— 析取范式

    $=(P \wedge \neg Q \wedge(\neg R \vee R)) \vee((\neg P \vee P) \wedge Q \wedge R)$	—— 缺 $R$ 补 $R$ ，缺 $P$ 补 $P$

    $=(P \wedge \neg Q \wedge \neg R) \vee(P \wedge \neg Q \wedge R) \vee(\neg P \wedge Q \wedge R) \vee(P \wedge Q \wedge R)$

    主析取范式： $\left(m_{3} \vee m_{4} \vee m_{5} \vee m_{7}\right)$

	2. 求主合取范式

    ​	$(P \rightarrow Q) \rightarrow(Q \wedge R)$

    $=(P \wedge \neg Q) \vee(Q \wedge R)$

    $=(P \vee Q) \wedge(P \vee R) \wedge(\neg Q \vee Q) \wedge(\neg Q \vee R)$

    $=(P \vee Q) \wedge(P \vee R) \wedge(\neg Q \vee R)$	—— 合取范式

    $\begin{aligned}= &(P \vee Q \vee \neg R) \wedge(P \vee Q \vee R) \wedge(P \vee \neg Q \vee R) \wedge(P \vee Q \vee R) \\  & \wedge(\neg P \vee \neg Q \vee R) \wedge(P \vee \neg Q \vee R) \end{aligned}$

    $=(P \vee Q \vee \neg R) \wedge(P \vee Q \vee R) \wedge(P \vee \neg Q \vee R) \wedge(\neg P \vee \neg Q \vee R)$

    $=(P \vee Q \vee R) \wedge(P \vee Q \vee \neg R) \wedge(P \vee \neg Q \vee R) \wedge(\neg P \vee \neg Q \vee R)$

    主合取范式： $\left(M_{0} \wedge M_{1} \wedge M_{2} \wedge M_{6}\right)$



#### 真值表技术

![](/img-post/2021-01-14-Discrete_mathematics/80j1kODVrjwxB6RmNH1x7okTxISnS6Ypu0xn9NjlZhU.original.fullsize.png)

- 利用真值表技术求主析取范式和主合取范式的简要方法
  - 列出真值表，选出公式的**真值结果为真**的所有的行，在这样的一行中，找到其每一个解释所对应的极小项，将这些**极小项进行析取**即可得到相应的主析取范式
  - 列出真值表，选出公式的**真值结果为假**的所有的行，在这样的每一行中，找到其每一个解释所对应的极大项，再将这些**极大项进行合取**即可得到相对的主合取范式
- 从真值表按所给的算法求出主范式的方法，成为真值表技术



#### 实例

| $P$  | $Q$  | $R$  | $G$  |
| :--: | :--: | :--: | :--: |
|  0   |  0   |  0   |  0   |
|  0   |  0   |  1   |  1   |
|  0   |  1   |  0   |  0   |
|  0   |  1   |  1   |  1   |
|  1   |  0   |  0   |  1   |
|  1   |  0   |  1   |  1   |
|  1   |  1   |  0   |  0   |
|  1   |  1   |  1   |  1   |

- 主析取范式
  - 选出真值为真的行：第 2,4,5,6,8 行，分别对应极小项 $m_{1}, m_{3}, m_{4}, m_{5}, m_{7},$ 这 5 个极小项构成了该公式的主析取范式
  - $G=\neg(P \rightarrow Q) \vee R=$
  	$(\neg P \wedge \neg Q \wedge R) \vee(\neg P \wedge Q \wedge R) \vee (P \wedge \neg Q \wedge \neg R) \vee(P \wedge \neg Q \wedge R) \vee(P \wedge Q \wedge R)$

- 主合取范式
  - 选出真值为假的行：第 1,3,7 行，分别对应极大项 $M_{0}, M_{2}, M_{6},$ 这 3 个极大项构成了该公式的主合取范式
  - $G=\neg(P \rightarrow Q) \vee R=$
    $(P \vee Q \vee R) \wedge(P \vee \neg Q \vee R) \wedge(\neg P \vee \neg Q \vee R)$



#### 范式的互相转化

- 由真值表技术可知，对于任一个命题公式而言，主析取范式所使用的极小项的编码和主合取范式所使用的极大项的编码是 **“互补"** 的关系。从而我们在求主析取范式和主合取范式 时，可根据公式特点，**先求出二者之一，然后可直接写出另一个**



#### 主范式的应用

- 主范式可以用于了解公式的真值情况，进行公式类型的判定预计等价关系的判定
  - 如果主析取范式包含所有的极小项，则该公式为永真公式
  - 如果主合取范式包含所有的极大项，则该公式为永假公式
  - 若两个公式具有相同的主析取范式或主合取范式，则两公式等价

- 某研究所要从 $A, B, C$ 三名科研骨干中挑选 $1-2$ 名出国进修人员，由于工作需要，选派时要满足以下条件： 若 $A$ 去，则 $C$ 同去;若 $B$ 去，则 $C$ 不能去 ; 若 $C$ 不能去，则 $A$ 或 $B$ 可以去。问该如何选派？

  - 设 $P$ : 派 $A$ 去；$Q$：派 $B$ 去；$R$：派 $C$ 去

  - $G=(P \rightarrow R) \wedge(Q \rightarrow \neg R) \wedge(\neg R \rightarrow(P \vee Q))$

    $=(\neg P \wedge \neg Q \wedge R) \vee(\neg P \wedge Q \wedge \neg R) \vee(P \wedge \neg Q \wedge R)$

  - 可见，有三种选派方案

    - $C$ 去，$A,B$ 都不去：

    - $B$ 去， $A, C$ 都不去

    - $A, C$ 同去，$B$ 不去

      





# 集合论基础



## 集合的初见



### 集合论基础

- **集合**是由指定范围内的满足给定条件的所有对象聚集在一起构成，每一个对象成额外这个集合的**元素**
- **集合**是不能精确定义的基本概念。直观来说，把一些事物汇集到一起组成一个整体就称作集合，而这些事物就是这个集合的元素或成员
  - 导致罗素悖论、理发师悖论出现
- ZFC 公理化集合论( Z :策梅洛, F :弗兰克尔, C :选择公理)
  - 外延公理
  - 空集存在公理
  - 无序对公理
  - 并集公理
  - 幂集公理
  - 无穷公理
  - 替换公理
  - 正则公理
  - 选择公理



### 集合定义

- 什么是集合？
  - 所有英文字母
  - 所有小于 100 的正奇数
  - 世界上所有的数学家
  - 天安门广场所有的路灯和树
  - 因为集合的随意性，才会导致很多悖论的出现，最后才有公理化集合论

- 集合的数学符号，通常情况下
  - 用带或不带下标的**大写**英文字母表示**集合**：
    - $A,B,C\cdots$,
    - $A_1,B_1,C_1\cdots$
  - 用带或不带下标的**小写**英文字母表示**元素**：
    - $a,b,c\cdots$
    - $a_1,b_1,c_1\cdots$
- 常用集合
  - 自然数集合 N : 0,1,2,3..
  - 整数集合 Z : ...,-2,-1,0,1,2...
  - 有理数集合 Q 与实数集合 R ,等等

- 属于关系
  - 若$a$是集合 $A$ 中的元素，则称 $a$ 属于 $A$，记为 $a\in A$
  - 若 $a$ 不是集合 $A$ 中的元素，则称 $a$ 不属于 $A$，记为 $a\notin A$



### 集合表示

- 枚举法
  - 列出集合中的全部元素或者仅列出一部分元素，其余用省略号(...)表示
    - $A = \left\{a,b,c,d\right\}$
    - $B = \left\{2,4,6,8,10,\cdots\right\}$
- 叙述法
  - 通过刻画集合中元素所具备的某种性质或特性来表示一个集合
    - $P = \left\{x|P(x)\right\}$
    - $A = \left\{x|x是英文字母中的元音字母\right\}$
    - $P = \left\{x|x \in Z, x< 10\right\}$
    - $P = \left\{x|x=2k,k \in N\right\}$
- 文氏图
  - **文氏图**是利用平面上的点做成对集合的图解方法。一般使用平面上的方形或圆形表示一个集合，而使用平面上的一个小圆点来表示集合的元素



### 集合基数

- 集合 $A$ 中的元素个数称为集合的**基数**(base number),记为 $|A|$
- 若一个集合的基数是有限的，则称该集合为**有限集**(finite set)
  - $A = \left\{a,b,c\right\},|A|=3$
  - $B = \left\{a,\left\{b,c\right\}\right\},|B|=2$
    - $\left\{b,c\right\}$为一个元素
- 若一个集合的基数是无限的，则称该集合为**无限集**(infinite set)



## 特殊集合与集合间关系



### 空集

- 不含任何元素的集合叫做空集(empty set)，记为 $\varnothing$
- 空集可以符号化为 $\varnothing=\left\{x|x\neq x\right\}$
  - $|\varnothing|=0,|\left\{\varnothing\right\}|=1$
    - 前者是一个空集，基数为 $0$
    - 后者空集本身作为集合中的一个元素，故基数为 $1$
- 空集是**绝对唯一**的



### 全集

- 针对一个具体范围，我们考虑的所有对象的集合叫做**全集**(universal set)，记作 $U$ 或 $E$
- 在文氏图中一般使用**方形**表示全集
  - 在立体集合中，全集是由空间的全体点组成的
  - 在我国的人口普查中，全集是由我国所有人组成的
- 全集是**相对唯一**的
  - 在不同的研究范围中全集是不同的
  - 在同一个研究范围内是唯一的



### 集合的相等关系

- 元素的基本特性
  - 集合中的元素是**无序**的
    - $\left\{1,2,3,4\right\}$与$\left\{2,3,1,4\right\}$相同
  - 集合中的元素是**不同**的
    - $\left\{1,2,2,3,4,3,4,2\right\}$与$\left\{2,3,1,4\right\}$相同
      - 虽然第一个集合有 $3$ 个 $2$，$2$ 个 $3$ 和 $4$，但是我们只会把他们当作一个
      - 各个元素互不相同
- **外延性原理**
  - 两个集合 $A$ 和 $B$ 相等，当且仅当它们的**元素完全相同**，记为 $A=B$，否则 $A$ 和 $B$ **不相等**，记为 $A \neq B$



### 包含关系

- 设 $A$、$B$ 是任意两个集合
  - 如果 $B$ 的每个元素都是 $A$ 中的元素，则称 $B$ 是 $A$ 的子集，也称作 $B$ 被 $A$ 包含或 $A$ 包含 $B$，记作 $B\subseteq A$，否则记作 $B\nsubseteq A$
  - 如果 $B\subseteq A$ 并且 $A\neq B$,则称 $B$ 是 $A$ 的真子集，也称作 $B$ 被 $A$ 真包含或 $A$ 真包含 $B$，记作 $B\subset A$，否则记作 $B\not\subset A$  (并非真包含)
- "$\subseteq$" 关系的数学语言描述为：
  -  $B\subseteq A\Leftrightarrow$ 对 $\forall X$，如果$x\in B$,则$x\in A$
    - 常常用于证明题
- 空集是任何集合的子集



### 证明集合相等、关系相等

- **定理**：设 $A、B$ 为任意两个集合

  - 则 $A=B \Leftrightarrow A\subseteq B$ 并且 $B\subseteq A$
  - 这个定理非常重要，这是证明集合相等的一种非常有效的方式

- **证明框架**：
  1. 首先证明 $A\subseteq B$：$\forall x \in A,\cdots x\in B,\therefore A\subseteq B$
  2. 其次证明 $B\subseteq A$：$\forall x \in B,\cdots x\in A,\therefore B\subseteq A$
  - 由以上两点，可知 $A=B$

- **定理**：对于任意 $n$ 元集合 $A$，它的 $m$ 元 $(0 \leq m \leq n)$自己个数为 $\mathrm{C}_n^m$ 个，所以不同的子集个数为：
  - $\mathrm{C}_n^0+\mathrm{C}_n^1+\cdots+\mathrm{C}_n^n$
  - $=(1+1)^n$
  - $=2^n个$
  - 每个元素都有存在和不存在两种可能，所以一共有 $2^n$ 种排列方式



### 幂集

- 设 $A$ 为任意集合，把 $A$ 的**所有不同子集**构成的集合叫做 $A$ 的**幂集**(power set)，记作 $P(A)$，即
  - $P(A)=\left\{x|x\subseteq A\right\}$
  - $x$是$A$的子集
  - $x\in P(A) \Leftrightarrow x \subseteq A$
  - 在**幂集**相关的证明可能会使用到上述定义
- 幂集也叫做**集族**或**集合的集合**，对集族的研究在数学方面、知识库和表处理语言以及人工智能方面都有十分重要的意义

  

## 集合的运算



### 并运算

- 设 $A,B$ 是两个集合，则集合 $A$ 与 $B$ 的**并集**定义为：
  - $A \cup B=\left\{x|x\in A或x \in B\right\}$

### 交运算

- 设 $A,B$ 是两个集合，则集合 $A$ 与 $B$ 的**交集**定义为：
  - $A \cap B=\left\{x|x\in A并且x \in B\right\}$

### 补运算

- 设 $U$ 是全集，则集合 $A$ 的**补集**定义为：
  - $\overline A=\left\{x|x\notin A\right\}$
  - $\sim A=\left\{x|x\notin A\right\}$
- 做补运算是必须要有全集$E$的

### 差运算

- 设 $A,B$ 是两个集合，则集合 $A$ 与 $B$ 的**差集**定义为：
  - $A - B=\{x|x\in A并且x \notin B\}$

### 对称差运算

- 设 $A,B$ 是两个集合，则集合 $A$ 与 $B$ 的**对称差集**定义为：
  - $A \oplus B=\left\{x|(x\in A并且x \notin B)或者(x\notin A并且x \in B)\right\}$
- $A-B$ 或 $B-A$ 的结果

### 运算扩展

- 设 $A_1,A_2,...,A_n$ 是任意 $n$ 个集合，则这 $n$ 个集合的**并集**是包含那些**至少是这组集合中一个集合成员的元素**的集合，即

  - $\bigcup_{i=1}^{n} A_{i}=A_{1} \cup A_{2} \cup \cdots \cup A_{n}$
  - $=\left\{x \mid x \in A_{1}\right.$ 或者 $x \in A_{2} \cdots$ 或者 $\left.x \in A_{n}\right\}$


- 设 $A_1,A_2,...,A_n$ 是任意 $n$ 个集合，则这 $n$ 个集合的**交集**是包含那些**这组集合中所有集合成员的元素**的集合，即
  - $\bigcap_{i=1}^{n}A_i=A_1\cap A_2 \cap \cdots \cap A_n$
  - $=\left\{x\mid x\in A_1并且x\in A_2\cdots 并且x\in A_n\right\}$



## 集合的运算定律



### 运算定律

设 $E$ 为全集，$A,B,C$ 为任意集合

#### 幂等律

- $A \cup A = A$

- $A \cap A = A$

#### 交换律

- $A \cup B = B \cup A$ 

- $A \cap B = B\cap A$

#### 结合律

- $A \cup (B\cup C) = (A \cup B)\cup C$ 

- $A \cap (B\cap C) = (A \cap B)\cap C$ 

#### 同一律

- $A \cup \varnothing = A$

- $A \cap E = A$

#### 零律

- $A \cup E = E$

- $A \cap \varnothing = \varnothing$

#### 分配律

- $A \cup (B\cap C) = (A \cup B)\cap (A \cup C)$

- $A \cap (B\cup C) = (A \cap B)\cup (A \cap C)$ 

#### 吸收律

- $A \cup (A\cap B) = A$ 

- $A \cap (A\cup B) = A$ 

#### 矛盾律和排中律

- $\overline {\cap A} = \varnothing$
- $\overline {\cup A} = E$

#### 双重否定律

- $\overline {\overline A}=A$

#### 德摩根律

- $\overline{A\cup B}=\overline A\cap \overline B$
- $\overline{A\cap B}=\overline A\cup \overline B$
- $A-(B \cup C)=(A-B)\cap (A-C)$
- $A-(B \cup C)=(A-B)\cap (A-C)$

#### 证明公式

- $A-B=A \cap \sim B$
-  $(A-B)\cup B = A \cup B$

### 证明方法

- 举例证明德摩根律：$\overline{A\cup B}=\overline A\cap \overline B$：

1. 首先证明 $\overline{A \cup B} \subseteq \bar{A} \cap \bar{B}$ :
$$
\begin{aligned}
\forall x \in \overline{A \cup B} & \Rightarrow x \notin A \cup B \Rightarrow x \notin A \text { 并且 } x \notin B \\
& \Rightarrow x \in \bar{A} \text { 并且 } x \in \bar{B} \Rightarrow x \in \bar{A} \cap \bar{B}
\end{aligned}
$$
2. 其次证明 $\bar{A} \cap \bar{B} \subseteq \overline{A \cup B} $ :
$$
\begin{aligned}
\forall x \in \bar{A} \cap \bar{B} \quad \Rightarrow x \in \bar{A} \text { 并且 } & x \in \bar{B} \\
\Rightarrow & x \in \overline{A \cup B}
\end{aligned}
$$
3. 由以上两点，可知等式 $\overline{A \cup B}=\bar{A} \cap \bar{B}$ 成立。



## 可数集合与不可数集合



### 自然数集的定义



#### 皮亚诺公理

- 1891年，意大利数学家皮亚诺公开发表了**基于序数**的自然数定义公理。这组公理包括
  1. 0 是自然数：
  2. 每个自然数 $n$ 都有一个后继，这个后继也是一个自然数，记为 $S(n)$;
  3. 两个自然数相等当且仅当它们有相同的后继，即 $m=n$ 当且仅当 $S(m)=S(n) ;$
  4. 没有任何自然数的后继是 0 ;
  5. (归纳公理) 若 $\varphi$ 是关于一个自然数的预测，如果 $\varphi(0)$ 为真 ; 当 $\varphi(n)$ 为真，则 有 $\varphi(S(n))$ 为真 ; 则 $\varphi(n)$ 对任意自然数 $n$ 都成立。



#### 冯 · 诺依曼的自然数定义

20 世纪初，集合称为数学的基本概念之后，数学奇才、计算机之父冯・诺依曼基于基数，利用一个集合的序列来定义自然数： 
- $\varnothing \in \mathbf{N}$
- 若 $n \in \mathbf{N},$ 则 $n^{\prime} \equiv n \cup\{n\} \in \mathbf{N}$ 。

从而，这个集合序列的基数就可以来定义自然数：
- $0 \equiv|\varnothing|$;
- $1 \equiv|\varnothing \cup\{\varnothing\}|=|\{\varnothing\}|$
- $2 \equiv|\{\varnothing\} \cup\{\{\varnothing\}\}|=|\{\varnothing,\{\varnothing\}\}|$
$\cdots$



### 等势



#### 引子

- 比较下列的集合对，哪一个的元素个数更多?

  1.  集合$ \{1,2,3\}$ 与集合 $\{a, b, c, d, \cdots, x, y, z\}$
  2.  自然数集合 $\mathbf{N}=\{0,1,2, \cdots\}$ 与奇数集合 $\{1,3,5,7, \cdots\}$对于
  -  两个有限集合而言，比较二者的大小只需要看集合的基数，但对于无限集合却没有这么简单。如何比较无限集合的 “大小" 呢？这里需要采用一种通过判断两个无限集合之间是否存在一种一一对应的关系来解决这个问题

#### 定义
设 $A, B$ 为两个集合，若在 $A, B$ 之间存在一种一一对应的关系：
$$
\Psi: A \rightarrow B
$$
则称 $A$ 与 $B$ 是等执的 (equipotential), 记作：
$$
A \sim B
$$
由等势定义可以看出，如果 $A=B$ ，那么 $A \sim B$， **反之却不成立**。

- 假设$A \sim B，A=\{1,2,3\}，B=\{a,b,c\}$，构成了一一对应的关系，但集合是不相等的



### 可数集合



#### 定义

- 凡与自然数集合 $\mathbf{N}$ 等势的集合，称为**可数集合(countable set)**，该集合的基数记 为 $\aleph_{0}($ 读作阿列夫零 $)$
- 从有限到无限，不仅仅是简单数量上的变化 (量变)，而引起了本质的改变 (质变)
  - 两个无限集合的 “大小" 已经不能单纯使用集合中的元素个数来衡量。 表示一切可数集合的基数，是一种抽象的表达
  - 表面上个数完全不相等的两个集合之间仍可能存在等势关系，如集合与其真子集之间，这体现了有限集合和无限集合的根本差别

#### 实例

试证明下列集合都是可数集合.

1.  $O^{+}=\{x \mid x \in \mathbf{N}, x$ 是正奇数 $\} ;$
    - 正偶数同理
2.  $P=\{x \mid x \in \mathbf{N}, x$ 是素数 $\} ;$
3.  有理数集合Q;
    - 有理数集合Q证明比较复杂，首先从$\frac{0}{1}$开始把每一个有理数按顺序写出来$\frac{1}{1},\frac{1}{2},\frac{0}{2},\frac{-1}{2}\cdots$
    - 随后标上对应的自然数顺序即可
    - 有理数集合Q是可数集合



#### 证明

在 $O^{+}$ 与 $\mathbf{N}$ 之间建立一个一一对应关系 $\varphi_{1}: \mathbf{N} \rightarrow O^{+}$ 如下:
$$
\begin{array}{lllllcl}
0 & 1 & 2 & 3 & \cdots & n & \cdots \\
\downarrow & \downarrow & \downarrow & \downarrow & & & \downarrow & \\
1 & 3 & 5 & 7 & \cdots & 2 n+1 & \cdots
\end{array}
$$
所以 $O^{+}$ 是可数集合。 



在 $P$ 与 $\mathbf{N}$ 之间建立一个一一对应关系 $\varphi_{2}: \mathbf{N} \rightarrow P$ 如下:
$$
\begin{array}{lllllllll}
0 & 1 & 2 & 3 & 4 & 5 & 6 & 7 & \cdots \\
\downarrow & \downarrow & \downarrow & \downarrow & \downarrow & \downarrow & \downarrow & \downarrow & \\
2 & 3 & 5 & 7 & 11 & 13 & 17 & 19 & \cdots
\end{array}
$$
所以 $P$ 是可数集合。



### 不可数集合



#### 定义

- 开区间 $(0,1)$ 称为不可数集合，凡与开区间$ (0,1)$ 等势的集合，称为不可数集合，该类 集合的基数记为 $\aleph$ (读作阿列夫)

#### 实例
- 闭区间$ [0,1]$ 是不可数集合; $\left\{\begin{array}{cccc}\frac{1}{4} & \rightarrow & 0 & \\ \frac{1}{2} & \rightarrow & 1 & \\ \frac{1}{2^{n}} & \rightarrow & \frac{1}{2^{n-2}} & (n=3,4,5 \cdots) \\ n & \rightarrow & n & \text { (others } n \in(0,1))\end{array}\right.$

- 实数集合 $\mathbf{R}$ 是不可数集合. $n \rightarrow \operatorname{tan} \pi\left(\frac{2 n-1}{2}\right)$

