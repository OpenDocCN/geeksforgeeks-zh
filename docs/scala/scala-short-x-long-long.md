# Scala 短/(x:长):长

> 原文:[https://www.geeksforgeeks.org/scala-short-x-long-long/](https://www.geeksforgeeks.org/scala-short-x-long-long/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。使用/(x: Long)方法返回对 x 指定的 Long 值进行商运算的结果

> **方法定义:** def /(x: Long): Long
> 
> **返回类型:**返回值为 x 的商。

**示例#1:**

```scala
// Scala program of Short /(x: Long) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Long) function 
        val result = (998.toShort)./(20:Long)

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
// Scala program of Short /(x: Long) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Long) function 
        val result = (-111.toShort)./(47:Long)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-2

```