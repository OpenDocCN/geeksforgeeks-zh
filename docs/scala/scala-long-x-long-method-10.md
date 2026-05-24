# 斯卡拉隆& (x:隆)法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-long-method-10/](https://www.geeksforgeeks.org/scala-long-x-long-method-10/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。 **& (x: Long)** 方法用于返回指定的 Long 值和 Long 值的按位与。

> **方法定义–**定义& (x:长)
> 
> **返回–**返回该值与 x 的按位“与”

**示例#1:**

```scala
// Scala program to explain working of
// &(x: Long) method

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

// Applying &(x: Long) method 
val result = (13.toLong).&(28:Long)

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
// &(x: Long) method

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

// Applying &(x: Long) method 
val result = (7.toLong).&(11:Long)

// Displays output
println(result)

}
} 
```

**输出:**

```scala
3
```