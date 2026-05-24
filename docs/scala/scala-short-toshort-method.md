# Scala Short toShort()方法

> 原文:[https://www.geeksforgeeks.org/scala-short-toshort-method/](https://www.geeksforgeeks.org/scala-short-toshort-method/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。toShort()方法用于将指定的数字转换为短数据类型值。

> **方法定义:**(数字)。toShort
> 
> **返回类型:**返回转换后的短值。

**示例#1:**

```scala
// Scala program of Short toShort() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toShort method 
        val result = (13).toShort

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
13

```

**例 2:**

```scala
// Scala program of Short toShort() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toShort method 
        val result = (123.4).toShort

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
123

```