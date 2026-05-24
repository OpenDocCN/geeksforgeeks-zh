# Scala 短整型 !=(x: Byte) 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-short-x-byte-method-with-example-4/](https://www.geeksforgeeks.org/scala-short-x-byte-method-with-example-4/)

`!=(x: Byte)` 方法用于检查所述短值是否不等于 `x`。`x` 是字节类型。

> **方法定义:** `def !=(x: Byte): Boolean`
>
> **返回类型:** 如果所述短值不等于 `x`，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of !=(x: Byte)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying !=(x: Byte) method
        val result = (-1000).!=(125)

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
// Scala program of !=(x: Byte)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying !=(x: Byte) method
        val result = (1000).!=(-125)

// Displays output
        println(result)

    }
}
```

**输出:**

```scala
true
```