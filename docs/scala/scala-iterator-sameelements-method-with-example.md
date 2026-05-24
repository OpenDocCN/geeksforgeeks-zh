# Scala 迭代器 sameElements()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-same elements-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-sameelements-method-with-example/)

**sameElements()** 方法属于 Scala 类迭代器的具体值成员。它检查两个声明的迭代器是否以相同的顺序产生相同的元素。对于无限迭代器，此方法不会终止。

*   **Method Definition:**

    ```scala
    def sameElements(that: Iterator[_]): Boolean

    ```

    其中，*表示*是所述的另一个迭代器。

*   **返回类型:**
    如果两个迭代器以相同的顺序产生相同的元素，则返回真，否则返回假。

**示例-1:**

```scala
// Scala program of sameElements()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(3, 4, 5, 6, 7)

        // Declaring an another iterator
        val iter1 = Iterator(3, 4, 5, 6, 7)

        // Applying sameElements method 
        val result = iter.sameElements(iter1)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
true

```

这里，两个声明的迭代器是相同的，所以 *sameElements* 方法返回 true。
T3】例:

```scala
// Scala program of sameElements()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(3, 4, 5, 6, 7)

        // Declaring an another iterator
        val iter1 = Iterator(3, 4, 5, 9, 7)

        // Applying sameElements method 
        val result = iter.sameElements(iter1)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

这里，两个声明的迭代器并不相同，所以 *sameElements* 方法返回 false。