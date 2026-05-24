# Scala `Int > (x: Short)` 方法详解

> 原文：[https://www.geeksforgeeks.org/scala-int-x-short-method-with-example-11/](https://www.geeksforgeeks.org/scala-int-x-short-method-with-example-11/)

如果指定的 `Int` 值大于 `Short` 值，则使用 `>(x: Short)` 方法返回 `true`。

## 方法定义

`(Int_Value).>(Short_Value)`

**返回类型：** 如果指定的 `Int` 值大于 `Short` 值，则返回 `true`。

## 示例 1

```scala
// Scala program of Int >(x: Short)
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying Int >(x: Short) function
        val result = (65).>(10)

        // Displays output
        println(result)
    }
}
```

**输出：**

```scala
true
```

## 示例 2

```scala
// Scala program of Int >(x: Short)
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying Int >(x: Short) function
        val result = (50).>(100)

        // Displays output
        println(result)
    }
}
```

**输出：**

```scala
false
```