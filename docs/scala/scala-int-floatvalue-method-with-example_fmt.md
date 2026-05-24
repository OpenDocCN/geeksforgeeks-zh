# Scala Int floatValue()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-int-floatvalue-method-with-example/](https://www.geeksforgeeks.org/scala-int-floatvalue-method-with-example/)

`floatValue()`方法用于返回指定整数值的浮点值。

## 方法定义

定义 `floatValue(): Float`

**返回类型:** 返回给定 `Int` 值的浮点值。

## 示例

### 示例#1:

```scala
// Scala program of Int floatValue
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying floatValue method
        val result = (15).floatValue

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
15.0
```

### 示例#2:

```scala
// Scala program of Int floatValue
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying floatValue method
        val result = (1586).floatValue

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
1586.0
```