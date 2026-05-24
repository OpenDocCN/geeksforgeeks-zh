# Scala Char > =(x: Byte)方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-3/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-3/)

使用 `>=(x: Byte)` 方法来查找所述字符值是否大于或等于 `x`。`x` 的类型必须是 `Byte`。

> **方法定义:** `def >=(x: Byte): Boolean`
>
> **返回类型:** 如果所述字符值大于或等于 `x`，则返回 `true`，否则返回 `false`。

## 例:1

```scala
// Scala program of >=(x: Byte)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying >=(x: Byte) method
        val result = 'D'.>=(-127)

// Displays output
        println(result)

    }
}
```

**Output:**

```scala
true
```

## 例:2

```scala
// Scala program of >=(x: Byte)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying >=(x: Byte) method
        val result = 'D'.>=(123)

// Displays output
        println(result)

    }
}
```

**Output:**

```scala
false
```