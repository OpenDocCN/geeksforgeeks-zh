# Scala Char to(end: Char, step: Char) 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-toend-char-step-char-method-with-example/](https://www.geeksforgeeks.org/scala-char-toend-char-step-char-method-with-example/)

`to(end: Char, step: Char)` 方法用于返回从所述字符到 `end` 的范围，该范围在参数列表中给出，并且在参数列表中也指定了一些 `step`。

## 方法定义

定义为 `to(end: Char, step: Char): Collection[Char]`

## 返回类型

返回范围。

## 示例 1

```scala
// Scala program of to()
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying to() method
        val result = 'A'.to('G', 2)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
NumericRange(A, C, E, G)
```

## 示例 2

```scala
// Scala program of to()
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying to() method
        val result = ('0').to('9', 3)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
NumericRange(0, 3, 6, 9)
```