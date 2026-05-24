# Scala Int !=(x: Byte) 方法详解与示例

> 原文: [https://www.geeksforgeeks.org/scala-int-x-byte-method-with-example-5/](https://www.geeksforgeeks.org/scala-int-x-byte-method-with-example-5/)

`!=(x: Byte)` 方法用于在 `Int` 值不等于指定的 `Byte` 值时返回 `true`，否则返回 `false`。

> **方法定义:** `(Int_Value).!=(Byte_Value)`
>
> **返回类型:** 如果 `Int` 值不等于指定的 `Byte` 值，则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program of Int !=(x: byte)
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying Int !=(x: byte) function
        val result = (100).!=(50)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
true
```

## 示例 #2

```scala
// Scala program of Int !=(x: byte)
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying Int !=(x: byte) function
        val result = (100).!=(100)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
false
```