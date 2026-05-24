# Scala Char <=(x: Double) 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-5/](https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-5/)

使用 `<= (x: Double)` 方法来查找所述字符值是否小于或等于 `x`。`x` 的类型必须是 `Double`。

## 方法定义

`def <= (x: Double): Boolean`

## 返回类型

如果所述字符值小于或等于 `x`，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of <=(x: Double)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying <=(x: Double) method
        val result = 'Z'.<=(90.4355)

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
// Scala program of <=(x: Double)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying <=(x: Double) method
        val result = 'Z'.<=(89.8655)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
false
```