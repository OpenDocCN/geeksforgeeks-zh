# 斯卡拉飘！=(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-byte-method-with-example-9/](https://www.geeksforgeeks.org/scala-float-x-byte-method-with-example-9/)

**！=(x: Byte)** 方法用于检查给定的 Float 和 Byte 值是否相等。

> **方法定义:** (Float_Value)！=(x:字节)
> 
> **返回类型:**如果给定的 Float 和 Byte 值不相等，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Float !=(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Byte) function
        val result = (65.0).!=(65.0)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

**例 2:**

```scala
// Scala program of Float !=(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Byte) function
        val result = (65.0).!=(45)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```