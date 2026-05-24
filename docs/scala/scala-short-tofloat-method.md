# Scala Short toFloat()方法

> 原文:[https://www.geeksforgeeks.org/scala-short-tofloat-method/](https://www.geeksforgeeks.org/scala-short-tofloat-method/)

简而言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。toFloat()方法用于将指定的数字转换为 Float 数据类型值。

> **方法定义:**(数字)。toFloat
> 
> **返回类型:**返回转换后的浮点值。

**示例#1:**

```scala
// Scala program of Short toFloat() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toFloat method 
        val result = (13).toFloat

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
// Scala program of Short toFloat() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toFloat method 
        val result = (123).toFloat

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
123.0

```