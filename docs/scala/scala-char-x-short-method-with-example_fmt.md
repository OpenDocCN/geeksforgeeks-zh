# Scala Char |(x: Short)方法示例

> 原文：[https://www.geeksforgeeks.org/scala-char-x-short-method-with-example/](https://www.geeksforgeeks.org/scala-char-x-short-method-with-example/)

## 方法介绍

`|(x: Short)` 方法用于在参数列表中查找所述字符值和给定 `x` 的逐位“或”，参数列表必须是 `Short` 类型。

**方法定义：**
```scala
def |(x: Short): Short
```

**返回类型：** 返回指定字符值和给定短类型 `x` 的逐位或。

## 示例 1

```scala
// Scala program of |(x: Short)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying |(x: Short) method
        val result = 'B'.|(10000)

        // Displays output
        println(result)

    }
}
```

**Output：**

```scala

```

## 示例 2

```scala
// Scala program of |(x: Short)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying |(x: Short) method
        val result = 'B'.|(-20000)

        // Displays output
        println(result)

    }
}
```

**Output：**

```scala

```