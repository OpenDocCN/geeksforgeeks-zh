# Scala Float.until(end: Float, step: Float) 方法及示例

> 原文: [https://www.geeksforgeeks.org/scala-float-untilend-float-step-float-method-with-example/](https://www.geeksforgeeks.org/scala-float-untilend-float-step-float-method-with-example/)

`until(end: Float, step: Float)` 方法用于返回一个从起始值到指定结束浮点值（不包含结束值）的范围。该范围的值按指定的步长递增。

> **方法定义:** `def until(end: Float, step: Float): collection.immutable.Range`
>
> **返回类型:** 返回一个 `Range`。

## 示例 #1

```scala
// Scala program of Float until()
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying until method
        val result = (1.0).until(12.0, 3.0)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
NumericRange(1.0, 4.0, 7.0, 10.0)
```

## 示例 #2

```scala
// Scala program of Float until()
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying until method
        val result = (3.0).until(20.0, 2.0)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
NumericRange(3.0, 5.0, 7.0, 9.0, 11.0, 13.0, 15.0, 17.0, 19.0)
```