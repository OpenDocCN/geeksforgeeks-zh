# Scala Int toShort()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-int-toshort-method-with-example/](https://www.geeksforgeeks.org/scala-int-toshort-method-with-example/)

`toShort()` 方法用于将指定的整数转换为短类型值。

**方法定义:** `(数字).toShort`
**返回类型:** 返回转换后的短数据类型值。

### 示例 1

```scala
// Scala program of Int toShort()
// method

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying toShort method
        val result = (1).toShort

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
1
```

### 示例 2

```scala
// Scala program of Int toShort()
// method

// Creating object
object GfG
{
    // Main method
    def main(args:Array[String])
    {
        // Applying toShort method
        val result = (187449572).toShort

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
-20060
```