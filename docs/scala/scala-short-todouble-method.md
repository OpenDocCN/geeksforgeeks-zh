# Scala Short toDouble()方法

> 原文:[https://www.geeksforgeeks.org/scala-short-todouble-method/](https://www.geeksforgeeks.org/scala-short-todouble-method/)

简而言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。toDouble()方法用于将指定的数字转换为 Double 数据类型值。

> **方法定义:**(数字)。到 Double
> 
> **返回类型:**返回转换后的双精度值。

**示例#1:**

```scala
// Scala program of Short toDouble() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toDouble method 
        val result = (13).toDouble

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
13.0

```

**例 2:**

```scala
// Scala program of Short toDouble() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toDoublemethod 
        val result = (123).toDouble

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
123.0

```