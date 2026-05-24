# Scala 流头()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stream-head-method-with-example/](https://www.geeksforgeeks.org/scala-stream-head-method-with-example/)

利用 **head()** 方法显示所述流的第一个元素。

> **方法定义:**定义标题:A
> 
> **返回类型:**返回指定流的第一个元素。

**示例#1:**

```scala
// Scala program of head()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Stream
        val m1 = Stream(3, 6, 7, 4)

        // Applying head method
        val result = m1.head

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
3

```

**例 2:**

```scala
// Scala program of head()
// method

// Creating object
object GfG
{  

    // Main method
    def main(args:Array[String])
    {

        // Creating a Stream
        val m1 = Stream(6, 8, 9, 12)

        // Applying head method
        val result = m1.head

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
6

```