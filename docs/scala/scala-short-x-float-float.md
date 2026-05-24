# Scala 短/(x: Float): Float

> 原文:[https://www.geeksforgeeks.org/scala-short-x-float-float/](https://www.geeksforgeeks.org/scala-short-x-float-float/)

简而言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。使用/(x: Float)方法返回 x 对指定 Float 值进行商运算的结果

> **方法定义:** def /(x: Float): Float
> 
> **返回类型:**返回值为 x 的商。

**示例#1:**

```scala
// Scala program of Short /(x: Float) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Float) function 
        val result = (998.toShort)./(22:Float)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
45.363636

```

**例 2:**

```scala
// Scala program of Short /(x: Float) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Float) function 
        val result = (-111.toShort)./(47:Float)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-2.3617022

```