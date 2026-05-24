# Scala Float 一元 _-方法示例

> 原文：[https://www.geeksforgeeks.org/scala-float-unary_-method-with-example-2/](https://www.geeksforgeeks.org/scala-float-unary_-method-with-example-2/)

利用`unary_-`方法返回相同的带负号的指定浮点值。

> **方法定义：** `(Float_Value).unary_-`
> **返回类型：** 返回相同的带负号的指定浮点值。

## 示例 1

```scala
// Scala program of Float unary_-
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying unary_- function
        val result = (65.0).unary_-

// Displays output
        println(result)

    }
}
```

**输出：**

```scala
-65.0
```

## 示例 2

```scala
// Scala program of Float unary_-
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying unary_- function
        val result = (115.9).unary_-

// Displays output
        println(result)

    }
}
```

**输出：**

```scala
-115.9
```