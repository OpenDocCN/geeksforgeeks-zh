# Scala short /(x: Short): Int

> 原文:[https://www.geeksforgeeks.org/scala-short-x-short-int/](https://www.geeksforgeeks.org/scala-short-x-short-int/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。/(x: Short)方法用于返回对 x 指定的短值进行商运算的结果

> **方法定义:** def /(x: Short): Int
> 
> **返回类型:**返回值为 x 的商。

**示例#1:**

```scala
// Scala program of Short /(x: Short) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Int) function 
        val result = (998.toShort)./(20:Short)

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
// Scala program of Short /(x: Short) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short /(x: Short) function 
        val result = (-111.toShort)./(47:Short)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
-2
```