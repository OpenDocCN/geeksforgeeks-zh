# Scala Char isSurrogate() 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-issurrogate-method-with-example/](https://www.geeksforgeeks.org/scala-char-issurrogate-method-with-example/)

`isSurrogate()` 方法用于查找所述字符值是否是 Unicode 替代代码单元。这些值本身并不表示字符，而是用于表示 UTF-16 编码中的补充字符。

> **方法定义:** `def isSurrogate: Boolean`
>
> **返回类型:** 如果指定的字符是替代字符，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of isSurrogate()
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying isSurrogate() method
        val result = ('\ud8b4').isSurrogate

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
// Scala program of isSurrogate()
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying isSurrogate() method
        val result = ('\u0555').isSurrogate

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
false
```