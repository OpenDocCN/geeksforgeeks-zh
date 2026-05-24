# Scala Short !=(x: Double)方法示例

> 原文: [https://www.geeksforgeeks.org/scala-short-x-double-method-with-example-4/](https://www.geeksforgeeks.org/scala-short-x-double-method-with-example-4/)

`!=(x: Double)` 方法用于检查所述 `Short` 值是否不等于 `x`。`x` 是 `Double` 类型。

> **方法定义:** `def !=(x: Double): Boolean`
>
> **返回类型:** 如果所述 `Short` 值不等于 `x`，则返回 `true`，否则返回 `false`。

## 例: 1

```scala
// Scala program of !=(x: Double)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying !=(x: Double) method
        val result = (666).!=(79.1234)

        // Displays output
        println(result)

    }
}
```

### Output:

```scala
true
```

## 例: 2

```scala
// Scala program of !=(x: Double)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying !=(x: Double) method
        val result = (999).!=(66.0000)

        // Displays output
        println(result)

    }
}
```

### Output:

```scala
true
```