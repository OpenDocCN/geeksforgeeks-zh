# Scala Char isLetterOrDigit() 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-isletterordigit-method-with-example/](https://www.geeksforgeeks.org/scala-char-isletterordigit-method-with-example/)

`isLetterOrDigit()` 方法用于检查所述字符是字母还是数字。

> **方法定义:** `def isLetterOrDigit: Boolean`
>
> **返回类型:** 如果所述字符是字母或数字，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of isLetterOrDigit()
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying isLetterOrDigit method
        val result = '9'.isLetterOrDigit

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
// Scala program of isLetterOrDigit()
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying isLetterOrDigit method
        val result = 'g'.isLetterOrDigit

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
true
```