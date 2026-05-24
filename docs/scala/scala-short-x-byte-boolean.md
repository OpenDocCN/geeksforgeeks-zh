# 斯卡拉短

T2】原文:[https://www.geeksforgeeks.org/scala-short-x-byte-boolean/](https://www.geeksforgeeks.org/scala-short-x-byte-boolean/)T5】

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的子类型。如果该值小于 x，则使用

> **方法定义:** def < (x:字节):布尔值
> 
> **返回类型:**如果该值小于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Short <(x: Byte) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short <(x: Byte) function 
        val result = (998.toShort).<(11:Byte)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
False

```

**例 2:**

```scala
// Scala program of Short <(x: Byte) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short <(x: Byte) function 
        val result = (102.toShort).<(101:Byte)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
false

```