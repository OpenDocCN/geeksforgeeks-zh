# Scala Short %(x: Byte)方法，示例

> 原文: [https://www.geeksforgeeks.org/scala-short-x-byte-method-with-example-5/](https://www.geeksforgeeks.org/scala-short-x-byte-method-with-example-5/)

使用 `%(x: Byte)` 方法来寻找所述短值除以 Byte 类型的 `x` 的余数。

> **方法定义:** `def %(x: Byte): Int`
>
> **返回类型:** 返回 `Int`。

## 示例1

```scala
// Scala program of %(x: Byte)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying %(x: Byte) method
        val result = (1000).%(111)

// Displays output
        println(result)

    }
}
```

**输出:**

```scala

```

## 示例2

```scala
// Scala program of %(x: Byte)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying %(x: Byte) method
        val result = (-1000).%(-116)

// Displays output
        println(result)

    }
}
```

**输出:**

```scala

```