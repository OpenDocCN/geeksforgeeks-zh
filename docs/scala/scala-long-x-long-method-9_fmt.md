# Scala Long %(x: Long) 方法

> 原文: [https://www.geeksforgeeks.org/scala-long-x-long-method-9/](https://www.geeksforgeeks.org/scala-long-x-long-method-9/)

在 Scala 中，`Long` 是 64 位有符号整数，相当于 Java 的 `long` 基本类型。当给定一个 `Long` 值除以另一个 `Long` 值时，使用 `%(x: Long)` 方法返回余数。

## 方法定义

```scala
def %(x: Long): Long
```

## 返回值

返回该值除以 `x` 的余数。

## 示例 1

```scala
// Scala program to explain the working 
// of Long %(x: Long) method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying %(x: Long) function
        val result = (125.toLong).%(8: Long)

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
// Scala program to explain the working 
// of Long %(x: Long) method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying %(x: Long) function
        val result = (165.toLong).%(13: Long)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala

```