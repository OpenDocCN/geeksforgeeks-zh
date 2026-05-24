# Scala Short +(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-byte-method-with-example-2/](https://www.geeksforgeeks.org/scala-short-x-byte-method-with-example-2/)

使用 **+(x: Byte)** 方法来寻找所述短值和 Int 类型的‘x’之和。

> **方法定义:** def +(x: Byte): Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of +(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Byte) method 
        val result = (991).+(126)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1117

```

**例:2#**

```scala
// Scala program of +(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying +(x: Byte) method
        val result = (-111).+(-125)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-236

```