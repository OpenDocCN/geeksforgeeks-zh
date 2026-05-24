# Scala 迭代器 seq()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-seq-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-seq-method-with-example/)

**seq()** 方法属于 Iterable 类的具体值成员。这有助于可视化所述集合的顺序视图。它的时间复杂度为 O(1)。

*   **方法定义:**

    ```scala
    def seq: Iterator[A]

    ```

*   **返回类型:**
    它返回迭代器的顺序视图。

**示例:**

```scala
// Scala program of seq()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(3, 4, 5, 6, 7)

        // Applying seq method in 
        // for loop
        for(n<-iter.seq)
        {

            // Displays output
            println(n)

        }
    }
}
```

**Output:**

```scala
3
4
5
6
7

```

这里，所述迭代器的顺序视图由 Scala 的 *seq* 方法返回。
T3】例:

```scala
// Scala program of seq()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(8, 9, 10, 11)

        // Applying seq method
        val result = iter.seq

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
non-empty iterator

```

这里，返回一个非空迭代器。