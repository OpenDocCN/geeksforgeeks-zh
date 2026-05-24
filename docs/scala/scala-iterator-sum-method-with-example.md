# Scala 迭代器 sum()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-sum-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-sum-method-with-example/)

**sum()** 方法属于抽象迭代器类的具体值成员。它在类*旅行可通行一次*和*旅行可通行一次*中定义。它添加了指定集合的元素。

*   **方法定义:**

    ```scala
    def sum: A
    ```

*   **返回类型:**
    返回所述迭代器中所有元素的总和。

**示例:**

```scala
// Scala program of sum()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring a iterator
        val iter = Iterator(2, 4, 5, 6)

        // Applying sum method
        val iter1 = iter.sum

        // Displays output
        println(iter1)

    }
}
```

**Output:**

```scala
17

```

这里，打印所有元素的总和。
**例:**

```scala
// Scala program of sum()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring a iterator
        val iter = Iterator(1.5, 2.3, 3.4)

        // Applying sum method
        val iter1 = iter.sum

        // Displays output
        println(iter1)

    }
}
```

**输出:**

```scala
7.199999999999999
```