# Scala Float `%(x: Long)` 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-float-x-long-method-with-example-8/](https://www.geeksforgeeks.org/scala-float-x-long-method-with-example-8/)

当给定的浮点值除以长值时，使用 `%(x: Long)` 方法返回余数。

> **方法定义:** `Float_Value.%(Long_Value)`
> **返回类型:** 当给定的浮点值除以长值时，返回余数。

## 示例 1

```scala
// Scala program of Float %(x: Long)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying %(x: Long) function
        val result = (65.0).%(65.0)

// Displays output
        println(result)

}
}
```

**输出:**

```scala
0.0
```

## 示例 2

```scala
// Scala program of Float %(x: Long)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying %(x: Long) function
        val result = (100.0).%(65.0)

// Displays output
        println(result)

}
}
```

**输出:**

```scala
35.0
```