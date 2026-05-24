# 斯卡拉双

T2】原文:[https://www.geeksforgeeks.org/scala-double-x-byte-method-5/](https://www.geeksforgeeks.org/scala-double-x-byte-method-5/)T5】

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。如果该值小于 x，则使用 **< (x:字节)**方法返回真，否则返回假。

> **方法定义–**定义< (x:字节):布尔值
> 
> **返回–**如果该值小于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program to explain the working 
// of Double <(x: Byte) method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Byte) function
        val result = (12.00123.toDouble).<(15:Byte)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```