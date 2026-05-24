# 斯卡拉国际

T2】原文:[https://www . geeksforgeeks . org/Scala-int-x-byte-method-with-example-8/](https://www.geeksforgeeks.org/scala-int-x-byte-method-with-example-8/)

如果指定的 int 值小于 Byte 值，则使用 **< (x: Byte)** 方法返回 true，否则返回 false。

> **方法定义:** (Int_Value)。<(字节值)
> 
> **返回类型:**如果指定的 int 值小于字节值，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int <(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <(x: Byte) function
        val result = (100).<(110)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```