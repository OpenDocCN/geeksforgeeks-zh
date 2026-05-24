# Scala short&(x:Int):Int

> 原文:[https://www.geeksforgeeks.org/scala-short-x-int-int-2/](https://www.geeksforgeeks.org/scala-short-x-int-int-2/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。使用&(x: Int)方法返回由 Int 值对指定的 Int 值进行按位 AND 运算的结果。

> **方法定义:** def +(x: Int): Int
> 
> **返回类型:**返回 Int。

**示例#1:**

```scala
// Scala program of Short &(x: Int) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short &(x: Int) function 
        val result = (998.toInt).&(1000:Int)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
992

```

**例 2:**

```scala
// Scala program of Short &(x: Int) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short &(x: Int) function 
        val result = (111.toInt).&(1000:Int) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
104

```