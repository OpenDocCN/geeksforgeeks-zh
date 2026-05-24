# Scala Char > (x: Double)方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-7/](https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-7/)

## 方法介绍

使用 `>(x: Double)` 方法来查找所述字符值是否大于 `x`。`x` 的类型必须是 `Double`。

### 方法定义

```
def >(x: Double): Boolean
```

**返回类型:** 如果所述字符值大于 `x`，则返回 `true`，否则返回 `false`。

### 示例 1

```scala
// Scala program of >(x: Double)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying >(x: Double) method
        val result = 'D'.>(111.65785)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
false
```

### 示例 2

```scala
// Scala program of >(x: Double)
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Applying >(x: Double) method
        val result = 'D'.>(11.65785)

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
true
```