# Scala Short toInt()方法

> 原文: `https://www.geeksforgeeks.org/scala-short-toint-method/`

## 概述

简而言之，16 位有符号整数(相当于 Java 的 `short` 原语类型)是 `scala.AnyVal` 的一个子类型。`toInt()`方法用于将指定的数字转换为 `Int` 数据类型值。

**方法定义:** `(数字).toInt`

**返回类型:** 返回转换后的整数值。

### 示例 1

```scala
// Scala program of Short toInt()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying toInt method
        val result = (13).toInt

// Displays output
        println(result)

}
}
```

**输出:**

```scala

```

### 示例 2

```scala
// Scala program of Short toInt()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying toInt method
        val result = (123.4).toInt

// Displays output
        println(result)

}
}
```

**输出:**

```scala

```