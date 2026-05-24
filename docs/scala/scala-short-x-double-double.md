# Scala 短/(x: Double): Double

> 原文:[https://www.geeksforgeeks.org/scala-short-x-double-double/](https://www.geeksforgeeks.org/scala-short-x-double-double/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。使用/(x: Int)方法返回 x 对指定的 Double 值进行商运算的结果

> **方法定义:** def /(x: Double): Double
> 
> **返回类型:**返回值为 x 的商。

**示例#1:**

```scala
// Scala program of Short /(x: Double) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Double) function 
        val result = (998.toShort)./(22:Double)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
45.36363636363637

```

**例 2:**

```scala
// Scala program of Short /(x: Double) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Double) function 
        val result = (-111.toShort)./(47:Double)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-2.3617021276595747

```