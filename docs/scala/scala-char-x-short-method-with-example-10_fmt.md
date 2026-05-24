# Scala Char > (x: Short) 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-x-short-method-with-example-10/](https://www.geeksforgeeks.org/scala-char-x-short-method-with-example-10/)

使用 `>(x: Short)` 方法来查找所述字符值是否大于 `x`。`x` 的类型必须是 `Short`。

> **方法定义:** `def >(x: Short): Boolean`
>
> **返回类型:** 如果所述字符值大于 `x`，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of >(x: Short)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying >(x: Short) method
        val result = 'D'.>(10000)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
false
```

## 示例 2

```scala
// Scala program of >(x: Short)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying >(x: Short) method
        val result = 'D'.>(-10000)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
true
```