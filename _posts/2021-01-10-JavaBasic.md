---

layout: post
title: Java基础笔记
date: 2021-01-10
categories: marginalia
tags: [课堂笔记]
description: 网课网课网课
header-img: "img/headline7.jpg"
catalog:  true
typora-root-url: ../../junyahuang.github.io
---





# 基础语法



## print、prinf、println

- `print`是一般的输出标准，但是不换行
- `println`会换行
- `printf`继承了C语言的`printf`一些特性，可以进行格式化输出




#  数组



##  数组定义

```
int[] a = new int[100];
int[] scores = {87,53,77,42,45};
```



##  数组长度

```
int[] a = new int[100];
a.length
for(i=0;i<a.length;i++)
```

- 在创建数组时，java会自动把所有的元素都填为0，每个元素都有0值



##  数组变量

```
int[] a = new int[10];
a[0]=5;
int[] b = a;
b[0]=16;
```
- 随后`a[0]`也会变成16，数组之间的直接赋值本质为地址的赋值
- 数组`a`是一个管理者，不是所有者，数组变量里不存数据，只存着地址
- 当`b=a`时，`a`把地址给了`b`，相当于把钥匙给了`b`共享，`a`和`b`共同管理一批数据

1. 数组变量是数组的管理者而非数组本身
2. 数组必须创建出来然后交给数组变量来管理
3. 数组变量之间的赋值是管理权限的赋予
4. 数组变量之间的比较（比较数组是否相同）是判断是否管理同一个数组

```
int[] a={1,2,3};
int[] b={1,2,3};

尽管数字相同，但'a==b'依然是错的，因为两个数组是分别定义的，是两个独立的数组，不是同一个数组

如果想比较两个数组的数据是否相等，需要利用flag，用循环进行依次比较
```




# For循环



## for-each循环

- `for(int k:data)`对数组data，每一轮k的值，都为数组data里的一个数值，下一轮为下一个数值

- 针对需要遍历的数组的场合，比较方便，缺点是没有数组的位置，也不能改变数组

  - 需要输出数组的时候比较方便



## continue MAIN_LOOP

- 可以定义一行`MAIN_LOOP:` ，然后接一个循环，随后`continue MAIN_LOOP`就是跳到这个循环前
适用于多层循环，从内部判断跳出到下一层大循环

```
int[] primes = new int[50];
primes[0] = 2;
int cnt = 1;
MAIN_LOOP:
for( int x = 3; cnt < prime.length; x++)
{
	for( int i = 0; i < cnt; i++)
	{
		if(x % primes[i] == 0)
			continue MAIN_LOOP;
	}
}
primes[cnt++] = x;
for( int k : primes)
	System.out.print( k + " ");
System.out.println();

```



## 二维数组

```
int[][] a = new int[SIZE][SIZE];
```




# 字符



## 字符类型

- 单个的字符是一种特殊的类型：`char`
	- Java使用Unicode来表示字符，可以表达包括汉字在内的多种文字
	- `char a = ‘\u0041’`，或者`65`，都表示`A`
		- 4x16+1=65
	- 整数和字符也能进行转换，和ASCII一样，A对应65；
- 字符加减与C语言一致
	- 汉字字符也是可以做运算的
	- 字符之间可以直接做大小比较，和C语言致



## 大小写字符的换算

```
char d = (char)('C' + 'a' - 'A');

C加上‘a'和'A'之间的距离，C就能转换成c。

注意计算之后c就变成了一个整型数，所以需要用char强制转换一下。
```



## 逃逸字符

|字符|意义|字符|意义|
|:-:|:-:|:-:|:-:|
|`\b`|回退一格|`\"`|双引号|
|`\t`|到下一个表格为|`\'`|单引号|
|`\n`|换行|`\\`|反斜杠本身|
|`\r`|回车|

- 一般来说，eclipse的Console不会理会`\b`的输出
- `\r` 和 `\n`，在计算机中，回车和换行是两个不同的操作



## 包裹类型


基础类型|包裹类型
:-:|:-:
`boolean`|`Boolean`
`char`|`Character`
`int`|`Integer`
`double`|`Double`

- 包裹类型均以大写字母开头，每种基础类型都有对应包裹类型

- 可以用包裹类型来实现一些功能
	- 获得该类型的最大最小值
		- `Integer.MAX_VALUE`
		- `Integer.MIN_VALUE`



## 运算符

当需要让一个类或对象做事情的时候，用`.运算符`



## Character运算

代码|功能
:-|:-
`Character.isDigit(char ch)`|判断字符是不是数字
`Character.isLetter(char ch)`|判断字符是不是字幕
`Character.isLetterOrDigit(char ch)`|判断字符是不是字幕或数字
`Character.isLowerCase(char ch)`|判断字符是不是小写字母
`Character.isUpperCase(char ch)`|判断字符是不是大写字母
`Character.isWhitespace(char ch)`|判断字符是不是一种空格
`Character.toLowerCase(char ch)`|把字符转换成小写
`Character.toUpperCase(char ch)`|把字符转换成大写



## 字符串变量

- `String`是一个类，`String`的变量是对象的管理者而非所有者
	- 就像数组变量是数组的管理者而非所有者一样
	- `String`不是一个系统的基础变量

```
String s = new String("a string");
```

- 创建了一个`String`对象
- 用`"a string"`初始化这个对象
- 创建管理这个对象的变量`s`

```
String s = "hello";
```

- 编译器帮你创建一个`String`类交给`s`来管理



## 字符串连接

- 用加号`+`可以连接两个字符串
	- `"hello"+"world"` → `"helloworld"`
- 当这个`+`的一边是字符串而另一边不是时，会将另一边表达为字符串然后做链接
	- `"I'm "+18` → `"I'm 18"`
	- `1+2+"age"` → `"3age"`
	- `"age"+1+2` → `"age12"`
		- 运算从左到右进行，所以如果`1+2`在`s`右边，会先计算`s+1`，结果是`s1`，再计算`s1+2`，结果是`s12`
		- 想要`s3`的话，只能用括号把`1+2`括起来，即`s+(1+2)`



## 字符串常用方法

代码|作用
:-|:-
`s=in.next`|输入，到下一个空格为止
`s=in.nextline`|输入，下一个回车为止
`s1.equals(s2);`|比较字符串内容是否相同
`s1.compareTo(s2);`|比较字符串大小
`s.length()`|获得String的长度
`s.charAt(int)`|获得String上的字符
`s.substring(n)`|得到从n号位置到末尾的全部内容
`s.substring(b,e)`|得到从b号位置到e号位置之前的内容
`s.replace(c1,c1)`|把字符串内的c1换成c2
`s.trim()`|删除字符串两端的空格

- 注意，Java中字符串没有`\0`，所见即所得，`String name="China";`的长度应为`5`
- 若`String str`,则`str.length()`会产生`error`，应为此时str没有管理任何字符串，是个空字符
- `s.substring(b,e)`为左闭右开，不会取到第`e`个字符，只会取到`e-1`



## 寻找字符串

代码|作用(-1表示不存在)
-|-
`s.indexOf(c)`|得到c字符所在的位置
`s.indexOf(c,n)`|从n号位置开始寻找c字符
`s.indexOf(t)`|找到字符串t所在的位置
`s.lastIndexOf(c)`|从右边开始找
`s.lastIndexOf(c,n)`|同上
`s.lastIndexOf(t)`|同上



## 不可变的String

- 所有的字符串都是不可变的，对它们的操作的结果都是制造新的字符串出来.
- 函数都不是修改字符串本身，而是返回一个新的字符串，Java没有方法能够改变字符串本身的内容
```
String s1="abcd";
s1.toUpperCase();
System.out.println(s1);

结果依然为`abcd`，s1并没有改变，正确写法为
String s2 = s1.toUpperCase();
```



## swtich-case中使用字符串

1.7及以上版本的Java可以在`switch-case`中使用字符串来判断

---




# 函数



## Math类函数

函数|功能
-|-
Math.abs()|绝对值
Math.round(float/double)|四舍五入
Math.random()|产生随机数(0~1之间)
Math.pow(x,n)|输出浮点数，x、n可为浮点数

- `Math.random()*100`是0~100的随机数



## 定义函数

- 在同一个`public class Main`下
- 大体和C语言相同，前缀为`public static`,是必须的
- 注意判断型的函数为`boolean`



## 类型不匹配

- 当函数期望的参数类型比调用函数时的值的类型宽的时候，编译器能悄悄替你把类型转换好。
	- char -> int -> double
	- 宽的可以接受窄的，反过来不可以，如果想传值，必须强制转换



## 传值和传址

- 和C语言类似，Java语言在调用函数时，永远只能传值给函数
  - 每个函数有自己的变量空间，参数也位于这个独立的空间中，和其他函数没有关系
  - 过去，对于函数参数表中的参数，叫做”形式参数“，调用函数时给的值，叫做”实际参数，现在这种方法意见不建议使用了
  - 我们认为，它们是参数和值的关系



## 生存期和作用域

- 和C语言类似的定义，对于本地变量，生存期和作用域是统一的
- 本地变量是定义在块内的
  - 它可以是定义在函数的块内
  - 也可以定义在语句的块内
  - 甚至可以随便拉一对大括号来定义变量
- 程序运行进入这个块之前，其中的变量不存在，离开这个块，其中的变量就消失了
- 块外面定义的变量在里面仍然有效
- 不能在一个块内定义同名的变量，也不能定义块外面定义过的变量
- 本地变量不会被默认初始化