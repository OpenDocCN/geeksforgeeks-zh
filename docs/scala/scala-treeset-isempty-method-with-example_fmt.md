# Scala TreeSet isEmpty()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-treeset-isempty-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-isempty-method-with-example/)

`isEmpty()` 用于检查树集是否为空。

> **方法定义:** `def isEmpty: Boolean`
>
> **返回类型:** 如果树集为空，则返回 `true`，否则返回 `false`。

## 示例#1

```scala
// Scala program of isEmpty()
// method

// Import TreeSet
import scala.collection.mutable._

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Creating TreeSet
        val q1 = TreeSet(1, 2, 3, 4, 5)

        // Print the TreeSet
        println(q1)

        // Applying isEmpty method
        val result = q1.isEmpty

        // Displays output
        print("TreeSet is empty: " + result)

    }
}
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet is empty: false
```

## 示例 2

```scala
// Scala program of isEmpty()
// method

// Import TreeSet
import scala.collection.mutable._

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Creating TreeSet
        val q1 = TreeSet[Int]()

        // Print the TreeSet
        println(q1)

        // Applying isEmpty method
        val result = q1.isEmpty

        // Displays output
        print("TreeSet is empty: " + result)

    }
}
```

**Output:**

```scala
TreeSet()
TreeSet is empty: true
```