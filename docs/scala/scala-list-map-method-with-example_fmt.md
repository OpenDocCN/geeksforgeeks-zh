# Scala List map()方法示例

> 原文：[https://www.geeksforgeeks.org/scala-list-map-method-with-example/](https://www.geeksforgeeks.org/scala-list-map-method-with-example/)

利用`map()`方法将所述函数应用于列表的所有元素。

> **方法定义：** `def map[B](f: (A) => B): List[B]`
>
> **返回类型：** 对列表的所有元素应用所述函数后，返回一个新列表。

## 示例1

```scala
// Scala program of map()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(2, 3, 5, 7, 8)

        // Applying map method
        val result = m1.map(x => x*3)

        // Displays output
        println(result)

    }
}
```

**输出：**

```scala
List(6, 9, 15, 21, 24)
```

## 示例2

```scala
// Scala program of map()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(2, 3, 5, 7, 8)

        // Applying map method
        val result = m1.map(x => x*x)

        // Displays output
        println(result)

    }
}
```

**输出：**

```scala
List(4, 9, 25, 49, 64)
```