# Scala 迭代器缓冲()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-iterator-buffered-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-buffered-method-with-example/)

Scala 中的**缓冲()**方法属于 Scala 类迭代器的具体值成员。它从声明的迭代器创建一个缓冲迭代器。

*   **方法定义:**

    ```scala
     def buffered: BufferedIterator[A]

    ```

*   **返回类型:**
    它返回一个缓冲迭代器，产生与所述迭代器相同的值。

**示例:**

```scala
// Scala program of buffered()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(3, 4, 5, 6, 7)

        // Applying buffered method 
        val result = iter.buffered

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
non-empty iterator

```

这里，在应用*缓冲*方法之后，返回所述迭代器的缓冲迭代器。
T3】例:

```scala
// Scala program of buffered()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an empty iterator
        val iter = Iterator()

        // Applying buffered method 
        val result = iter.buffered

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
empty iterator

```

这里，所述迭代器是空的，因此，在应用*缓冲*方法之后，返回空的缓冲迭代器。