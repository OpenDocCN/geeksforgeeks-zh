# Scala Short.!=(x: Float) 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-short-x-float-method-with-example-3/](https://www.geeksforgeeks.org/scala-short-x-float-method-with-example-3/)

`!=(x: Float)` 方法用于检查所述 `Short` 值是否不等于 `x`。`x` 是 `Float` 类型的。

> **方法定义:** `def !=(x: Float): Boolean`
>
> **返回类型:** 如果所述 `Short` 值不等于 `x`，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of !=(x: Float)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying !=(x: Float) method
        val result = (995).!=(44.5)

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
// Scala program of !=(x: Float)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying !=(x: Float) method
        val result = (66).!=(66.0)

// Displays output
        println(result)

}
}
```

**输出:**

```scala
false
```