# Scala `Float.underlying()` 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-float-underlying-method-with-example/](https://www.geeksforgeeks.org/scala-float-underlying-method-with-example/)

`underlying()` 方法用于返回相同的指定浮点值。

> **方法定义:** `def underlying(): AnyRef`
>
> **返回类型:** 返回相同的指定浮点值。

## 示例 1

```scala
// Scala program of Float underlying
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {
        // Applying underlying method
        val result = (5.0).underlying

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
5.0
```

## 示例 2

```scala
// Scala program of Float underlying
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {
        // Applying underlying method
        val result = (100.9).underlying

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
100.9
```