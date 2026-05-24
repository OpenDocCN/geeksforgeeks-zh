# Scala Byte %(x: Long): Long

> 原文: [https://www.geeksforgeeks.org/scala-byte-x-long-long/](https://www.geeksforgeeks.org/scala-byte-x-long-long/)

在 Scala 中，`Byte` 是一个 8 位有符号整数（相当于 Java 的 `byte` 基元类型）。方法 `%(x: Long)` 用于返回该值除以 `x` 的余数。

## 方法定义

`Byte %(x: Long): Long`

**返回类型:** 返回该值除以 `x` 的余数。

## 示例 #1

```scala
// Scala program of Byte %(x: Long)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying Byte %(x: Long) function
        val result = (100.toByte).%(3: Long)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala

```

## 示例 2

```scala
// Scala program of Byte %(x: Long)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying Byte %(x: Long) function
        val result = (167.toByte).%(3: Long)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala

```