# 斯卡拉隆& (x: Char)法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-char-method-9/](https://www.geeksforgeeks.org/scala-long-x-char-method-9/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。 **& (x: Char)** 方法用于返回指定的 Long 值和 Char 值的按位与。

> **方法定义–**定义& (x:字符)
> 
> **返回–**返回该值与 x 的按位“与”

**示例#1:**

```scala
// Scala program to explain working of
// &(x: Char) method

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

// Applying &(x: Char) method 
val result = (13.toLong).&('G':Char)

// Displays output
println(result)

}
} 
```

**输出:**

```scala
5
```

**例 2:**

```scala
// Scala program to explain working of
// &(x: Char) method

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

// Applying &(x: Char) method 
val result = (7.toLong).&('A':Char)

// Displays output
println(result)

}
} 
```

**输出:**

```scala
1
```