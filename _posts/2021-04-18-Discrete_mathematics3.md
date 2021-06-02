---
layout: post
title: 离散数学笔记3
date: 2021-04-22
categories: marginalia
tags: [笔记]
description: 离散数学好难搞
header-img: "img/headline4.jpg"
catalog:  true
typora-root-url: ../../junyahuang.github.io
---



## 图论



### 图的引入



#### 无序对和无序积

- 设 $A, B$ 为任意集合, 称集合 $A \& B=\{(a, b) \mid a \in A, b \in B\}$ 为 $A$ 与 $B$ 的无序积, $(a, b)$ 称为无序对
  - 与序偶不同, 对 $\forall a, b,(a, b)=(b, a)$

取 $A=\{a, b, c\}, B=\{1,2\}$, 则
- $A \& B=B \& A=\{(a, 1),(a, 2),(b, 1),(b, 2),(c, 1),(c, 2)\} $
- $A \& A=\{(a, a),(a, b),(a, c),(b, b),(b, c),(c, c)\}$



#### 图的定义

- 一个图 (Graph) 是一个序偶 $<V, E>$, 记为 $G=<V, E>$, 其中：
	- $V=\left\{v_{1}, v_{2}, \cdots, v_{n}\right\}$ 是有限非空集合， $v_{i}$ 称为结点 (node), $V$ 称为结点集。
	- $E$ 是有限集合，称为边集。 $E$ 中的每个元素都有 $V$ 中的结点对与之对应，称之为边 $($ edge $)$ 。

- 与边对应的结点对即可以是无序的, 也可以是有序的.
	- 若边 $e$ 与无序结点对 $(u, v)$ 相对应, 则称 $e$ 为无向边(undirected edge), 记为 $e=$ $(u, v)=(v, u)$, 这时称 $u, v$ 是边 $e$ 的两个端点
	- 若边 $e$ 与有序结点对 $<u, v>$ 相对应，则称 $e$ 为有向边(directed edge)(或弧), 记为 $e=<u, v>$, 这时称 $u$ 为 $e$ 的始点 $($ 或弧尾 $), v$ 为 $e$ 的终点 $($ 或弧头 $)$, 统称为 $e$ 的端点

<img src="/img-post/2021-04-18-Discrete_mathematics3/Y6aKzubdCUZwO20Cx2-09S4zwu7_W7OIBjvYN-M-xdc.original.fullsize.png" style="zoom:50%;" />
$$
\begin{array}{l}
V=\left\{v_{1}, v_{2}, v_{3}, v_{4}, v_{5}\right\} \\
E=\left\{e_{1}, e_{2}, e_{3}, e_{4}, e_{5}, e_{6}\right\} \\
e_{1}=\left(v_{1}, v_{2}\right) \quad e_{2}=<v_{1}, v_{3}> \\
e_{3}=\left(v_{1}, v_{4}\right) \quad e_{4}=\left(v_{2}, v_{3}\right) \\
e_{5}=<v_{3}, v_{2}>\ e_{6}=\left(v_{3}, v_{3}\right)
\end{array}
$$
​													$e_{1}, e_{3}, e_{4}, e_{6}$ 是无向边
​													$e_{2}, e_{5}$ 是有向边。



### 图的表示











### 子图和补图



### 握手定理



### 图的同构



### 通路和回路





### 可达性与最短通路



### 无向图的连通性



### 有向图的连通性



