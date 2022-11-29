# weiqi
# 围棋

## 题目背景

_以下内容为围棋的基本规则，了解围棋规则的同学可以直接前往题目描述。_

#### 基础知识

围棋是一种二人对战的策略型棋类游戏，双方轮流在横竖各 $n$ 条线的棋盘（称为 $n$ 路棋盘）交叉点上放置黑白棋子。

下图为一个 $9$ 路棋盘。

![](https://cdn.luogu.com.cn/upload/image_hosting/6fx7rafs.png)

#### 气

气指棋子与其上下左右四面相邻的空交叉点。围棋以气数定生死，气口决定了棋子的生存。

下图所示的黑棋有 $4$ 口气。

![](https://cdn.luogu.com.cn/upload/image_hosting/hx9t0ewz.png)

#### 连接

棋子可以连接。当一方两个及以上的毗邻棋子沿棋盘线相联，它们就会形成一个相互依存的整体，并共享气。

下图所示的黑棋总共有 $6$ 口气。

![](https://cdn.luogu.com.cn/upload/image_hosting/ex93yhjx.png)

#### 提

棋子处于无气状态时，必须立即从棋盘上提掉。所谓提子，即指落子封住对方所有气口后，将无气棋子取走的过程。

下列图展示了一系列黑棋提掉白子的过程。

![](https://cdn.luogu.com.cn/upload/image_hosting/6so387ha.png)![](https://cdn.luogu.com.cn/upload/image_hosting/ndu8qp3w.png)![](https://cdn.luogu.com.cn/upload/image_hosting/m34viexf.png)

![](https://cdn.luogu.com.cn/upload/image_hosting/ib095c86.png)![](https://cdn.luogu.com.cn/upload/image_hosting/3is2qluq.png)![](https://cdn.luogu.com.cn/upload/image_hosting/46lo900f.png)

![](https://cdn.luogu.com.cn/upload/image_hosting/nv2b3w3y.png)![](https://cdn.luogu.com.cn/upload/image_hosting/zoygdlk9.png)![](https://cdn.luogu.com.cn/upload/image_hosting/ppydvax2.png)

#### 禁入点

当一方在棋盘上某空白交叉点落子后，不仅无法提走对方棋子，反使己方处于无气状态，则按规定禁止落子。这样的交叉点也被称为“禁入点”。

下图中用红色禁止符标识的三处即为禁入点，黑棋无法落入。

![](https://cdn.luogu.com.cn/upload/image_hosting/tveebvl7.png)

落子后虽然没有气，但能立即提走对方棋子的情况，则是正常的提子过程，不存在禁入点。

下图中被白棋包围的交叉点就不是禁入点，黑棋可下入该点以提取白方棋子。

![](https://cdn.luogu.com.cn/upload/image_hosting/5xk1gwlm.png)![](https://cdn.luogu.com.cn/upload/image_hosting/ju45trwc.png)![](https://cdn.luogu.com.cn/upload/image_hosting/luzyt6sb.png)

_以上部分素材来自软件 JustGo_

## 题目描述

请你编写一段程序，模拟围棋的落子与提子过程。

## 输入格式

每个测试输入包含多个测试用例。输入的第一行包含一个正整数 $t$ ($1\le t\le 10$)，表示测试用例的组数。测试用例的描述如下：

测试用例的第一行包含一个正整数 $n$ ($3\le n\le 19$)，表示棋盘是一个 $n$ 路棋盘。

接下来的 $n$ 行，每行包含 $n$ 个字符 `+`、`X`、`O` 或 `?`，表示棋盘的初始状态。其中，字符 `+` 表示空交叉点，字符 `X` 表示黑棋，字符 `O` 表示白棋，字符 `?` 表示黑棋即将落子的位置。

数据保证，每个测试用例含有且仅含有一个 `?` 字符，且 `?` 字符所在的位置不是黑棋的禁入点。

数据保证，每个测试用例所表示的局面均为合法局面，即将 `?` 替换为 `+` 后，不存在没有气的棋子。

## 输出格式

对于每个测试用例，输出 $n$ 行，其中每行包含 $n$ 个字符 `+`、`X` 或 `O`，表示黑棋落子后棋盘的状态。其中，字符 `+` 表示空交叉点，字符 `X` 表示黑棋，字符 `O` 表示白棋。

测试用例的输出之间用一个空行分隔。

## 样例 #1

### 样例输入 #1

```
5
3
+X+
XO?
+X+
3
+X+
XO?
+++
3
+++
+?+
+++
3
OOO
O?O
OOO
5
++XOO
+XOOO
XO?X+
OOX++
OX+++
```

### 样例输出 #1

```
+X+
X+X
+X+

+X+
XOX
+++

+++
+X+
+++

+++
+X+
+++

++XOO
+XOOO
X+XX+
++X++
+X+++
```
