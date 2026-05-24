# 斯卡拉隆& (x: Int)法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-int-method-9/](https://www.geeksforgeeks.org/scala-long-x-int-method-9/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。 **& (x: Int)** 方法用于返回指定的 Long 值和 Int 值的按位 AND。

> **方法定义–**定义& (x: Int)
> 
> **返回–**返回该值与 x 的按位“与”

**示例#1:**

```scala
// Scala program to explain working of
// &(x: Int) method

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

// Applying &(x: Int) method 
val result = (13.toLong).&(28:Int)

// Displays output
println(result)

}
} 
```

**输出:**

```scala
12
```

**例 2:**

```scala
// Scala program to explain working of
// &(x: Int) method

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

// Applying &(x: Int) method 
val result = (7.toLong).&(11:Int)

// Displays output
println(result)

}
} 
```

**输出:**

```scala
3
```