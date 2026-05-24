# Scala 迭代器 isTraversableAgain()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-is traversableleagain-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-istraversableagain-method-with-example/)

**isTraversableAgain()** 方法属于 Scala 中类迭代器的具体值成员。它检查迭代器是否可以重复遍历。

*   **方法定义:**

    ```scala
    def isTraversableAgain: Boolean

    ```

*   **返回类型:**
    如果所述迭代器可以重复遍历，则返回真，如果不能重复遍历，则返回假。

**示例:**

```scala
// Scala program of isTraversableAgain()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(3, 1, 7, 9, 15)

        // Applying isTraversableAgain 
        // method 
        val result = iter.isTraversableAgain

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

这里，迭代器不能重复遍历，所以它返回 false。
**例:**

```scala
// Scala program of isTraversableAgain()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an empty iterator
        val iter = Iterator()

        // Applying isTraversableAgain 
        // method 
        val result = iter.isTraversableAgain

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

这里，我们已经声明了一个空迭代器，甚至不能重复遍历，因此，该方法返回 false。