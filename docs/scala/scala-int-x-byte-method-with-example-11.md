# Scala Int > (x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-byte-method-with-example-11/](https://www.geeksforgeeks.org/scala-int-x-byte-method-with-example-11/)

如果指定的 int 值大于 Byte 值，则使用 **> (x: Byte)** 方法返回 true。

> **方法定义:** (Int_Value)。>(字节值)
> **返回类型:**如果指定的 int 值大于字节值，则返回 true。

**示例#1:**

```scala
// Scala program of Int >(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >(x: Byte) function
        val result = (65).>(10)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of Int >(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >(x: Byte) function
        val result = (50).>(100)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```