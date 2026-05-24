# Scala Char.!=(x: Long) 方法举例

> 原文: [https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-14/](https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-14/)

`!=(x: Long)` 方法用于检查所述字符值是否不等于 `x`。而 `x` 是 `Long` 型的。

> **方法定义:** `def !=(x: Long): Boolean`
>
> **返回类型:** 如果所述字符值不等于 `x` 则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of !=(x: Long)
// method

// Creating object
object GfG
{

// Main method
def main(args:Array[String])
{

// Applying !=(x: Long) method
val result = 'E'.!=(100000L)

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
def main(args:Array[String])
{

// Applying !=(x: Long) method
val result = '\u5544'.!=(-100000L)

// Displays output
println(result)

}
}
```

**输出:**

```scala
true
```