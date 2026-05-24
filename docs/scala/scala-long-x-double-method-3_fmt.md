# Scala Long <=(x: Double) 方法

> 原文: `https://www.geeksforgeeks.org/scala-long-x-double-method-3/`

在 Scala 中，`Long` 是 64 位有符号整数，相当于 Java 的 `Long` 基元类型。如果该值小于或等于 `x`，则使用 `<= (x: Double)` 方法返回 `true`，否则返回 `false`。

## 方法定义

```scala
def <=(x: Double): Boolean
```

## 返回值

如果该值小于或等于 `x`，则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program to explain the working
// of Long <=(x: Double) method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying <=(x: Double) function
        val result = (12.toLong).<=(8: Double)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
false
```