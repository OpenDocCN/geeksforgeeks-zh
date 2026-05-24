# 斯卡拉短托查尔()法

> 原文:[https://www.geeksforgeeks.org/scala-short-tochar-method/](https://www.geeksforgeeks.org/scala-short-tochar-method/)

简而言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。toChar()方法用于将指定的数字转换为 Char 数据类型值。

> **方法定义:**(数字)。托哈尔
> 
> **返回类型:**返回转换后的字符值。

**示例#1:**

```scala
// Scala program of Short toChar() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toChar method 
        val result = (68).toChar 

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
D

```

**例 2:**

```scala
// Scala program of Short toChar() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying toChar method 
        val result = (123).toChar

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
{

```