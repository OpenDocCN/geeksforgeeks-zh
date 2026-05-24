# Scala Int ==(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-byte-method-with-example-6/](https://www.geeksforgeeks.org/scala-int-x-byte-method-with-example-6/)

如果指定的 int 值等于 Byte 值，则使用 **==(x: Byte)** 方法返回 true，否则返回 false。

> **方法定义:** (Int_Value)。==(Byte_Value)
> 
> **返回类型:**如果指定的 int 值等于 Byte 值则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int ==(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int ==(x: Byte) function
        val result = (10).==(10)

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
// Scala program of Int ==(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int ==(x: Byte) function
        val result = (500).==(100)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
false

```