# Scala 迭代器切片()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-iterator-slice-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-slice-method-with-example/)

**slice()** 方法属于抽象迭代器类的具体值成员。它是在迭代器类中定义的。它为*切片*中给定的时间间隔创建一个新的迭代器。出现在*切片*中的第一个值表示新迭代器中元素的开始，出现在*切片*中的第二个值表示结束。

*   **Method Definition:**

    ```scala
    def slice(from: Int, until: Int): Iterator[A]
    ```

    其中，*从*表示第一个元素的索引，*直到*表示切片后第一个元素的索引。

*   **返回类型:**
    它返回一个新的迭代器，元素从**从**直到**直到**。

**示例:**

```scala
// Scala program of slice()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring a iterator
        val iter = Iterator(1, 2, 3, 4, 5)

        // Applying slice method
        val iter1 = iter.slice(1, 4)

        // Using while loop to print the 
        // elements of new iterator
        while(iter1.hasNext)
        {

            // Displays output
            println(iter1.next())

        }
    }
}
```

**Output:**

```scala
2
3
4

```

这里，如果切片中存在的间隔像(n，m)，那么元素将从第*个*索引打印到第 *(m-1)个*索引。函数*下一步*和*下一步*用于打印新迭代器的元素。
**示例:**

```scala
// Scala program of slice()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring a iterator
        val iter = Iterator(2, 4, 5, 6)

        // Applying slice method
        val iter1 = iter.slice(0, 3)

        // Using while loop to print the 
        // elements of new iterator
        while(iter1.hasNext)
        {

            // Displays output
            println(iter1.next())

        }
    }
}
```

**Output:**

```scala
2
4
5

```

这里，元素从索引 0 一直打印到第二个索引。