# 斯卡拉短

T2】原文:[https://www . geesforgeks . org/Scala-short-x-double-boolean-4/](https://www.geeksforgeeks.org/scala-short-x-double-boolean-4/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的子类型。如果该值小于 x，则使用

> **方法定义:** def < (x: Double):布尔值
> 
> **返回类型:**如果该值小于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Short <(x: Double) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short <(x: Double) function 
        val result = (998.toShort).<(998.002:Double)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
True

```

**例 2:**

```scala
// Scala program of Short <(x: Double) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short <(x: Double) function 
        val result = (102.toShort).<(101.999:Double)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
false

```