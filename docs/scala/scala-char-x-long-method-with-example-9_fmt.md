# Scala Char类的<(x: Long)方法

> 原文: [https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-9/](https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-9/)

利用`<(x: Long)`方法查找所述字符值是否小于`x`。而`x`的类型必须是`Long`。

## 方法定义

> `def < (x: Long): Boolean`
>
> **返回类型:** 如果指定的字符值小于`x`，则返回`true`，否则返回`false`。

## 示例 1

```scala
// Scala program of <(x: Long)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying <(x: Long) method
        val result = 'D'.<(100000L)

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
// Scala program of <(x: Long)
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Applying <(x: Long) method
        val result = 'D'.<(-100000L)

// Displays output
        println(result)

    }
}
```

**输出:**

```scala
false
```