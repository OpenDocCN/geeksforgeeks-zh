# Scala Char >=(x: Int) 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-x-int-method-with-example-13/](https://www.geeksforgeeks.org/scala-char-x-int-method-with-example-13/)

使用 `>=(x: Int)` 方法来查找所述字符值是否大于或等于 `x`。`x` 的类型必须是整数。

## 方法定义

> `def >=(x: Int): Boolean`
>
> **返回类型:** 如果所述字符值大于或等于 `x`，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of >=(x: Int)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying >=(x: Int) method
        val result = 'D'.>=(56)

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
// Scala program of >=(x: Int)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying >=(x: Int) method
        val result = 'D'.>=(74)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
false
```