# Scala 迭代器 toList()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-to list-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-tolist-method-with-example/)

**toList()** 方法属于*抽象*类的具体值成员，在 *TraversableOnce* 和 *GenTraversableOnce* 类中定义。它将可遍历或迭代器转换为列表，但对于无限大小的集合，它不会终止。

*   **方法定义:**

    ```scala
    def toList: List[A]

    ```

*   **返回类型:**
    它从指定的可遍历或迭代器中返回一个列表。> /li >

**示例:**

```scala
// Scala program of toList()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(8, 9, 10, 11)

        // Applying toList method
        val result = iter.toList

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List(8, 9, 10, 11)

```

因此，一个*列表*是由一个迭代器生成的。
T3】例:

```scala
// Scala program of toList()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an empty-iterator
        val iter = Iterator()

        // Applying toList method
        val result = iter.toList

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List()

```

因此，一个空的*列表*是由一个空的迭代器生成的。