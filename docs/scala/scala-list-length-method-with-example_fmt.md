# Scala List length()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-list-length-method-with-example/](https://www.geeksforgeeks.org/scala-list-length-method-with-example/)

利用`length()`方法求列表的长度。

## 方法定义

> `def length: Int`

## 返回类型

> 返回所述列表的长度。

## 示例 1

```scala
// Scala program of length()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(3, 4, 5, 7, 8)

        // Applying length method
        val result = m1.length

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala

```

## 示例 2

```scala
// Scala program of length()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List()

        // Applying length method
        val result = m1.length

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala

```