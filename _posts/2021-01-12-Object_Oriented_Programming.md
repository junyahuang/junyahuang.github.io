---

layout: post
title: 面向对象编程笔记
date: 2021-01-12
categories: marginalia
tags: [课堂笔记]
description: 网课网课网课
header-img: "img/headline7.jpg"
catalog:  true
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
```
public class VendingMachin{
    int price = 80;
    int balance;
    int total;
    
    void showPrompt()
    {
        System.out.println("Welcome")'
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
            System.out.println("Here you are.);
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
```
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
  

```
VendingMachine()
{
  total=0;
}
```

### 函数重载

- 一个类可以有多个构造函数，只要它们的参数表不同
- 创建对象的时候给出不同的参数值，就会自动调用不同的构造函数
- 一个类里的同名但参数表不同的函数构成了重载关系

```
VendingMachine()
{
  total=0;
}

VendingMachin(int price)
{
 
  this.price = price;
}
//接收一个price数据，赋给对象的price变量

——————————————————————————————————

VendingMachine vm1 = new VendingMachine();
//调用构造函数1，total=0；

VendingMachine vm2 = new VendingMachine(80);
//调用构造函数2，price=80；
```


- 通过`this()`还可以在构造函数里调用其他构造函数
- `this()`只能在构造函数里出现
```
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
  
```
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

```
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
 ```
import display.Display
 ```
 - 如果不在文件开头导入，则每一次引用另一个包内的类时都要使用全名(包+类)
```
private display.Display hour = new display.Display(24);
```
- `import`还可以写成通配符的形式
```
import display.*;
//但有时会有重名冲突，故不推荐这种用法
```

- 包的内部还能有另外的包
```
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
```
private static int step = 1;

...

Display.step = 3;
```

## 类函数

- `static`函数被称为类函数，不属于任何对象，属于类本身
- 类函数中不可以调用非`static`的成员变量，只能调用类变量

```
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
  - `list()`

- 避免新手很容易犯的错误：不要去考虑数据是怎么输入输出的
  - 真正的软件，**人机交互**部分(输入输出)和**业务逻辑**部分(对数据进行计算)一定要分离
- 一个类只需要考虑这个类能够提供的功能

## 对象数组

## 集合容器(Set)

## 散列表(Hash)