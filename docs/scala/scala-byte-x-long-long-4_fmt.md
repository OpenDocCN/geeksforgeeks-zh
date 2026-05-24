# Scala `Byte.*(x: Long): Long` 方法

> 原文: [https://www.geeksforgeeks.org/scala-byte-x-long-long-4/](https://www.geeksforgeeks.org/scala-byte-x-long-long-4/)

在 Scala 中，`Byte` 是一个 8 位有符号整数（相当于 Java 的 `byte` 基元类型）。方法 `*(x:Long)` 用于返回该值与 `x` 的乘积。

## 方法定义

`Byte.*(x: Long): Long`

## 返回类型

返回该值与 `x` 的乘积。

## 示例 1

```scala
// Scala program of Byte *(x: Long)
// method

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying Byte *(x: Long) function
        val result = (64.toByte).*(12:Long)

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
// Scala program of Byte *(x: Long)
// method

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying Byte *(x: Long) function
        val result = (17.toByte).*(128:Long)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala

```