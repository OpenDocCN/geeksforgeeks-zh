# Scala Char

> 原文: [https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-7/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-7/)

使用 `<(x: Byte)` 方法来查找所述字符值是否小于 `x`。`x` 的类型必须是 `Byte`。

## 方法定义

`def <(x: Byte): Boolean`

## 返回类型

如果指定的字符值小于 `x`，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of <(x: Byte)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying <(x: Byte) method
        val result = 'D'.<(127)

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
// Scala program of <(x: Byte)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying <(x: Byte) method
        val result = 'D'.<(-127)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
false
```