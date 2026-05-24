# Scala Long !=(x: Float) 方法，示例

> 原文: [https://www.geeksforgeeks.org/scala-long-x-float-method-with-example/](https://www.geeksforgeeks.org/scala-long-x-float-method-with-example/)

在 Scala 中，`Long` 是 64 位有符号整数，相当于 Java 的 `Long` 基元类型。`!=(x: Float)` 方法用于检查给定的 `Long` 值是否相等。

> **方法定义–** `def !=(x: Float): Boolean`
>
> **返回–** 如果该值不等于 `x`，则返回 `true`，否则返回 `false`。

## 示例#1

```scala
// Scala program to explain working
// of Long !=(x: Float) function

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying !=(x: Float) function
        val result = (10).toLong.!=(10.0)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
false
```

## 例 2

```scala
// Scala program to explain working
// of Long !=(x: Float) function

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying !=(x: Float) function
        val result = 1186000000.toLong.!= (1296000.5)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
true
```