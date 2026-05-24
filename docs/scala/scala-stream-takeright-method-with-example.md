# Scala Stream takeRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stream-taker ight-method-with-example/](https://www.geeksforgeeks.org/scala-stream-takeright-method-with-example/)

**takeRight()** 方法用于选择流的最后‘n’个元素。

> **方法定义:**def taker right(n:Int):Stream[A]
> 
> **返回类型:**返回流的最后 n 个元素。

**示例#1:**

```scala
// Scala program of takeRight()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Stream
        val m1 = Stream(1, 2, 3, 4, 5, 7)

        // Applying takeRight method
        val result = m1.takeRight(2)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Stream(5, 7)

```

**例 2:**

```scala
// Scala program of takeRight()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Stream
        val m1 = Stream(1, 2, 3, 4, 5, 7)

        // Applying takeRight method
        val result = m1.takeRight(7)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Stream(1, 2, 3, 4, 5, 7)

```