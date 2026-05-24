# Scala `!=(x: Long)` 方法举例

> 原文: [https://www.geeksforgeeks.org/scala-short-x-long-method-with-example-4/](https://www.geeksforgeeks.org/scala-short-x-long-method-with-example-4/)

`!=(x: Long)` 方法用于检查所述 `Short` 值是否不等于 `x`。其中 `x` 是 `Long` 类型的。

## 方法定义

`def !=(x: Long): Boolean`

## 返回类型

如果所述 `Short` 值不等于 `x`，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of !=(x: Long)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying !=(x: Long) method
        val result = (1000).!=(100000L)

// Displays output
        println(result)

    }
}
```

**输出:**

```scala
true
```

## 示例 2

```scala
// Scala program of !=(x: Long)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying !=(x: Long) method
        val result = (999).!=(-100000L)

// Displays output
        println(result)

    }
}
```

**输出:**

```scala
true
```