# Scala 不可变 TreeSet head()方法

> 原文: [https://www.geeksforgeeks.org/scala-immutable-treeset-head-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-head-method/)

在 Scala 不可变 `TreeSet` 类中，`head()` 方法用于返回 `TreeSet` 的第一个元素。

## 方法定义

```scala
def head: A
```

## 返回类型

返回 `TreeSet` 的第一个元素。

## 示例#1

```scala
// Scala program of head() method

// Import TreeSet
import scala.collection.immutable._

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating TreeSet
        val t1 = TreeSet(1, 3, 2, 7, 6, 5)

        // Print the TreeSet
        println(t1)

        // Applying head() method
        val result = t1.head

        // Displays output
        println("First element of the TreeSet: " + result)
    }
}
```

**Output:**

```scala
TreeSet(1, 2, 3, 5, 6, 7)
First element of the TreeSet: 1
```

## 示例#2

```scala
// Scala program of head() method

// Import TreeSet
import scala.collection.immutable._

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating TreeSet
        val t1 = TreeSet("a", "e", "i", "o", "u")

        // Print the TreeSet
        println(t1)

        // Applying head() method
        val result = t1.head

        // Displays output
        println("First element of the TreeSet: " + result)
    }
}
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
First element of the TreeSet: a
```