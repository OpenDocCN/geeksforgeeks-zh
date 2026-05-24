# Byte.==(x: Double): Boolean

> 原文: [https://www.geeksforgeeks.org/scala-byte-x-double-boolean-5/](https://www.geeksforgeeks.org/scala-byte-x-double-boolean-5/)

在 Scala 中，`Byte` 是一个 8 位有符号整数（相当于 Java 的 `byte` 基元类型）。如果该值等于 `x`，则使用方法 `==(x:Double)` 返回 `true`，否则返回 `false`。

> `Byte.==(x:Double):Boolean`
> 如果该值等于 `x` 则返回 `true`，否则返回 `false`。

### 示例 1

```scala
// Scala program of Byte ==(x: Double)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying Byte ==(x: Double) function
        val result = (64.toByte).==(64:Double)

// Displays output
        println(result)

}
}
```

**输出:**

```scala
true
```

### 示例 2

```scala
// Scala program of Byte ==(x: Double)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying Byte ==(x: Double) function
        val result = (25.toByte).==(111:Double)

// Displays output
        println(result)

}
}
```

**输出:**

```scala
false
```