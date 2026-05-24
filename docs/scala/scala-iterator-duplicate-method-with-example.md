# Scala 迭代器复制()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-replicate-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-duplicate-method-with-example/)

**replicate()**方法属于类迭代器的具体值成员。它生成一个迭代器的副本，该迭代器将迭代相同顺序的值。如果将重复迭代器放在相同的元素上，则称它们相等。

*   **方法定义:**

    ```scala
     def duplicate: (Iterator[A], Iterator[A])

    ```

*   **返回类型:**
    它返回一对迭代器。

**示例:**

```scala
// Scala program of duplicate()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(3, 4, 5, 7, 8)

        // Applying duplicate method
        val iter1 = iter.duplicate

        // Displays output
        println(iter1)

    }
} 
```

**Output:**

```scala
(non-empty iterator, non-empty iterator)

```

这里，所述迭代器是非空的，因此创建了两个非空迭代器。
**例:**

```scala
// Scala program of duplicate()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an empty-iterator
        val iter = Iterator()

        // Applying duplicate method
        val iter1 = iter.duplicate

        // Displays output
        println(iter1)

    }
} 
```

**Output:**

```scala
(empty iterator, empty iterator)

```

这里，声明的迭代器是空的，所以创建了两个空迭代器。