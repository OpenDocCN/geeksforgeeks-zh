# Scala Float >=(x: Byte) 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-float-x-byte-method-with-example-11/](https://www.geeksforgeeks.org/scala-float-x-byte-method-with-example-11/)

如果浮点值大于或等于指定的字节值，则使用 `>=(x: Byte)` 方法返回 `true`。

## 方法定义
`(Float_Value).>=(Byte_Value)`

## 返回类型
如果浮点值大于或等于指定的字节值，则返回 `true`。

## 示例 #1

```scala
// Scala program of Float >=(x: Byte)
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying >=(x: Byte) function
        val result = (100.0).>=(60)

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
// Scala program of Float >=(x: Byte)
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying >=(x: Byte) function
        val result = (10.0).>=(60)

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
false
```