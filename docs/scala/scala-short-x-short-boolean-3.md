# 斯卡拉短> (x:短):布尔

> 原文:[https://www . geesforgeks . org/Scala-short-x-short-boolean-3/](https://www.geeksforgeeks.org/scala-short-x-short-boolean-3/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的一个子类型。如果该值大于 x，则使用>(x: Short)方法返回 true，否则返回 false。

> **方法定义:** def > (x:短):布尔值
> 
> **返回类型:**如果该值大于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Short >(x: Short) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short >(x: Short) function 
        val result = (998.toShort).>(999:Short)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
false

```

**例 2:**

```scala
// Scala program of Short >(x: Short) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short >(x: Short) function 
        val result = (102.toShort).>(101:Short)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
true

```