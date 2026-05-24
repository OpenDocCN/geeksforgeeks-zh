# Scala Int | (x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-byte-method-with-example-16/](https://www.geeksforgeeks.org/scala-int-x-byte-method-with-example-16/)

**|(x: Byte)** 方法用于返回一个值，该值是 int 和指定字节值的按位“或”运算的结果。

> **方法定义:** (Int_Value)。|(字节值)
> **返回类型:**它返回一个值，该值是 int 和指定字节值的按位 OR 运算的结果。

**示例#1:**

```scala
// Scala program of Int |(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int |(x: Byte) function
        val result = (15).|(2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
15

```

**例 2:**

```scala
// Scala program of Int |(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int |(x: Byte) function
        val result = (13).|(9)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
13

```