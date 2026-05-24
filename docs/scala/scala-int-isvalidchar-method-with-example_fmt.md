# Scala Int isValidChar() 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-int-isvalidchar-method-with-example/](https://www.geeksforgeeks.org/scala-int-isvalidchar-method-with-example/)

如果指定的 `Int` 数为零或在 `scala.Char.MinValue` 和 `scala.Char.MaxValue` 范围内，则使用 `isValidChar()` 方法返回 `true`，否则返回 `false`。

> **方法定义:** `(Int_Number).isValidChar`
>
> **返回类型:** 如果指定的数字为零或在 `scala.Char.MinValue` 和 `scala.Char.MaxValue` 范围内，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of Int isValidChar()
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying isValidChar method
        val result = (0).isValidChar

// Displays output
        println(result)

    }
}
```

**输出:**

```scala
true
```

## 示例 2

```scala
// Scala program of Int isValidChar()
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying isValidChar method
        val result = (5.9).isValidChar

// Displays output
        println(result)

    }
}
```

**输出:**

```scala
false
```