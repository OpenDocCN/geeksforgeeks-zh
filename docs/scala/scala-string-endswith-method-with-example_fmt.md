# Scala 字符串 `endsWith()` 方法示例

> 原文：[https://www.geeksforgeeks.org/scala-string-endswith-method-with-example/](https://www.geeksforgeeks.org/scala-string-endswith-method-with-example/)

`endsWith()` 方法用于检查所述字符串是否以参数中所述的后缀结束。

> **方法定义：** `Boolean endsWith(String suffix)`
> **返回类型：** 如果字符串以所述后缀结束，则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program of endsWith()
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {
        // Creating a String
        val m1 = "Nidhi"

        // Applying endsWith() method
        val result = m1.endsWith("i")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
true
```

## 示例 #2

```scala
// Scala program of endsWith()
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {
        // Creating a String
        val m1 = "Nidhi"

        // Applying endsWith() method
        val result = m1.endsWith("y")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
false
```