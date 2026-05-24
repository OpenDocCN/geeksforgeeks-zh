# Scala 不可变 TreeSet isEmpty()方法

> 原文: [https://www.geeksforgeeks.org/scala-immutable-treeset-isempty-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-isempty-method/)

在 Scala 中，不可变的 `TreeSet` 类的 `isEmpty()` 方法用于检查树集是否为空。

> **方法定义:** `def isEmpty: Boolean`
>
> **返回类型:** 如果树集为空，则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program of isEmpty()
// method

// Import TreeSet
import scala.collection.immutable._

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
import scala.collection.immutable._

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