# Scala 迭代器 indexWhere()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-index where-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-indexwhere-method-with-example/)

**indexWhere()** 方法属于 Scala 中迭代器类的具体值成员。这个方法将找到迭代器的第一个值的位置，该值满足所述谓词。

*   **Method Definition:**

    ```scala
    def indexWhere(p: (A) => Boolean): Int

    ```

    其中，p 是陈述的谓词。

*   **返回类型:**
    它返回迭代器中满足所述谓词的第一个值的索引，如果迭代器中没有一个值满足所述谓词，那么这个方法返回-1。

**示例:**

```scala
// Scala program of indexWhere()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(3, 1, 4, 9, 6)

        // Applying indexWhere method
        // with a predicate
        val result = iter.indexWhere(x=>{x % 2==0})

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
2

```

这里，给定的谓词由第三个位置(即索引 2)的迭代器的值满足，因此返回 2。
**例:**

```scala
// Scala program of indexWhere()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(3, 1, 7, 9, 15)

        // Applying indexWhere method
        // with a predicate
        val result = iter.indexWhere(x=>{x % 2==0})

        // Displays output
        println(result)

    }
}     
```

**Output:**

```scala
-1

```

这里，迭代器的任何值都不满足所述谓词，因此在这种情况下返回-1。