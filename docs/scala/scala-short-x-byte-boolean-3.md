# 斯卡拉短> =(x: Byte):布尔

> 原文:[https://www.geeksforgeeks.org/scala-short-x-byte-boolean-3/](https://www.geeksforgeeks.org/scala-short-x-byte-boolean-3/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的子类型。如果该值大于或等于 x，则使用> =(x: Byte)方法返回 true，否则返回 false。

> **方法定义:** def > =(x:字节):布尔值
> 
> **返回类型:**如果该值大于或等于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Short >=(x: Byte) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short >=(x: Byte) function 
        val result = (99.toShort).>=(11:Byte)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
true

```

**例 2:**

```scala
// Scala program of Short >=(x: Byte) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short >=(x: Byte) function 
        val result = (102.toShort).>=(101:Byte)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
true

```