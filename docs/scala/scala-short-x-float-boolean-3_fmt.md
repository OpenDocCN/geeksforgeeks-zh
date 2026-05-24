# Scala Short > (x: Float): Boolean

> 原文: [https://www.geeksforgeeks.org/scala-short-x-float-boolean-3/](https://www.geeksforgeeks.org/scala-short-x-float-boolean-3/)

## 概述
简言之，16位有符号整数（相当于Java的`short`原语类型）是`scala.AnyVal`的一个子类型。如果该值大于`x`，则使用`>(x: Float)`方法返回`true`，否则返回`false`。

> **方法定义:** `def >(x: Float): Boolean`
>
> **返回类型:** 如果该值大于`x`，则返回`true`，否则返回`false`。

## 示例 #1

```scala
// Scala program of Short >(x: Float) 
// method

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Applying Short >(x: Float) function 
        val result = (998.toShort).>(999:Float)

// Displays output 
        println(result)

} 
} 
```

**输出:**

```scala
false
```

## 示例 #2

```scala
// Scala program of Short >(x: Float) 
// method

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Applying Short >(x: Float) function 
        val result = (102.toShort).>(101:Float)

// Displays output 
        println(result)

} 
} 
```

**输出:**

```scala
true
```