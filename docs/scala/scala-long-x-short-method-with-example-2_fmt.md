# Scala `Long.!=(x: Short)` 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-long-x-short-method-with-example-2/](https://www.geeksforgeeks.org/scala-long-x-short-method-with-example-2/)

在 Scala 中，`Long` 是 64 位有符号整数，相当于 Java 的 `Long` 基元类型。`!=(x: Short)` 方法用于检查给定的 `Long` 值和 `Short` 值是否相等。

## 方法定义

```scala
def !=(x: Short): Boolean
```

## 返回值

如果该值不等于 `x`，则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program to explain working 
// of Long !=(x: Short) function

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying !=(x: Short) function
        val result = (66).toLong.!= (66:Short)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
false
```

## 示例 #2

```scala
// Scala program to explain working
// of Long !=(x: Short) function

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying !=(x: Short) function
        val result = 1186000000.toLong.!= (16:Short)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
true
```