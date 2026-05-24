# Scala Long & (x: Byte)方法

> 原文:[https://www.geeksforgeeks.org/scala-long-x-byte-method-9/](https://www.geeksforgeeks.org/scala-long-x-byte-method-9/)

在 Scala 中，long 是 64 位有符号整数，相当于 Java 的 Long 基元类型。 **& (x:字节)**方法用于返回指定的长值和字节值的按位与。

> **方法定义–**定义& (x:字节)
> 
> **返回–**返回该值与 x 的按位“与”

**示例#1:**

```scala
// Scala program to explain working of
// &(x: Byte) method

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

// Applying &(x: Byte) method 
val result = (13.toLong).&(2^3:Byte)

// Displays output
println(result)

}
} 
```

**输出:**

```scala
1
```

**例 2:**

```scala
// Scala program to explain working of
// &(x: Byte) method

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

// Applying &(x: Byte) method 
val result = (7.toLong).&(2^7:Byte)

// Displays output
println(result)

}
} 
```

**输出:**

```scala
5
```