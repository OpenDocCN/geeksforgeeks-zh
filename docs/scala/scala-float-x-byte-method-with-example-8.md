# Scala Float %(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-byte-method-with-example-8/](https://www.geeksforgeeks.org/scala-float-x-byte-method-with-example-8/)

当给定的浮点值除以字节值时，使用 **%(x: Byte)** 方法返回余数。

> **方法定义:** (Float_Value)。%(字节值)
> 
> **返回类型:**当给定的浮点值除以字节值时，返回余数。

**示例#1:**

```scala
// Scala program of Float %(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Byte) function
        val result = (65.0).%(65)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0.0

```

**例 2:**

```scala
// Scala program of Float %(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Byte) function
        val result = (100.0).%(65)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
35.0

```