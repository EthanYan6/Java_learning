# Java 基础

学习一门语言，第一件事当然是输出 `Hello Wrold`，下面使用 `Java` 编写一个最简单的应用程序：

```java
public class FirstSample
{
    public static void main(String[] args)
    {
        System.out.println("Hello Wrold!");
    }
}
```

**注意事项：**

1.Java 对大小写敏感。

2.`public` 为访问修饰符，此处简单理解为它用于控制程序的其他部分对这段代码的访问级别。

3.`class` 为类，表明 Java 程序中的全部内容都包含在类中。

4.关键字 `class` 后面紧跟类名。

> 类名定义规则：名字以字母开头，后面可以跟字母和数字的任意组合，每个单词首字母大写。长度不受限制。同 Python，起名不能使用 Java 的保留字，如 public 等。（凡事讲究先来后到）
>
> 如果你有一些编程基础，那么可以理解为它符合驼峰命名规则。

5.在文件中书写完上述代码后，文件需命名为 `FirstSample.java`

> **源代码的文件名必须与公共类的名字相同，且大小写一定要注意！！！**

6.Java 中代码块都是以大括号包裹起来的。

## 1.输出

上面已经有了最简单的输出方式：

```java
System.out.println();
```

它使用了 `System.out` 对象的 `println` 方法。类似于 Python 中的 `print()`

> 如果你想输出语句后，不执行换行的效果，可以使用 `System.out` 对象的 `print`方法。类比 Python 中如下代码：
>
> ```python
> print("xxx", end="")
> ```

下面测试一下：

```java
public class HelloDemo {
    public static void main(String[] args) {
        // 尝试 println 方法
        System.out.println("hello world");
        System.out.println("Ethan");
        // 尝试 print 方法
        System.out.print("hello world");
        System.out.print("Ethan");
    }
}
```

最后输出结果为：

```java
hello world
Ethan
hello worldEthan
```

> 可看出 println 自带换行效果，print 则无此效果。

## 2.注释

注释为了让日后自己还能看懂自己的代码，或者让别人接盘。下面看一下 Java 中是如何书写注释的：

### 2.1 单行注释

单行注释使用符号 `//`，其注释内容从 `//` 开始到本行结束，例：

```java
// 我是单行注释
```

### 2.2 多行注释

多行注释使用符号 `/**` 开始，符号 `*/` 结束。例如：

```java
/**
 * 这是多行注释
 * 为了表明多行，这是第2行
 * 这是第3行
 */
```

> 也许你会好奇，为什么每一行注释前还有一个 `*` 号，这是使用编辑器 `IDEA` 时输入 `/**` 后按回车键自动生成的效果。

## 3.数据类型

Java 是一种强类型语言，即在使用变量前需声明其类型。在 Java 中共有 8 中基本数据类型，其中 4 种整型、2种浮点类型、1种用于表示 Unicode 编码的字符单元的字符类型 char 和一种用于表示真值的布尔类型 boolean。

### 3.1 整型

#### long 类型

long 类型同样有正负，存储时占用 8 字节，其取值范围为 `-2^63` 到 `2^63-1`

```java
long l = 100000L 
long l1 = -100000L
```

> "L"理论上不分大小写，但是若写成"l"容易与数字"1"混淆，不容易分辩。所以最好大写。
> 这种类型主要使用在需要比较大整数的系统上


#### int 类型

int 是我们最熟悉的整数，可表示正负。存储时占用 4 字节。取值范围为 `-2^31` 到 `2^31-1 `

```java
int a = 100000
int a1 = -520000
```
> 一般地整型变量默认为 int 类型

#### short 类型

short 也有正负之分，存储时占用 2 字节，其取值范围为 `-2^15` 到 `2^15-1`

```java
short s = 100
short s1 = -1000
```
> short 数据类型也可以像 byte 那样节省空间。一个short变量是int型变量所占空间的二分之一

#### byte 类型

byte 类型可表示正负，存储时占用 1 字节，其取值范围为 `-2^7` 到 `2^7-1`

```java
byte b = 50
byte b = -50
```

> byte 类型用在大型数组中节约空间，主要代替整数，因为byte 变量占用的空间只有 int 类型的四分之一；

### 3.2 浮点类型

#### float 类型

float 类型表示单精度小数，存储时占用 4 字节。它在存储大型浮点数组时可节省内存空间，但是其**不能用来表示精确的值**。

```java
float f1 = 234.5f
```

#### double 类型

double 数据类型是双精度小数，存储时占用 8 字节。浮点数默认类型便是 double 类型，同样，它也**不能用来表示精确的值**，如货币。

```java
double d1 = 123.4b
```

> 因为 double 是默认类型，所以数字末尾的 `b ` 写不写均可

### 3.3 char 类型

char 类型用来表示单个字符，如 `'A'` 是编码 65 对应的字符常量。注意它不是字符串。Unicode 编码单元可以表示为十六进制值，其范围为 `\u0000` 到 `\Uffff`。

> 通常用来表示字符常量。

### 3.4 布尔类型

布尔类型只有两个值，便是 `True` 和 `False`

> **注意：**Java 中与 Python 中不同。Python 中与 C++ 中类似，数值 0 可以代替 `False` ，非 0 表示 `True` 而 Java中不可以！

## 4.变量

