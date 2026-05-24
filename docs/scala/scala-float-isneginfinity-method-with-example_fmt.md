# Scala Float isNegInfinity() 方法示例

> 原文：[https://www.geeksforgeeks.org/scala-float-isneginfinity-method-with-example/](https://www.geeksforgeeks.org/scala-float-isneginfinity-method-with-example/)

如果浮点值或指定的浮点值是负无穷大数，则使用 `isNegInfinity()` 方法返回真，否则返回假。

**方法定义：**
`(Float_Number).isNegInfinity`

**返回类型：**
如果浮点值或指定的浮点值为负无穷大，则返回真，否则返回假。

## 示例 1

```scala
// Scala program of Float isNegInfinity()
// method

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying isNegInfinity method
        val result = (8.9).isNegInfinity

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
// Scala program of Float isNegInfinity()
// method

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying isNegInfinity method
        val result = (-7.965).isNegInfinity

        // Displays output
        println(result)
    }
}
```

**输出：**

```scala
false
```