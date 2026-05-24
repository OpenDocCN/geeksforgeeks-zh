# 斯卡拉短& (x:长):长

> 原文:[https://www.geeksforgeeks.org/scala-short-x-long-long-2/](https://www.geeksforgeeks.org/scala-short-x-long-long-2/)

短，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。使用&(x: Long)方法返回长值对指定长值的按位 AND 运算的结果。

> **方法定义:** def +(x: Long): Long
> 
> **返回类型:**返回 Long。

**示例#1:**

```scala
// Scala program of Short &(x: Long) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Long &(x: Long) function 
        val result = (998).&(100000L)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
672

```

**例 2:**

```scala
// Scala program of Short &(x: Long) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Long &(x: Long) function 
        val result = (111).&(-100000L) 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
96

```