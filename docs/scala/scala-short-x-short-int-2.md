# Scala Short&(x:Short):Int

> 原文:[https://www.geeksforgeeks.org/scala-short-x-short-int-2/](https://www.geeksforgeeks.org/scala-short-x-short-int-2/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。使用&(x: Int)方法返回由 Int 值对指定短值进行按位 AND 运算的结果。

> **方法定义:** def +(x: Short): Int
> 
> **返回类型:**返回 Int。

**示例#1:**

```scala
// Scala program of Short &(x: Short) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short &(x: Short) function 
        val result = (998.toShort).&(1000:Int)

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
// Scala program of Short &(x: Short) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short &(x: Short) function 
        val result = (-111.toShort).&(1000:Int) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
896

```