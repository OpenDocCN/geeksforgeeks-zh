# Scala Byte 类型的 `-(x:Float):Float` 方法

> 原文: [https://www.geeksforgeeks.org/scala-byte-x-float-float-2/](https://www.geeksforgeeks.org/scala-byte-x-float-float-2/)

在 Scala 中，`Byte` 是一个 8 位有符号整数（相当于 Java 的 `byte` 基元类型）。`-(x:Float)` 方法用于返回该值与 `x` 的差值。

> **方法定义:** `Byte -(x: Float): Float`
> **返回类型:** 返回该值减去 `x` 的差。

## 示例 1

```scala
// Scala program of Byte -(x: Float)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying Byte -(x: Float) function
        val result = (167.toByte).-(125:Float)

// Displays output
        println(result)

}
}
```

**输出:**

```scala
-213.0
```

## 示例 2

```scala
// Scala program of Byte -(x: Float)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying Byte -(x: Float) function
        val result = (128.toByte).-(2:Float)

// Displays output
        println(result)

}
}
```

**输出:**

```scala
-130.0
```