# Scala 迭代器有 hasDefiniteSize()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-hasdefinetesize-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-hasdefinitesize-method-with-example/)

**Hadefinitiseize()**方法是*抽象映射*类的具体值成员。它检查所述可遍历集合是否具有有限的大小。

*   **方法定义:**

    ```scala
    def hasDefiniteSize: Boolean

    ```

*   **返回类型:**
    如果指定的集合大小有限，则返回真，否则返回假，如果迭代器为空，则返回真，否则返回假。

**示例:**

```scala
// Scala program of hasDefiniteSize()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an empty iterator
        val iter = Iterator()

        // Applying hasDefiniteSize method
        val result = iter.hasDefiniteSize

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

这里，迭代器是空的，所以*方法返回真。
T3】例:*

```scala
// Scala program of hasDefiniteSize()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(2, 3, 4, 9, 6)

        // Applying hasDefiniteSize method
        val result = iter.hasDefiniteSize

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

这里，所述迭代器是非空的，因此方法*返回假。*