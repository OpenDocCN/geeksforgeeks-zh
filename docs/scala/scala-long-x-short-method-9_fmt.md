# Scala Long `&(x: Short)` 方法

> 原文: [https://www.geeksforgeeks.org/scala-long-x-short-method-9/](https://www.geeksforgeeks.org/scala-long-x-short-method-9/)

在 Scala 中，`Long` 是 64 位有符号整数，相当于 Java 的 `Long` 基元类型。`&(x: Short)` 方法用于返回指定 `Long` 值和 `Short` 值的按位与。

> **方法定义–** `&(x: Short)`
>
> **返回–** 返回该值与 `x` 的按位“与”

## 示例 #1

```scala
// Scala program to explain working of
// &(x: Short) method

// Creating object
object GfG
{

// Main method
def main(args:Array[String])
{

// Applying &(x: Short) method 
val result = (13.toLong).&(28:Short)

// Displays output
println(result)

}
}
```

**输出:**

```scala

```

## 示例 #2

```scala
// Scala program to explain working of
// &(x: Short) method

// Creating object
object GfG
{

// Main method
def main(args:Array[String])
{

// Applying &(x: Short) method 
val result = (7.toLong).&(11:Short)

// Displays output
println(result)

}
}
```

**输出:**

```scala

```