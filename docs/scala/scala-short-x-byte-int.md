# Scala short /(x: Byte): Int

> 原文:[https://www.geeksforgeeks.org/scala-short-x-byte-int/](https://www.geeksforgeeks.org/scala-short-x-byte-int/)

简而言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。使用/(x: Byte)方法返回 x 对指定的 Byte 值进行商运算的结果

> **方法定义:** def /(x: Byte): Int
> 
> **返回类型:**返回值为 x 的商。

**示例#1:**

```scala
// Scala program of Short /(x: Byte) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Byte) function 
        val result = (998.toShort)./(20:Byte)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
49

```

**例 2:**

```scala
// Scala program of Short /(x: Byte) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Byte) function 
        val result = (-111.toShort)./(47:Byte)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-2
```