# Scala 迭代器 indexOf()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-indexof-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-indexof-method-with-example/)

()方法的**索引属于类*抽象迭代器*的具体值成员。它有助于搜索值，然后指出它们在指定迭代器中的位置。**

*   **Method Definition:**

    ```scala
    def indexOf(elem: B): Int

    ```

    其中， *elem* 是要搜索的元素。

*   **返回类型:**
    它返回所述 Scala 迭代器中元素 *elem* 的第一次出现的索引。

**示例:**

```scala
// Scala program of indexOf()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(2, 3, 4, 9, 6)

        // Applying indexOf method
        val result = iter.indexOf(9)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
3

```

这里，方法的*索引中的值 9 出现在迭代器的第三个位置，因此它返回三。
T3】例:*

```scala
// Scala program of indexOf()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(2, 3, 4, 9, 6)

        // Applying indexOf method
        val result = iter.indexOf(7)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-1

```

这里，迭代器中不存在方法的*索引中声明的值，因此它返回-1。
**注意:**如果在所述迭代器中不存在*方法的*索引中给出的值，则该方法将返回-1。*