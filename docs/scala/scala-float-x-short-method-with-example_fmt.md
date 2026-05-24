# Scala Float ==(x: Short) 方法示例

> 原文：[`https://www.geeksforgeeks.org/scala-float-x-short-method-with-example/`](https://www.geeksforgeeks.org/scala-float-x-short-method-with-example/)

如果浮点值等于短值，则使用 `==(x: Short)` 方法返回 `true`，否则返回 `false`。

**方法定义：** `(Float_Value).==(Short_Value)`

**返回类型：** 如果浮点值等于短值则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of Float ==(x: Short)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying ==(x: Short) function
        val result = (100.0).==(50)

// Displays output
        println(result)

}
}
```

**输出：**

```scala
false
```

## 示例 2

```scala
// Scala program of Float ==(x: Short)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying ==(x: Short) function
        val result = (50.0).==(50)

// Displays output
        println(result)

}
}
```

**输出：**

```scala
true
```