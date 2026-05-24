# Scala Float >=(x: Long) 方法示例

> 原文：`https://www.geeksforgeeks.org/scala-float-x-long-method-with-example-11/`

如果浮点值大于或等于指定的长整型值，则使用 `>=(x: Long)` 方法返回真。

> **方法定义：** `(Float_Value).>=(Long_Value)`
> **返回类型：** 如果浮点值大于或等于指定的长整型值，则返回 `true`。

## 示例 #1

```scala
// Scala program of Float >=(x: Long)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying >=(x: Long) function
        val result = (100.0).>=(60)

// Displays output
        println(result)

    }
}
```

**输出：**

```scala
true
```

## 示例 #2

```scala
// Scala program of Float >=(x: Long)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying >=(x: Long) function
        val result = (10.0).>=(60)

// Displays output
        println(result)

    }
}
```

**输出：**

```scala
false
```