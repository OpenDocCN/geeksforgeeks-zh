# Scala Int compareTo 方法与示例

> 原文：[https://www.geeksforgeeks.org/scala-int-compareto-method-with-examples/](https://www.geeksforgeeks.org/scala-int-compareto-method-with-examples/)

`compareTo` 是 Scala 中的一个 `Int` 类方法，用于将其与操作数进行它类似于比较方法。

> **语法：** `(givenValue1).compareTo(givenValue2)`
> **返回：** 当 `givenValue1` 小于 `givenValue2` 时返回 `-1`。当两个值相等时，返回 `0`。当 `givenValue1` 大于 `givenValue2` 时，返回 `1`。

### 示例 1

```scala
// Scala Program to demonstrate the
// compareTo method of Int class

object GfG
{
    // Main Method
    def main(args: Array[String])
    {
        // Applying the method
        val v1 = (500).compareTo(400)

        // Displaying the output
        println(v1)
    }
}
```

**输出：**

```scala
1
```

### 示例 2

```scala
// Scala Program to demonstrate the
// compareTo method of Int class

object GfG
{
    // Main Method
    def main(args: Array[String])
    {
        // Applying the method
        val v1 = (200).compareTo(700)

        // Displaying the output
        println(v1)
    }
}
```

**输出：**

```scala
-1
```