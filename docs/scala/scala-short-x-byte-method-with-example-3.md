# Scala Short *(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-byte-method-with-example-3/](https://www.geeksforgeeks.org/scala-short-x-byte-method-with-example-3/)

使用 ***(x: Byte)** 方法来寻找所述短值和类型 Byte 的“x”的乘积。

> **方法定义:** def *(x:字节):Int
> 
> **返回类型:**返回 Int。

**例:1#**

```scala
// Scala program of *(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Byte) method 
        val result = (777).*(126)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
97902

```

**例:2#**

```scala
// Scala program of *(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying *(x: Byte) method
        val result = (-1000).*(-125)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
125000

```