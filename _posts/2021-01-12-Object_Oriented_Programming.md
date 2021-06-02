---
layout: post
title: 面向对象编程笔记
date: 2021-01-12
categories: marginalia
tags: [课堂笔记]
description: 网课网课网课
header-img: "img/headline7.jpg"
catalog:  true
typora-root-url: ../../junyahuang.github.io
---



# 面向对象编程



# 类与对象



## 类与对象的辨析


- 对象是实体，需要被创建，可以为我们做事情
- 类是规范，根据类的定义来创建对象

  - 对象（这只猫）
    - 表达东西或实践
    - 运行时相应消息（提供服务）
  - 类（猫）
    - 定义所有猫的属性
    - 就是Java中的类型
    - 可以用来定义变量

  - `类`->定义了->`对象`->是...的实体->`类`
- 对象 = 属性 + 服务
  - 数据：属性或状态
  - 操作：函数
    - 对象内的数据可以通过函数来使用，但是数据是只属于对象本身、不对外公开的。
  - 把数据和对数据的操作放在一起 -> 封装



## 定义类



### 典型的类和对象（售货机）

```java
public class VendingMachin{
    int price = 80;
    int balance;
    int total;
    
    void showPrompt()
    {
        System.out.println("Welcome");
    }
    void insertMoney(int amount)
    {
        balance = balance = amount;
    }

    void showBalance()
    {
        System.out.println(balance);
    }

    void getFood()
    {
        if( balance >= price)
        {
            System.out.println("Here you are.");
            balance = balance - price;
            total = total + price;
        }
    }

    public static void main(String[] args){

        VendingMachine vm = new VendingMachine();
        vm.showPrompt();
        vm.showBalance();
        vm.insertMoney(100);
        vm.getFood();
    }
    
}


```



### 创建对象

- `new VendingMachine();`
- `VendingMachine vm = new VendingMachine()`
  - 对象变量是对象的管理者
  - Debug中，对象拥有一个id，是Java在内部去表达每一个不同的对象的编号，id不同代表是不同对象



### 让对象做事

- `.运算符`
- `vm.insertMonet(100)`
- `vm.getFood()`



## 成员变量和成员函数



### 成员变量

- 类定义了对象中所具有的变量，这些变量称作成员变量
  - 每个对象有自己的变量，和同一个类的其他对象是分开的
  - 在函数中可以写成员变量的名字来访问成员变量
- 在函数中可以直接写成员变量的名字来访问成员变量，那么究竟访问的是哪个对象的呢？
  - 函数是通过对象来调用的
    - `vm.insertMoney()`
  - 这次调用临时建立了`inserMoney()`和`vm`之间的关系，让`inserMoney()`内部的成员变量指的是`vm`的成员变量



### this

- `this`是成员函数中的一个特殊的固有的本地变量，他表达了调用这个函数的那个对象
  - `System.out.println(this.balance)`
  - 在任何一个成员函数里面，总是可以用`this`来表达这一次调用这个函数的那个对象
```java
int price = 80;
void setPrice(int price)
{
  this.price = price;
}

函数的作用是改变类中的成员变量的值
```



### 调用函数

- 通过`.运算符`调用某个对象的函数
- 在成员函数内部直接调用自己(`this`)的其他函数



### 本地变量

- 定义在函数内部的变量是本地变量
  - 本地变量的生存期和作用域都是函数内部
- 成员变量的生存期是对象的生存期，作用域是类内部的成员函数



## 对象初始化



### 初始化零值辨析

- 本地变量如果没有初始化和赋值，变量是禁止使用的
- 类里的成员变量：
  - 成员变量在定义的地方就可以给出初始值
  - 没有给出初始值的成员变量会自动获得`0`值
    - 在`new`一个新对象的时候，按类里的顺序依次赋值
    - 对象变量的`0`值表示没有管理任何对象，也可以主动给`null`值
    - `Boolean`类型的`0`值是`false`
- 定义初始化可以调用函数，甚至可以使用已经定义的成员变量



### 构造函数

- 如果有一个成员函数的名字和类的名字完全相同，则在创建这个类的每一个对象的时候会自动调用这个函数
- 这个函数成为构造函数，这个函数不能有返回类型(即函数名前面没有类型名)
  - 定义对象时，最先进入构造函数
  - 但是会先去外面把成员变量先定义
  - 再回到构造函数内执行构造函数里的内容
  - 随后返回主程序

```java
VendingMachine()
{
  total=0;
}
```



### 函数重载

- 一个类可以有多个构造函数，只要它们的参数表不同
- 创建对象的时候给出不同的参数值，就会自动调用不同的构造函数
- 一个类里的同名但参数表不同的函数构成了重载关系

```java
VendingMachine()
{
  total=0;
}

VendingMachin(int price)
{
 
  this.price = price;
}
//接收一个price数据，赋给对象的price变量

//——————————————————————————————————

VendingMachine vm1 = new VendingMachine();
//调用构造函数1，total=0；

VendingMachine vm2 = new VendingMachine(80);
//调用构造函数2，price=80；
```


- 通过`this()`还可以在构造函数里调用其他构造函数
- `this()`只能在构造函数里出现
```java
VendingMachin(int price)
{
  this();
  //调用构造函数1
  this.price = price;
}
```





# 对象交互



## 时钟的实现



### 类的识别

- 时钟的小时和分钟有相同的属性，所以可以做一个类，以这个类创建两个对象代表小时和分钟
- 这个类最重要的属性是`value`和`limit`，有一个值，且有上限
- 创建类的时候需要有一个属于他的`main`，方便我们测试
```java
public class Display{
  private int value = 0;
  private int limit = 0;
  //0可有可无，但是为了避免出错尽量都初始化
  
  public Display(int limit){
    this.limit=limit;
  }
  //构造函数,public不是类型名

  public void increase(){
    value++;
    if(value==limit)
      value = 0;
  }

  public int getValue(){
    return value;
  }

  public static void main(String[] args){
    Display d = new Display(24);
    for(;;){
      d.increase();
      System.out.println(d.getValue());
    }
    //测试是不是value到24后置0
  }
}
```



### 对象的交互

- 对象可以包含其他的对象
  - `Clock`类包含两个`Display`类，为小时和分钟
- 小时和分钟的互动有几种做法可以实现
  - 例如，在`Min`的类中有一个代码，可以直接调用`Hour`类函数
    - 这意味着`Min`的代码和`Hour`的代码是不一样的，所以不能是同一个`Display`类
    - 我们希望我的类的设计和对象的结构都尽可能独立，我们希望`Min`和`Hour`之间没有直接联系
    - 没有直接联系的好处是他们各自独立，例如我们在编写`Min`的时候就不需要考虑`Hour`怎么办
    - 他们之间的联系需要通过第三方类——`Clock`来做

```java
public class Clock{

  private Display hour = new Display(24);
  private Display minute = new Display(60);

  public void start()
  {
    while(ture)
    {
      minute.increase();
      if(minute.getValue() == 0)
        hour.increase();

      System.out.printf("%02d:%02d\n",hour.getValue(),minute.getValue());
      //Java中也可以做到类似C语言的输出格式，需要printf
    }
  }

  public static void main(String[] args){
    Clock clock = new Clock();
    clock.start();

  } 
}
```



## Private关键字

- `private`只有这个类内部可以访问
  - 类内部指类的成员函数和定义初始化
  - 这个限制是针对**类**的而不是针对**对象**的
    - **同一个类的不同对象**之间，可以互相访问对方私有的成员
  
- `private`关键字只能用于成员变量，不能用在本地变量
  - 意思为这个变量是这个类私有的，在类的外部是不可访问的
  - 在外部只能通过成员函数来使用或修改
  - 在该类下的`main`函数里也是可以使用的
  - 若无特殊理由，所有的成员变量都应该是`private`



## Public关键字

- `public`任何人都可以访问
  - 如果一个类是`public`，任何人都可以用这个类的定义来定义变量
    - 如果一个类是`public`，要求源代码的**文件名**必须和**这个类的名字**相同
    - `public`的类必须定义在它自己的文件里
- 如果一个成员函数或成员变量前没有`private`或`public`，意味着它是`friendly`的，位于**同一个包**的其他类可以访问。

- 一个`.java`文件是一个编译单元，一次编译只对一个编译单元有编译动作
  - 一个编译单元可以有多个类，但最多只能有一个`public`类



## Package关键字

 - 在一个`src`下的同一个文件夹里的文件属于一个`package`
- `import`：如果用到的类和`.java`文件本身不在同一个`package`里，就需要`import`导入
 ```java
import display.Display
 ```
 - 如果不在文件开头导入，则每一次引用另一个包内的类时都要使用全名(包+类)
```java
private display.Display hour = new display.Display(24);
```
- `import`还可以写成通配符的形式
```java
import display.*;
//但有时会有重名冲突，故不推荐这种用法
```

- 包的内部还能有另外的包
```java
import display.led.Display;

import java.util.Scanner;

//java->util->Scanner
```



## 类变量

- `static`变量被称为类变量，多个对象共用同一个变量
- `static`变量不属于任何对象，属于一个类本身
- 只有**类变量**可以通过**类名+变量名**来访问
- 类似C语言，`static`变量的初始化只会进行一次
  - `static`变量只在类的装载时初始化
```java
private static int step = 1;

...

Display.step = 3;
```



## 类函数

- `static`函数被称为类函数，不属于任何对象，属于类本身
- 类函数中不可以调用非`static`的成员变量，只能调用类变量

```java
//同一个类中
public static void f(){
}

public static void main(String[] args){
  f();
  //d1.f();也是可以的
  //但通过对象去访问时，并不能获得该对象具体的信息，因为无法使用非static变量
}
```





# 对象容器



## 顺序容器



### 记事本

- 要求
  - 能存储记录
  - 不限制能存储的记录的数量
  - 能知道已经存储的记录的数量
  - 能查看存进去的每一条记录
  - 能删除一条记录
  - 能列出所有的记录
- 接口设计
  - `add(String note)`
  - `getSize()`
  - `getNote(int index)`
  - `removeNote(int index)`
    - list()`
- 避免新手很容易犯的错误：不要去考虑数据是怎么输入输出的
  - 真正的软件，**人机交互**部分(输入输出)和**业务逻辑**部分(对数据进行计算)一定要分离
- 一个类只需要考虑这个类能够提供的功能



### 范型容器类：ArrayList

- `ArraList<String> notes = new ArrayList<String>;`
  
- 容器类有两个类型：
  - 容器的类型
  - 元素的类型

```java
public class NoteBook{

  private ArraList<String> notes = new ArrayList<String>(); 
//用来存放String的ArraList，这是一个范型类

  public void add(String s)
  {
    notes.add(s);
    //ArrayList的add函数
  }

  public void add(String s, int location)
  {
    notes.add(location,s);
  }
//重载
  public int getSize()
  {
    return notes.size();
  }

  public String getNote(int index)
  {
    return notes.get(index);
  }

  public void removeNote(int index)
  {
    notes.remove(index);
  }

  public String[] list()
  {
    String[] a = new String[notes.size()];
//  for(int i=0;i<notes.size();i++)
//    	a[i] = notes.get(i);
		notes.toArray(a);
    retuan a;
  }

  public static void main(String[] args){
    NoteBook nb = new NoteBook();
    nb.add("Fist");
    nb.add("Second");
    nb.add("Third",1);
    System.out.println(nb.getSize());
    System.out.println(nb.getNote(0));
    nb.removeNote(1);
    String [] a = nb.list();
    for(String s : a){
    	System.out.println(s);
    }
  }
}
```



### ArrayList的方法

|方法|描述|
|:-|:--|
|`add()`|将元素插入到指定的arralist中|
| `addAll()` | 添加集合中的所有元素到 arraylist 中|
| `clear()` | 删除 arraylist 中的所有元素|
|`clone()` | 复制一份 arraylist|
| `contains()` | 判断元素是否在 arraylist|
| `get()` | 通过索引值获取 arraylist 中的元素|
| `indexOf()` | 返回 arraylist 中元素的索引值|
| `removeAll()` | 删除存在于指定集合中的 arraylist 里的所有元素 |
| `remove()` | 删除 arraylist 里的单个元素|
| `size()` | 返回 arraylist 里元素数量|
| `isEmpty()` | 判断 arraylist 是否为空|
| `subList()` | 截取部分 arraylist 的元素|
| `set()` | 替换 arraylist 中指定索引的元素|
| `sort()` | 对 arraylist 元素进行排序|
| `toArray()` | 将 arraylist 转换为数组|
| `toString()` | 将 arraylist 转换为字符串|
| `retainAll()` | 保留 arraylist 中在指定集合中也存在的那些元素|
| `containsAll()` | 查看 arraylist 是否包含指定集合中的所有元素|
| `removeRange() `| 删除 arraylist 中指定索引之间存在的元素|
| `forEach()` | 遍历 arraylist 中每一个元素并执行特定操作#    |



## 对象数组



### 对象数组

- `String`的数组，数组里的每一个元素都是一个对象的管理者（地址），而非对象本身
- 当没有赋值的时候，默认为`null`，此时无法输出它的`length`，赋值了之后就可以输出了

### 对象数组的`for-each`循环

- 对象数组的`for-each`循环与基础数组的`for-each`循环不一样
  - 基础数组的每一轮`k`都是改变的（数组对k赋值），对`k`进行改动是无效的
  - 对象数组的每一轮`k`都是一个管理者（数组传递地址），所以利用`k`进行改动时会影响本身的数据
- 容器类的数组也是一样的道理 

```java
public class Value{
	private int i;
	public void set(int i){this.i = i;}
	public int get(){return i;}
}
public static void main(String[] args)
{
	Value[] a = new Value[10];
	for(int i=0;i<a.length;i++)
	{
		a[i] = new Value();
		a[i].set(i);
	}
	for( Value k : a){
		System.out.println(k.get());
		k.set(0)
	}
	for( Value k : a){
		System.out.println(k.get());
	}
}
```



## 集合容器(Set)



### Set容器——集合容器

- `HashSet<String> s = new HashSet<String>();`
- `Set`是数学中的集合，集合的一个重要特点是无重复，所以不会放入重复的内容
- 集合的另一个特点是无序性，即不会按输入的先后顺序来排序

```java
HashSet<String> s = new HashSet<String>();
s.add("first");
s.add("second");
s.add("first");
for(String : s)
	System.out.println(k);
//输出结果为：
//second
//first
```

- 输出时也可以写作

```java
System.out.println(s);

//输出结果为：
//[second, first]
```



### toString函数

- 'public String toString`函数
	- 如果没有`toString`函数，直接输出对象时，会显示一串无意义的地址
	- 加入了`toString`函数，再直接输出对象，会输出你设定好的内容

```java
public class Value{
	public int i;
	public void set(int i){ this.i = i; }
	public int get(){ return i; }
	public String toString(){ return ""+i };
}
public static void main(String[] args){
	Value v = new Value();
	v.set(10);
	System.out.println(v);
	
	//没有toSrting：输出“*.Value@22998b08”;
	//定义toString：输出“10”;
}
```

  


## 散列表(Hash)

- `hash`表有覆盖作用，一个`key`唯一对应一个内容，重复对一个`key`赋值会覆盖原值。

- 可以通过构造函数来放入`hash`表的内容

- `coinnames.keySet()`是一个`key`的集合，所以可以利用这个`keyset`的`size`来获得`key`的多少，或者用`for-each`循环输出全部的内容

  - ```java
    System.out.println(coinnames.keySet().size());
    for( Integet k : coinnames.ketSet()){
    	String s = coinnames.get(k);
    	System.out.println(s);
    }
    ```

    

```java
public class Coin{

	private HashMap<Integer, String> coinnames = new HashMap<Integet, String>();
	//Hash表
	//这是个面向对象的容器，容器内的所有类型都必须是对象而不能是基本元素
	//包裹类型是对象类型，int对应Integet
	
	public Coin(){
		coinnames.put(1, "penny");
		coinnames.put(10, "dime");
		coinnames.put(25, "quarter");
		coinnames.put(50, "half-dolar");
	}
	//构造函数
	
	public String getName(int amount){
		if( coinnames.containsKey(amount))	
			return coinnames.get(amount);
		else
			return "NOT FOUND";
	}
	
	public static void main(String[] args){
		Scanner in = new Scanner(System.in);
		int amount = in.nextInt();
		Coin coin = new Coin();
		String name = coint.getName(amount);
		System.out.println(name);
	}
}
```



# 继承与多态



## 前言

	面向对象程序设计语言有三大特性：封装、继承和多态性。继承是面向对象语言的重要特征之一，没有继承的语言只能被称作“使用对象的语言”。继承是非常简单而强大的设计思想，它提供了我们代码重用和程序组织的有力工具。
	
	类是规则，用来制造对象的规则。我们不断地定义类，用定义的类制造一些对象。类定义了对象的属性和行为，就像图纸决定了房子要盖成什么样子。
	
	一张图纸可以盖很多房子，它们都是相同的房子，但是坐落在不同的地方，会有不同的人住在里面。假如现在我们想盖一座新房子，和以前盖的房子很相似，但是稍微有点不同。任何一个建筑师都会拿以前盖的房子的图纸来，稍加修改，成为一张新图纸，然后盖这座新房子。所以一旦我们有了一张设计良好的图纸，我们就可以基于这张图纸设计出很多相似但不完全相同的房子的图纸来。
	
	基于已有的设计创造新的设计，就是面向对象程序设计中的继承。在继承中，新的类不是凭空产生的，而是基于一个已经存在的类而定义出来的。通过继承，新的类自动获得了基础类中所有的成员，包括成员变量和方法，包括各种访问属性的成员，无论是public还是private。当然，在这之后，程序员还可以加入自己的新的成员，包括变量和方法。显然，通过继承来定义新的类，远比从头开始写一个新的类要简单快捷和方便。继承是支持代码重用的重要手段之一。
	
	类这个词有分类的意思，具有相似特性的东西可以归为一类。比如所有的鸟都有一些共同的特性：有翅膀、下蛋等等。鸟的一个子类，比如鸡，具有鸟的所有的特性，同时又有它自己的特性，比如飞不太高等等；而另外一种鸟类，比如鸵鸟，同样也具有鸟类的全部特性，但是又有它自己的明显不同于鸡的特性。
	
	如果我们用程序设计的语言来描述这个鸡和鸵鸟的关系问题，首先有一个类叫做“鸟”，它具有一些成员变量和方法，从而阐述了鸟所应该具有的特征和行为。然后一个“鸡”类可以从这个“鸟”类派生出来，它同样也具有“鸟”类所有的成员变量和方法，然后再加上自己特有的成员变量和方法。无论是从“鸟”那里继承来的变量和方法，还是它自己加上的，都是它的变量和方法。



## 继承



### 媒体资料库的设计

- `Source` → `Generate Constructor using Fields`自动设置构造函数，将成员变量初始化好

```java
package dome;
import java.until.ArrayList;

public class Databasa{
	private ArrayList<CD> listCD = new ArrayList<CD>();
	
	public void add(CD cd){
		listCD.add(cd);
	}
	
	public void list(){
		for( CD cd : listCD)
			cd.print;
	}
	
	public static void main(String[] args){
		Database db = new Database();
		db.add(new CD("abc","abc",4,60,"..."));
		db.add(new CD("def","def",4,60,"..."));
    //注意新建一个CD的方法
	}
	
}
```

```java
package dome;

public class CD{
	private String title;
	private String artist;
	private int numofTracks;
	private int playingTime;
	private boolean gotIt = false;
	private String comment;
	
	public CD(String title, String artise, int numofTracks, int playingTime, String commen){
		//super();
		this.title = title;
		this.artist = artise;
		this.numofTracks = numofTracks;
		this.playingTime = playingTime;
		this.comment = comment;
	}
	
	public void print(){
		System.out.println(title + ":" + artist);
	}
	public static void main(String[] args){
	
	}
}
```

```java
package dome;
import java.until.ArrayList;

public class Databasa{
	private ArrayList<Item> listItem = new ArrayList<Item>();
	
	public void add(Item item){
		listItem.add(item);
	}
	
	public void list(){
		for( Item item : listITem)
			item.print;
	}
	
	public static void main(String[] args){
		Database db = new Database();
		db.add(new CD("abc","abc",4,60,"..."));
		db.add(new CD("def","def",4,60,"..."));
	}
	
}
```



### 继承辨析

	我们把用来做基础派生其它类的那个类叫做父类、超类或者基类，而派生出来的新类叫做子类。Java用关键字extends表示这种继承/派生关系：

```
class ThisClass extends SuperClass {   
	//… 
}
```

	继承表达了一种is-a关系，就是说，子类的对象可以被看作是父类的对象。比如鸡是从鸟派生出来的，因此任何一只都可以被称作是一只鸟。但是反过来不行，有些鸟是鸡，但并不是所有的鸟都是鸡。如果你设计的继承关系，导致当你试图把一个子类的对象看作是父类的对象时显然很不合逻辑，比如你让鸡类从水果类得到继承，然后你试图说：这只本鸡是一种水果，所以这本鸡煲就像水果色拉。这显然不合逻辑，如果出现这样的问题，那就说明你的类的关系的设计是不正确的。Java的继承只允许单继承，即一个类只能有一个父类。

```java
class Vehicle {
protected String brand = "Tesla";
public void honk() {
System.out.println("Beep, Beep!");
}
}
class Car extends Vehicle {
private String modelName = "Model Y";
public static void main(String[] args) {
Car myCar = new Car();
myCar.honk();
System.out.println(myCar.brand + " " + myCar.modelName);
}
}
```

执行 java Car 得到

```java
//Beep, Beep!
//Tesla Model Y
```



### 继承实现

```java
package dome;

public class Item{
	public void print(){
	
	}
}
```

```java
package dome;

public class CD extends Item{
	private String title;
	private String artist;
	private int numofTracks;
	private int playingTime;
	private boolean gotIt = false;
	private String comment;
	
	public CD(String title, String artise, int numofTracks, int playingTime, String commen){
		//super();
		this.title = title;
		this.artist = artise;
		this.numofTracks = numofTracks;
		this.playingTime = playingTime;
		this.comment = comment;
	}
	
	public void print(){
		System.out.println(title + ":" + artist);
	}
	public static void main(String[] args){
	
	}
}
```

```java
package dome;
import java.until.ArrayList;

public class Databasa{
	private ArrayList<Item> listItem = new ArrayList<Item>();
	
	public void add(Item item){
		listItem.add(item);
	}
	
	public void list(){
		for( Item item : listItem)
			item.print;
	}
	
	public static void main(String[] args){
		Database db = new Database();
		db.add(new CD("abc","abc",4,60,"..."));
		db.add(new CD("def","def",4,60,"..."));
	}
}
```





## 子类父类关系



### 成员关系

	对理解继承来说，最重要的事情是，知道哪些东西被继承了，或者说，子类从父类那里得到了什么。答案是：所有的东西，所有的父类的成员，包括变量和方法，都成为了子类的成员，除了构造方法。构造方法是父类所独有的，因为它们的名字就是类的名字，所以父类的构造方法在子类中不存在。除此之外，子类继承得到了父类所有的成员。
	
	但是得到不等于可以随便使用。每个成员有不同的访问属性，子类继承得到了父类所有的成员，但是不同的访问属性使得子类在使用这些成员时有所不同：有些父类的成员直接成为子类的对外的界面，有些则被深深地隐藏起来，即使子类自己也不能直接访问。下表列出了不同访问属性的父类成员在子类中的访问属性：

| **父类成员访问属性** | **在父类中的含义**                 | **在子类中的含义**                                           |
| -------------------- | ---------------------------------- | ------------------------------------------------------------ |
| public               | 对所有人开放                       | 对所有人开放                                                 |
| protected            | 只有包内其它类、自己和子类可以访问 | 只有包内其它类、自己和子类可以访问                           |
| 缺省                 | 只有包内其它类可以访问             | 如果子类与父类在同一个包内：只有包内其它类可以访问否则：相当于private，不能访问 |
| private              | 只有自己可以访问                   | 不能访问                                                     |

```java
public的成员直接成为子类的public的成员，protected的成员也直接成为子类的protected的成员。Java的protected的意思是包内和子类可访问，所以它比缺省的访问属性要宽一些。而对于父类的缺省的未定义访问属性的成员来说，他们是在父类所在的包内可见，如果子类不属于父类的包，那么在子类里面，这些缺省属性的成员和private的成员是一样的：不可见。父类的private的成员在子类里仍然是存在的，只是子类中不能直接访问。我们不可以在子类中重新定义继承得到的成员的访问属性。如果我们试图重新定义一个在父类中已经存在的成员变量，那么我们是在定义一个与父类的成员变量完全无关的变量，在子类中我们可以访问这个定义在子类中的变量，在父类的方法中访问父类的那个。尽管它们同名但是互不影响。

在构造一个子类的对象时，父类的构造方法也是会被调用的，而且父类的构造方法在子类的构造方法之前被调用。在程序运行过程中，子类对象的一部分空间存放的是父类对象。因为子类从父类得到继承，在子类对象初始化过程中可能会使用到父类的成员。所以父类的空间正是要先被初始化的，然后子类的空间才得到初始化。在这个过程中，如果父类的构造方法需要参数，如何传递参数就很重要了。
```

- 子类从父类那里继承所有的父类的成员，包括变量和方法，但是不继承父类的构造方法
- 子类能继承得到父类的所有成员。包括private修饰的私有成员。
  - 但是，拥有不等于可以任意使用，子类不能访问继承得到的私有成员。
  - 子类也不能继承父类的构造函数。因为构造函数的函数名必须和所在类的类名一致。

```java
package dome;

public class Item{
  private String title;
  public Item(String title){
    super();
    this.title = title;
  }
  
  public print(){
    System.out.printf("");
  }
}

public class CD extends Item {
  	public CD(String title){
      super(title);
    }
}
```

- `super`可以传递参数到子类，所以父类的构造函数如果有`super`，子类的构造函数也需要有`super`与之对应，如果子类没有`super`，会自动寻找父类中不带参数的构造器
- 定义顺序：父类定义初始化→父类构造器初始化→子类定义初始化→子类构造器初始化

```java
package dome;

public class Item{
  private String title;
  public Item(String title){
    super();
    this.title = title;
  }
  
  public Item(){
  }
  
  public print(){
    System.out.printf("");
  }
}

public class DVD extends Item {
  	public DVD(){
    }
}
```



### 子类父类的复杂关系

- 如果子类和父类都有同名的变量，则子类的函数里使用的变量是子类的，父类函数里使用的变量是父类的

```java
package dome;

public class Item{
  private String title;
  private int playingTime;
  private boolean gotIt = false;
  private String comment;
  
  public Item(){
    
  }
  public Item(String title,int playingTime, boolean gotIt, String comment){
    super();
    this.title = title;
    this.playingTime = playingTime;
    this.gotIt = gotIt;
    this.comment = comment;
  }
  
  
  public print(){
    System.out.printf(title);
  }
}
```

```java
package dome;

public class CD extends Item {
  	private String artist;
  	private int numofTracks;
  
  	public CD(String title, String artist, int numofTracks, int playingTime, String comment){
      super(title,playingtime,false,comment);
      this.artist = artist;
      this.numofTracks = numofTracks;
    }
}
```

```java
package dome;

public class DVD extends Item {
  	private String director;
  
  	public DVD(String title, String director, int playingTime, String comment){
      super(title,playingtime,false,comment);
      this.director = director;
    }
  	public void print(){
      System.out.println("DVD:");
      super.print();
      //super可以调用父类的函数
      //this可以调用本类的函数
      System.out.println(director);
    }
}
```



### super()

1. 能在一个构造函数里调用两次`super()`吗？
   - 一个构造函数里面不能调用两次`super()`
2. `super()`必须在构造函数的第一行吗？
   - `super()`必须写在第一行

## 多态变量和向上造型



### 前言

	类定义了类型,DVD类所创建的对象的类型就是DVD。类可以有子类,所以由那些类定义的类型可以有子类型。在DoME的例子中,DVD类型就是Item类型的子类型。
	子类型类似于类的层次,类型也构成了类型层次。子类所定义的类型是其超类的类型的子类型。
	当把一个对象赋值给一个变量时,对象的类型必须与变量的类型相匹配,如:
	Car myCar = new Car(); 
	是一个有效的赋值,因为Car类型的对象被赋值给声明为保存Car类型对象的变量。但是由于引入 了继承,这里的类型规则就得叙述得更完整些:
	
	一个变量可以保存其所声明的类型或该类型的任何子类型。
	
	对象变量可以保存其声明的类型的对象,或该类型的任何子类型的对象。Java中保存对象类型的变量是多态变量。“多态”这个术语(字面意思是许多形态)是指一个变量可以保存不同类型(即其声明的类型或任何子类型)的对象。



### 子类和子类型

- 类定义了类型
- 子类定义了子类型
- 子类的对象可以被当作父类的对象来使用
  - 赋值给父类的变量
    - 子类的对象可以赋值给父类的变量
    - `Vehicle ( Car / Bicycle )`
      - `Vehicle v1 = new Vehicle();`
      - `Vehicle v2 = new Car();`
      - `Vehicle v3 = new Bicycle();`
  - 传递给需要父类对象的函数
    - 子类的对象可以传递给需要父类对象的函数
  - 放进存放父类对象的容器里



### 多态变量

- Java 的对象变量是多态的，它们能保存不止一种类型的对象
- 它们可以保存的是声明类型的对象，或声明类型的子类的对象
- 当把子类的对象赋给父类的变量的时候，就发生了向上造型



```java
 public class Test{
   private class Father{
     -var
     -staticVar
     -method()
     -staticMethod()
   }
   private class Son{
     -var
     -staticVar
     -sonVar
     -method()
     -staticMethod()
     -sonMethod()
   }
   public static void main(String args[]){
     Father f = new Son();
     //Father f = new Father();
     //Son f = new Son();
     System.out.println(f.var);;//打印父类变量，字段没有多态，编译器只认变量类型，不看本质对象
     System.out.println(f.staticVar);//打印父类的静态变量
     f.method();//多态，如果子类改写了这个方法，就会调用子类的方法
     f.staticMethod();//静态方法没有多态，看管理者，是谁就调用谁
     f.sonVar="123";//编译不通过，父类管理者变量看不到子类变量
     f.sonMethod();//编译不通过，同理
     ((Son)f).sonVar="123";//强转成子类管理者变量，编译器通过，ok
     ((Son)f).sonMethod();//同上
     //如果f放入父类对象，上述两式编译器通过，但是编译的时候失败，因为f管理的本质上是父类变量，强转了也不会改变管理的对象，只改变了管理者的类型
   }
 }
```

- 字段(静态和非静态)、静态和`final` / `private` 方法——静态绑定
- 非静态、非 `final` / `private` 方法——动态绑定



### 造型Cast

- 子类的对象可以赋值给父类的变量

  - 注意！Java中不存在对象对对象的赋值！

- 父类的对象不能赋值给子类的变量

  - ```java
    Vechicle v;
    Car c = new Car();
    v = c;//可以
    x = v;//编译错误
    ```
- 可以用造型：
  - `c = (Car) v;`
  - 只有当`v`这个变量实际管理的是Car才行
    - 否则会“类造型一场”
### 造型

- 用括号围起来放在值的前面
- 对象**本身**并没有发生任何变化
  
  - 所以不是类型转换
- 运行是有机制来检查这样的转化是否合理
  
- `ClassCastException`
  
- 和类型转换是不一样的

  
### 向上造型
- 拿一个子类的对象，当作父类的对象来用
- 向上造型是默认的，不需要运算符
- 向上造型总是安全的



### 编译器和运行期检查

- 编译时，能向上造型 (默认) 和向下造型 (需强转)
- 运行时，要看引用变量的本质对象，子类变量不可以管理父类对象，父类变量可以管理子类对象，而且必须在一条线上



### 关于`instanceof`运算符

- 可以使用 "`引用变量 instanceof 类名` 来判断该引用变量所指向的对象是否属于该类或该类的子类
- `instanceof`运算符的结果是`true`，否则是`false`
- 用直观逻辑去判断" (子类) 狗是不是 (父类) 动物"就可以





## 多态



>​	如果子类的方法覆盖了父类的方法，我们也说父类的那个方法在子类有了新的版本或者新的实现。覆盖的新版本具有与老版本相同的方法签名：相同的方法名称和参数表。因此，对于外界来说，子类并没有增加新的方法，仍然是在父类中定义过的那个方法。不同的是，这是一个新版本，所以通过子类的对象调用这个方法，执行的是子类自己的方法
>
>​	覆盖关系并不说明父类中的方法已经不存在了，而是当通过一个子类的对象调用这个方法时，子类中的方法取代了父类的方法，父类的这个方法被“覆盖”起来而看不见了。而当通过父类的对象调用这个方法时，实际上执行的仍然是父类中的这个方法。注意我们这里说的是对象而不是变量，因为一个类型为父类的变量有可能实际指向的是一个子类的对象。
>
>​	当调用一个方法时，究竟应该调用哪个方法，这件事情叫做绑定。绑定表明了调用一个方法的时候，我们使用的是哪个方法。绑定有两种：一种是早绑定，又称静态绑定，这种绑定在编译的时候就确定了；另一种是晚绑定，即动态绑定。动态绑定在运行的时候根据变量当时实际所指的对象的类型动态决定调用的方法。Java缺省使用动态绑定。

### 函数调用的绑定

- 多态变量有两种类型：声明类型和动态类型
  - 当多态变量处于动态类型时，它会执行动态类型所对应的函数
- 当通过对象变量调用函数的时候，调用哪个函数这件事情叫做绑定
  - 静态绑定：根据变量的声明类型来决定
  - 动态绑定：根据变量的动态类型来决定
    - Java默认所有的绑定都是动态绑定
- 在成员函数中调用其他成员函数也是通过`this`这个对象变量来调用的
  - 所有成员函数的调用都可以看做一种动态绑定



### 覆盖Override

- 子类和父类中存在名称和参数表完全相同的函数，这一对函数构成覆盖关系
- 通过**父类的变量**调用存在覆盖关系的函数时，会调用变量当时所管理的对象所属的类的函数



### 对象的上转型对象

- 上转型对象不能操作子类新增的成员变量，不能调用子类新增的方法
- 上转型对象可以访问子类继承或隐藏的成员变量，也可以调用子类继承的方法或子类重写的实例方法
- 如果子类重写了父类的某个实例方法后，当用上转型对象调用这个实例方法时一定是调用了子类重写的实例方法
- 即，上转型对象不能看到新增的，但是旧有的如果被重写了的话，还是会调用重写后的

## 类型系统



### Object类

- 所有的类都是默认继承自`Object`的
- Object类的函数
  - `toString()`
    - 输出对象时需要`toString()`，默认调用
      - `System.out.println(cd.toString);`=`System.out.println(cd);`
    - 所以如果想直接输出对象内容时，在对象对应的类中添加`toString`函数，重载`toString`，此时直接输出对象时就会输出你改写的内容
    - `Source`→`Generate toString()`可以帮助输出内容
  - `equals()`
    - 默认的`equals()`函数只能判断管理者是不是管理着同一个对象
    - 我们需要自己写一个`equals()`函数来重载
    - `Source`→`Override/Implement Methods`：列出父类的函数并问你要改写哪个函数

```java
@Override
public boolean equals(Object obj){
  	CD cc = CD(obj);
  	return artist.equals(cc.artist);
}
//重载：新函数的函数名、参数必须和原函数完全一致
//有@Override时，会检查下面的的函数是否符合重载条件，不符合条件会报错
```



###  构造子类的技巧

- 新建子类时：`superclass`→`Superclass`，自动`extends`
- 构造子类变量时：`Srouce`→`Generate Constructors from Superclass`，形成一个来自父类的构造器





# 设计原则



## 消除代码复制

- 代码赋值是不良设计的体现
- 将重复啰嗦的代码化为函数

## 封装

- 用封装来降低耦合

  - 类和类之间的关系称作耦合
  - 耦合越低越好，保持距离是形成良好代码的关键
  - 类和类之间不要有成员变量的直接交互

- 对于城堡游戏

  - Room类和Game类都有大量的代码和出口相关
  
  - 尤其是Game类中大量使用了Room类的成员变量

  - 利用封装减低耦合
  
    

### 用接口实现聚合

  - 给Room类实现的新方法，把方向的细节彻底隐藏在Room类内部了
  - 今后方向如何实现和外部无关了

```java
//class room中
public String getExitDesc(){
  StringBuffer sb = new StringBuffer();
  if(northExit != null)
    sb.append("north ");
  if(eastExit != null)
    sb.append("east ");
  if(westExit != null)
    sb.append("west ");
  if(southExit != null)
    sb.append("south ");
  return sb.toString();
}
```



## 可扩展性

- 可以运行的代码不等于良好的代码
- 对代码维护的时候最能看出代码的质量



### 用容器来实现灵活性

- Room的方向是用成员变量来表示的，增加或减少方向就要改变代码
- 如果用Hash表来表示方向，那么方向就不是”硬编码“的了

```java
package castle;
import java.util.HashMap;
  
public class Room{
  private String description;
  private HashMap<String, Room> exits = new HashMap<String, Room>();
  
  public Room(String description)
  {
    this.description = description;
  }
  
  public void setExit(String dir, Room room){
    exits.put(dir,room);
  }
  
  
  public String toString(){
    	return description;
  }
  
  public String getExitDesc(){
    StringBuffer sb = new StringBuffer();
    for( String dir : exits.keySet()){
      sb.append(dir);
      sb.append(' ');
    }
  }
  public Room getExit(String direction)
  {
    	return exits.get(direction);
  }
}
```



## 框架加数据

- 以框架+数据来提高可扩展性
  - 命令的解析是否可以脱离`if-else`
  - 定义一个`Handler`来处理命令
  - 用`Hash`表来保存命令和`Handler`之间的关系

```java
package castle;

public class Handler{
  protected Game game;
  
  public Handler(Game game){
    this.game = game;
  }
  public void doCmd(String word){}
  public boolean isBye(){return false;}
}
```

```java
package castle;

public class HandlerBye extends Handler{
  
  public HandlerBye(Game game){
    super(game);
  }
  @Override
  public boolean isBye(){
    return true;
  }
}
```

```java
package castle;

public class HandlerGo extends Handler{
  public HandlerGo(Game game){
    super(game);
  }
  public void doCmd(String word){
    game.goRoom(word);
  }
}
```

```java
package castle;

public class HandlerHelp extends Handler{
  public HandlerHelp(Game game){
    super(game);
  }
  @Override
  public void doCmd(String word){
    System.out.println("迷路了吗？你可以做的命令有：go bye help");
    System.out.println("如：\tgo east");
  }
}
```


```java
package castle;

import java.util.Scanner;
import java.util.HashMap;

public class Game{
  private Room currentRoom;
  private HashMap<String, Handler> handlers = new HashMap<String, Handler>();
  
  
  public Game(){
    handlers.put("go",new HandlerGo(this));
    handlers.put("bye",new HandlerBye(this));
    handlers.put("help",new HandlerHelp(this));
    creatRooms();
  }
  
  private void creatRooms(){
    Room outside, lobby, pub, study, bedroom;
    
    outside = new Room("城堡外");
    lobby = new Room("大堂");
    pub = new Room("小酒吧");
    study = new Room("书房");
    bedroom = new Room("卧室");
    
    outside.setExit("east",lobby);
    outside.setExit("south",study);
    outside.setExit("west",pub);
    lobby.setExit("west",outside);
    pub.setExit("east",outside);
    study.setExit("north",outside);
    study.setExit("east",bedroom);
    bedroom.setExit("west",study);
    lobby.setExit("up",pub);
    pub.setExit("down",lobby);
    
    currentRoom = outside;
  }
  private void printWelcome(){
    System.out.println("这是一个城堡游戏");
    System.out.println("if you need help, input 'help'");
    showPrompt();
  }

  public void goRoom(String direction)
  {
    Room nextRoom = currentRoom.getExit(direction);
    
    if(nextRoom == null)System.out.println("那里没有门!");
    else
    {
      currentRoom = nextRoom;
      showPrompt();
    }
  }
  
  public void showPrompt(){
    System.out.println("你在" + currentRoom);
    System.out.print("出口有：");
    System.out.print(currentRoom.getExitDesc());
    System.out.println();
  }
  
  public void play(){
    Scanner in = new Scanner(System.in);
    while( true ){
      	String line = in.nextLine();
      	String[] words = line.split(" ");
      	Handler handler = handlers.get(words[0]);
      	String value = "";
      	if(words.length > 1)value = words[1];
      	if( handler != null){
          	handler.doCmd(value);
          	if( handler.isBye())
          	{
          		System.out.println("游戏结束，感谢参与。");
          		break;
          	}
        }
      	
    }
  }
  public static void main(String[] args){
    Game game = new Game();
    game.printWelcome();
    game.play();
  }
}
```





# 抽象与接口



## 抽象



### 前言

> ​	在第一周就有一个Shape类的例子。这个类有很多的子类，每个子类也都实现了父类的方法。实际上父类Shape只是一个抽象的概念而并没有实际的意义。如果请你画一个圆，你知道该怎么画；如果请你画一个矩形，你也知道该怎么画。但是如果我说：“请画一个形状，句号”。你该怎么画？同样，我们可以定义Circle类和Rectangle类的draw()，但是Shape类的draw()呢？
>
> ​	Shape类表达的是一种概念，一种共同属性的抽象集合，我们并不希望任何Shape类的对象会被创建出来。那么，我们就应该把这个Shape类定义为抽象的。我们用abstract关键字来定义抽象类。抽象类的作用仅仅是表达接口，而不是具体的实现细节。抽象类中可以存在抽象方法。抽象方法也是使用abstract关键字来修饰。抽象的方法是不完全的，它只是一个方法签名而完全没有方法体。
>
> ​	如果一个类有了一个抽象的方法，这个类就必须声明为抽象类。如果父类是抽象类，那么子类必须覆盖所有在父类中的抽象方法，否则子类也成为一个抽象类。一个抽象类可以没有任何抽象方法，所有的方法都有方法体，但是整个类是抽象的。设计这样的抽象类主要是为了防止制造它的对象出来。

### 抽象函数

- 带有`abstract`修饰符的函数
- 表达概念而无法实现具体代码的函数
- 抽象函数不能有`{}`
- 没有抽象构造函数和抽象静态方法 (不能和static连用)
- 不能与 `final` 连用
- 抽象类中可以没有抽象方法





  

### 抽象类

- 表达改变而无法构造出实体的类
- 抽象的类不能产生对象
  - 但是可以定义变量
  - 任何继承了抽象类的非抽象类的对象可以付给这个变量
- 有抽象函数的类一定是抽象类
- 继承自抽象类的子类必须覆盖父类中的抽象函数
- 如果一个类继承自抽象类，但是却没有全部继承，那这个类也需要是抽象类
- 和普通的类相比，抽象类里可以有抽象方法，也可以没有。对于抽象方法，只允许声明，不允许实现，而且不允许使用`final`修饰抽象方法

```java
package shapes;

import java.awt.Graphics;

public abstract class Shape{
  	public abstract void draw(Graphics g  );
} 
```





### 两种抽象的辨析

- 与具体相对

  - 表示一种概念而非实体

- 与细节相对

  - 表示在一定程度上忽略细节而着眼大局

    

## 数据与表现分离

- 程序的业务逻辑与表现无关
  - 表现可以是图形的也可以是文本的
  - 表现可以是当地的也可以是远程的

- View和Field的关系
  - 表现与数据的关系
  - View只管根据Field画出图形
  - Field只管数据的存放
  - 一旦数据更新以后，通知View重新画出整个画面
    - 不去精心设计哪个局部需要更新
    - 这样简化是程序逻辑
    - 是在计算机运算速度提高的基础上实现的

- 网格化
  - 图形界面本身有更高的解析度
  - 但是将画面网格化以后，数据就更容易处理了

## 接口



### 狐狸与兔子

- 狐狸和兔子都有年龄
- 当年龄到了一定的上限就会自然死亡
- 狐狸可以随机决定在周围的兔子中吃一个
- 狐狸和兔子可以随机决定生一个小的，放在旁边的格子里
- 如果不吃也不生，狐狸和兔子可以随机决定向旁边空的格子移一步



### 接口的定义

- 接口是纯抽象类
  - interface是一种特殊的class
  - 所有的**成员函数**都是抽象函数
  - 所有的**成员变量**都是`public static final`
  - **成员变量和成员函数**不写前缀的时候，默认是`public static`
- 接口规定了长什么样，但是不管里面有什么
- 一个类可以实现多个不相关的接口（从而代替”多继承“）
- 多个不相关的类可以实现一个接口
- 接口与其相应实现类之间也存在多态性
- 一个接口可以继承另一个接口，进行扩展
- 接口中没有构造函数，方法可以抛出异常

```java
package cell;
import java.awt.Graphics;

public interface Cell{
  	void draw(Graphics g, int x, int y, int size);
}
```

```java
public class Fox extends Animal implements Cell{
  
}
```

```java
public Cell place(int row, int col, Cell o){
  //o是任意能被执行的对象
}
```



### 接口的实现

- 类用`extends`，接口用`implements`
- 类可以实现很多接口
- 接口可以继承接口，但是不能继承类
- 接口不能实现接口



### 面向接口的编程方式

- 设计程序时先定义接口，再实现类
- 任何需要在函数间传出的一定是接口而不是具体的类
  - 是Java成功的关键之一，因为极适合多人同时写一个大程序
  - 也是Java被批评的要点之一，因为代码量膨胀起来很快

### Cell和Field的关系

- Cell在Field中，但是Cell的很多操作需要Field的数据
- 方法一：
  - 让每个Cell有一个Field的管理者（Cell知道Field）
- 方法二：
  - 由外部的第三方来建立两者之间的联系（Cell不知道Field）



# 控制反转与MVC模式



## 控制反转

###  前言

		GUI（图形用户界面）给应用程序提供界面,其中包括窗口、菜单、按钮和其他图形组件,这就是今天大多 数人所熟悉的“典型”应用程序界面。
		图形用户界面所涉及的细节很多,我们的课程并不打算教授GUI，但是我们打算借助GUI来介绍两个设计思想：控制反转和MVC设计模式。
	部件是创建GUI的独立部分,比如像按钮、菜单、菜单项、选择框、滑动条、文本框等。Java类库中有不少现成的部件。
		布局是指如何在屏幕上放置组件。过去,大多数简单的GUI系统让程序员在二维坐标系上 指定每个组件的x和y坐标(以像素点为单位),这对于现代的GUI系统来说太简单了。因为现代的GUI系统还得考虑不同的屏幕分辨率、不同的字体、用户可改变的窗口尺寸,以及许多其他使得布局困难的因素。所以需要有一种能更通用地指定布局的方法,比如,要求“这个部件应该在那个部件的下面“或者”这个部件在窗口改变尺寸时能自动拉伸,但是其他部件保持尺寸不变”。这些可以通过布局管理器(layout manager)来实现。
		事件处理是用来响应用户输入的技术。创建了部件并且放在屏幕上合适的位置以后,就得 要有办法来处理诸如用户点击按钮这样的事情。Java类库处理这类事情的模型是基于事件的。 如果用户激活了一个部件(比如,点击按钮或者选择菜单项),系统就会产生一个事件。应用 程序可以收到关于这个事件的通知(以程序的一个方法被调用的方式),然后就可以采取程序该做的动作了。



### 布局管理器

```java
JButton btnStep = new JButton("单步");
frame.add(btnStep, BorderLayout.NORTH);
```

- 如果不指定加到哪儿，则默认加入`BorderLayout.CENTER`
  - 位置一共有：`EAST`,`WEST`,`NORTH`,`SOUTH`,`CENTER`
  - 根据放进去的东西会自动计算填补到容器内

### 控制反转

```java
	Swing使用一个非常灵活的模型来处理GUI的输入:采用事件监听器的事件处理(event handling)模型。
	Swing框架本身以及大部分部件在发生一些情况时会触发相关的事件,而其他的对象也许会对这些事件感兴趣。不同类型的动作会导致不同类型的事件。当点击一个按钮或选中一个菜单项,部件就会触发动作事件;而当点击或移动鼠标时,会触发鼠标事件;当框架被关闭或最小化时,会触发窗口事件。另外还有许多种其他事件。
	所有的对象都可以成为任何这些事件的监听器,而一旦成为监听器,就可以得到这些事件触发的通知。
	实现了众多监听器接口 之一的对象就成为一个事件监听器。如果对象实现了恰当的接口, 就可以注册到它想监听的组件上。
```

```java
btnStep.addActionListener(new ActionListener(){
  @Override
  public void actionPerformed(ActionEvent e){
    	System.out.println("按下啦");
    	step();
  }
});
//匿名类
```

### 内部类

		内部类就是指一个类定义在另一个类的内部，从而成为外部类的一个成员。因此一个类中可以有成员变量、方法，还可以有内部类。实际上Java的内部类可以被称为成员类，内部类实际上是它所在类的成员。所以内部类也就具有和成员变量、成员方法相同的性质。比如，成员方法可以访问私有变量，那么成员类也可以访问私有变量了。也就是说，成员类中的成员方法都可以访问成员类所在类的私有变量。内部类最重要的特点就是能够访问外部类的所有成员。

- 定义在别的类内部、函数内部的类
- 内部类能直接访问外部的全部资源
  - 包括任何私有的成员
  - 外部是函数时，只能访问那个函数里final的变量

### 匿名类

- 在`new`对象的时候给出的类的定义形成了匿名类
- 匿名类可以继承某类，也可以实现某接口
- `Swing`的消息机制广泛使用匿名类



### 注入反转

- 由按钮公布一个守听者接口和一对注册 / 注销函数
- 你的代码实现那个接口，将守听者对象注册在按钮上
- 一旦按钮被按下，就会反过来调用你的守听者对象的某个函数



## MVC模式



### JTable

- 用`JTable`类可以以表格的形式显示和编辑数据。`JTable`类的对象并不存储数据，他只是数据的变现。

```java
package kcb;

import javax.swing.*;

public class KCB{
  
  public static void main(String[] args){
    JFrame frame = new JFrame();
    JTable table = new JTable(new KCBData());
    JScrollPane pane = new JScrollPane(table);
    frame.add(pane);
    frame.pack();
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setVisible(true);
  }
}
```

```java
package kcb;

import javax.swing.event.TableModelListener;
import javax.swing.table.TableModel;

public class KCBData implements TableModel {

	private String[] title = {"周一","周二","周三","周四","周五","周六","周日"};
	private String[][] data = new String[8][7];
	
	public KCBData() {
		for(int i=0;i<data.length;i++) {
			for(int j=0;j<data[0].length;j++) {
				data[i][j]="";
			}
		}
	}
	@Override
	public int getRowCount() {
		// TODO 自动生成的方法存根
		return 8;
	}

	@Override
	public int getColumnCount() {
		// TODO 自动生成的方法存根
		return 7;
	}

	@Override
	public String getColumnName(int columnIndex) {
		// TODO 自动生成的方法存根
		return title[columnIndex];
	}

	@Override
	public Class<?> getColumnClass(int columnIndex) {
		// TODO 自动生成的方法存根
		return String.class;
	}

	@Override
	public boolean isCellEditable(int rowIndex, int columnIndex) {
		// TODO 自动生成的方法存根
		return true;
	}

	@Override
	public Object getValueAt(int rowIndex, int columnIndex) {
		// TODO 自动生成的方法存根
		return data[rowIndex][columnIndex];
	}

	@Override
	public void setValueAt(Object aValue, int rowIndex, int columnIndex) {
		// TODO 自动生成的方法存根
		data[rowIndex][columnIndex] = (String)aValue;
	}

	@Override
	public void addTableModelListener(TableModelListener l) {
		// TODO 自动生成的方法存根

	}

	@Override
	public void removeTableModelListener(TableModelListener l) {
		// TODO 自动生成的方法存根

	}

}
```



### MVC设计模式

- 数据、表现和控制三者分离，各负其责
  - M = Model（模型）
  - V = View（表现）
  - C = Control（控制）
- 模型：保存和维护数据，提供接口让外部修改数据，通知表现需要刷新
- 表现：从模型获得数据，根据数据画出表现
- 控制：从用户得到输入，根据输入调整数据





# 异常处理与输入输出



## 异常

- 异常
  - 有不寻常的事情发生了
  - 当这个事情发生的时候，原本打算要接着做的事情不能再继续了，必须得要停下来，让其他地方的某段代码来处理

### 捕抓异常

- 将可能出现异常的块放入`try`中处理
- 异常发生不代表程序的终止

```java
int[] a = new int[10];
int idx;
Scanner in = new Scanner(System.in);
idx = in.nextInt();
try{
  a[idx] = 10;
  System.out.println("hello");
}catch(ArrayIndexOutOfBoundException e){
  System.out.println("Caught");
}
```

```java
try{
  //可能产生异常的代码
}catch(Type1 id1){
  //处理Type1 id1异常的代码
}catch(Type2 id2){
  //处理Type2异常的代码
}catch(Type3 id3){
  //处理Type3异常的代码
}
```

![image-20210123154641957](/img-post/2021-01-12-Object_Oriented_Programming/image-20210123154641957.png)

- 拿到异常对象后
  - `System.out.println(e.getMessage())`
  - `System.out.println(e.toString())`
  - `e.printStackTrace()`
  - 但是你肯定是回不去了，而具体的处理逻辑则取决于你的业务逻辑需要

### 再度抛出

- 这个在这个层面上需要处理，但是不能做最终的决定

```java
catch(Exception e){
  System.err.println("An exception was thrown");
  throw e;
}
```



### Finally

```java
try{
  //你的代码
}catch(A a1){
  
}catch(B b1){
  
}catch(C c1){
  
}finally{
  //每次进入try后一定会执行
}
```

- 进入`try`的四种下场
  - 无疾而终
  - 发生了异常，而且捉到了
  - 发生了异常但是没有捉到
  - 发生了异常捉到了，但是又抛出了
- 在离开`try`语句之前，最后都要进`finally`



## 异常机制



### 异常声明

- 你可以声明并不会真的抛出的异常
  - 目前不会抛出，但是以后可能会改版，提前配置好

- 如果你调用一个声明会抛出异常的函数，那么你必须：
  - 把函数的调用放在`try`块，并设置`catch`来捕捉所有可能抛出的异常；
  - 或声明自己会抛出但无法处理的异常

```java
class OpenException extends Exception{
  
}
class CloseException extends Exception{
  
}

public static void readFile() throws OpenException, CloseException{ //三单。有s
  if(open() == -1){
    throw new OpenException();
    //祈使句，无s
  }
}
//函数会抛出异常时，调用时一定要try并catch该异常
public static void main(String[] args){
  try{
    	readFile();
  }catch(OpenException e){
    e.printStackTrace();
  }catch(NullPointerException e){
    e.printStackTrace();
  }catch(CloseExcepiton e){
    e.printStackTrace();
  }
}
```



### 什么能扔

- 任何继承了`Throwable`类的对象
- `Exception`类继承了`Throwable`
  - `throw new Exception();`
  - `throw new Exception("HELP");`



### catch怎么匹配异常的

- `Is-A`的关系
  - 也就是说，抛出子类异常会被捕捉父类异常的`catch`给捉到
- 自上而下匹配，匹配到第一个异常后停止



### 捕捉任何异常

- `throwable` → `Exception`→其他异常
  - 父类`Exception`可以捉到所有的异常
- 像`ArrayIndexOutOfBoundsException`这样的异常是不需要声明的
  - 但是如果没有适当的机制来捕捉，就会最终导致程序终止

```java
catch(Exception e){
  	System.err.println("Caught an exception");
}
```



### 异常声明遇到继承关系

- 当在子类内覆盖一个函数的时候，子类**不能**声明抛出比父类的版本更多的异常
  - 可以不抛出，但是不能抛更多
  - 成员函数不能抛出更多的异常
- 在子类的构造函数中，**必须**声明父类可能抛出的全部异常
  - 构造函数中的异常可以抛出父类所没有的异常



## 流(stream)

- 流是一维单向的 

- 流的基础类
  - InputStream
  - OutputStream
- InputStream使用时，必须要使用`Exception`，因为默认存在`IOEception`

```java
package inputoutput;

import java.io.IOException;

public class Main {

	public static void main(String[] args) {
		System.out.println("Input:");
		byte[] buffer = new byte[1024];
		try {
			int len = System.in.read(buffer);
			String s = new String(buffer, 0, len);
			System.out.println("读到了"+len+"字节");
			System.out.println(s);
			System.out.println(s+"的长度是"+s.length());
		} catch (IOException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		}	
	}
}
```

- GKB中，每个汉字是 2 个字节，在unicode中是一个字符
  - UTF-8中，汉字为 3 个字节



### 文件流

- FileInputStream
- FileOutputStream
  - 对文件读写操作
- 实际工程中已经较少使用
  - 更常用的是以在内存数据或通信数据上建立的流，如数据库的二进制数据读写或网络端口通信
  - 具体的文件读写往往有更专业的类，比如配置文件和日志文件

```java
package inputoutput;

import java.io.*;

public class File {

	public static void main(String[] args) {
		System.out.println("Input:");
		byte[] buffer = new byte[10];
		for(int i=0; i<buffer.length; i++)
		{
			buffer[i]=(byte)i;
		}
		try {
			FileOutputStream  out  = new FileOutputStream("a.dat");
			out.write(buffer);
			out.close();
		} catch (FileNotFoundException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		} catch (IOException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		}
	}
}
```



### 流过滤器

- 以一个介质流对象为基础层层构建过滤器流，最终形成的流对象能在数据的输入输出过程中，逐层使用过滤器流的方法来读写数据
  - `DataOutputStream out  = new DataOutputStream(
    				new BufferedOutputStream(
          					new FileOutputStream("a.dat")));`

```java
package inputoutput;
import java.io.*;
public class File {
	public static void main(String[] args) {
		try {
			DataOutputStream out  = new DataOutputStream(
				new BufferedOutputStream(
					new FileOutputStream("a.dat")));
			int i = 123456;
			out.writeInt(i);
			out.close();//一定要关闭，否则文件指针在末尾，抛出EOF错误
			DataInputStream in = new DataInputStream(
					new BufferedInputStream(
							new FileInputStream("a.dat")));
			int j = in.readInt();
			System.out.print(j);
			in.close();
		} catch (FileNotFoundException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		} catch (IOException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		}
	}
}
```



## 文本输入输出



- Reader / Writer

  - 二进制数据采用 InputStream / OutputStream
  - 文本数据采用 Reader / Writer

- 在流上建立文本处理

  - ```java
    PrintWriter pw = new PrintWriter(
    	new BufferedWriter(
      	new OutputStreamWriter(
        	new FileOutputStream("abc.txt"))));
    ```

  - ```java
    BufferedReader in = new BufferedReader(
    				  	new InputStreamReader(
    				    	new FileInputStream("abc.txt")));
    ```

  - 文件本身并非Unicode码格式时，需要多层过滤器来处理

- Reader

  - 常用的是`BufferedReader`
  - `readLine()`

- LineNumberReader

  - 可以得到行号
    - `getLineNumber()`

```java
package inputoutput;
import java.io.*;
public class wenben {

	public static void main(String[] args) {
		try {
			PrintWriter out = new PrintWriter(
					new BufferedWriter(
				  	new OutputStreamWriter(
				    	new FileOutputStream("abc.txt"))));
			int i = 123456;
			out.println(i);
			out.close();
			BufferedReader in = new BufferedReader(
				  	new InputStreamReader(
				    	new FileInputStream("src/inputoutput/File.java")));
			String line;
			while((line=in.readLine())!= null) {
				System.out.println(line);
			}
			in.close();
		} catch (FileNotFoundException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		} catch (IOException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		}
	}
}
```



### FileReader

- InputStreamReader类的子类，所有方法都从父类中继承而来
- `FileReader (File file)`
- 在给定从中读取数据的 File 的情况下创建一个新 FileReader
- `FileReader (String fileName)`
  - 在给定从中读取数据的文件名的情况下创建一个新 FileReader
- FileReader不能指定编码转换方式
  - 比较少用



### 汉字编码

- 文本的编码方式有很多，默认为 GKB 模式，如果要读取 UTF-8 模式的文本，需要指定

  - ```java
    	BufferedReader in = new BufferedReader(
    				  	new InputStreamReader(
    				    	new FileInputStream("utf8.txt"),"utf8"));
    ```

  - `"utf8"`是`InputStreamReader()`的参数



### 格式化输出

- PrintWriter
  - fomat("格式",...);
  - printf("格式",...);
  - print(各种基本类型);
  - println(各种基本类型);
- Scanner
  - 在`InputStream`或`Reader`上建立一个Scanner对象可以从流中的文本中解析出文本表达的各种基本类型
    - next..();

![image-20210124190016747](/img-post/2021-01-12-Object_Oriented_Programming/image-20210124190016747.png)

## 流的应用

- 可以向服务器获得或输出文本
- 在终端中输入`nc -l 12345(端口)`并回车，后运行程序，即可开始

```java
package inputoutput;

import java.io.*;
import java.net.*;

public class Flush {

	public static void main(String[] args) {
		try {
			Socket socket = new Socket(InetAddress.getByName("localhost"),12345);
			PrintWriter out = new PrintWriter(
					new BufferedWriter(
							new OutputStreamWriter(
									socket.getOutputStream())));
			out.println("hello");
			out.flush();
			BufferedReader in = new BufferedReader(
					new InputStreamReader(
							socket.getInputStream()));
			String line;
			line = in.readLine();
			System.out.println(line);
			out.close();
			socket.close();
			in.close();
			
		} catch (FileNotFoundException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		} catch (IOException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		}
	}
}
```

### 阻塞 / 非阻塞

- `read()`函数是阻塞的，在读到所需的内容之前会停下来等
  - 使用`read()`的更“高级”的函数，如`nextInt()`、`readLine()`都是这样的
  - 所以常用单独的线程来做 socket 读的等待，或使用 noi 的 channel 选择机制
- 对于 socket，可以设置 SO 时间
  - `setSoTimeout(int timeOut)`

### 对象串行(xing)化

- ObjectInputStream 类
  - `readObject()`
- ObjectOutputStream类
  - `writeObject()`
- Serializable 接口

```java
package inputoutput;

import java.io.*;

class Student implements Serializable{
	private String name;
	private int age;
	private int grade;
	
	public Student(String name, int age, int grade) {
		this.name = name;
		this.age = age;
		this.grade = grade;
	}
	
	public String toString() {
		return name + " " + age + " " + grade;
	}
}

public class Chuan {

	public static void main(String[] args) {
		try {
			Student s1 = new Student("John",18,5);
			System.out.println(s1);
			ObjectOutputStream out = new ObjectOutputStream(
					new FileOutputStream("obj.dat"));
			out.writeObject(s1);
			out.close();
			ObjectInputStream in = new ObjectInputStream(
					new FileInputStream("obj.dat"));
			Student s2 = (Student)in.readObject();
			System.out.println(s2);
			in.close();
			System.out.println(s1==s2);
			//s1,s2的内容一样，但是并不是相同的对象
		} catch (FileNotFoundException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		} catch (IOException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		} catch (ClassNotFoundException e) {
			// TODO 自动生成的 catch 块
			e.printStackTrace();
		}
	}
}
```





# 实用类



## Object类的方法

- **equals(Object obj)**
  - Object 类的 `equals()` 方法定义为：`x.equals(y)`，当 x 和 y 为同一个对象时返回 `true`，否则返回 `false`；与 "==" 相同
  - 但是，JDK 提供的一些常用类，比如 `String`, `Date` 等重写了这个方法，语义为判断**属性（成员变量）是否相同**，不判断是否为同一个，是判断内容
  - "==" 只能判断是不是同一个对象，不能用来判断是否内容相同
  - 用户自定义类也应根据需要重写这个方法
  - 改写 `equals()` 方法应遵守的约定（离散数学的等价关系的定义）
    - 自反性：对任何费控引用值 x，`x.equals(x)` 都应返回` `true`
    - 对称性
    - 传递性
    - 一致性
    - 非空性 
  - 改写  `equals()` 方法时总是要改写 `hashCode()` 方法
  - 类对象作为 hashxxx 结构（hashMap）的索引时，必须要重写该类的 `hashCode()` 方法
    - 对于  `equals()` 相等的两个对象，其 `hashCode()` 返回的值一定相等；对于 `equals()` 不同的两个对象，其 `hashCode()` 尽量相等
- notify()
- nofityAll()
- **hashCode()**
- wait()
- **toString()**
  - 返回当前对象的字符串表示，返回值是一个String，通常，`toString `方法会返回一个“以文本方式表示”此对象的字符串。结果应是一个简明但易于读懂的信息表达式。建议所有子类都重写此方法
  - 直接输出对象和输出 `对象.toString()` 是一个效果
    - 因为 `println(Object obj)` 会调用 `obj.toString()`
    - ↑ 这是一个多态调用
  - `new Integer(100).toString`  会打印100



## String类



- 自变量只存一个，s1 和 s3 是相同的一个对象，"hello" 只有一个，是一个**自变量**

```java
public class Test{
  public static void main(String[] args){
    String s1 = "hello";
    String s2 = "world";
    String s3 = "hello";
    System.out.println(s1 == s3);//true
    
    s1 = new String("hello");
    s2 = new String("hello");
    System.out.println(s1 == s2);//false
    System.out.println(s1.equals(s2));//true
    
    char c[] = {'s','u','n',' ','j','a','v','a'};
    String s4 = new String(c);
    String s5 = new String(c,4,4);
    System.out.println(s4);//sun java
    System.out.println(s5);//java
  }
}
```



#### String类常用方法

- `public int length()`：返回字符串长度

- `public char charAt(index)`：返回字符串中第 index 个字符

- `public int  indexOf(String str)` 和 `lindexOf(String str, int fromIndex)`：返回字符串中str第一次出现的位置；如果找到，返回匹配的位置 ，找不到返回 -1

- `public String concat(String str)`：在最后添加字符串

- `public String replace(char oldChar, char newChar)`：在字符串中用字符 newChar 替换字符 oldChar

- `public String substring(int beginIndex)` 和 `public String substring(int beginIndex, int endIndex)`：返回字符串的第一个子字符串，子串在源串的起始位置为 beginIndex，结束位置为 endIndex

- `public static String valueOf(byte/int/long/float/double)`：将形如123、1232.98等数值转化为字符串

  





#### 比较 String 类和 StringBuffer 类

- String 类不可编辑
- StringBuffer 类可编辑



#### String辨析

```java
//常量池
public class Example{
  public static void main(String args[]){
    String hello = "你好";
    String testOne = "你" + "好";
    System.out.println(hello == testOne);//true
    System.out.println("你好" == testone);//true
    System.out.println("你好" == hello);//true
    String you = "你";
    String hi = "好";
    String testTwo = you + hi;
    System.out.println(hello == testTwo);//false
    String testThree = you + hi;
    System.out.println(testTwo == testThree);//flase
  }
}
```



# 组件及事件处理



## AWT简介

- AWT（Abstract Window Toolkit）包含众多类和接口，用于 Java 应用程序的 GUI 编程
- GUI 的各种元素由 Java 类提供实现
- 使用 AWT 所涉及的类一般在 java.awt 包及其子包中
- Contrainer 和 Component 是AWT 中的两个核心类
