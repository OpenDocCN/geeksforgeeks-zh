# Scala 不可变 TreeSet 的 `contains()` 方法

> 原文：[https://www.geeksforgeeks.org/scala-immutable-treeset-contains-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-contains-method/)

在 Scala 不可变 `TreeSet` 类中，`contains()` 方法用于检查一个元素是否存在于该树集中。

> **方法定义：** `def contains(elem: A): Boolean`
>
> **返回类型：** 如果元素存在于树集中，则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program of contains()
// method

// Import TreeSet
import scala.collection.immutable._

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating TreeSet
        val t1 = TreeSet(41, 12, 23, 43, 1, 72)

// Print the TreeSet
        println(t1)

// Applying contains() method
        val result = t1.contains(10)

// Display output
        print("TreeSet contains '10': " + result)

}
}
```

**输出：**

```scala
TreeSet(1, 12, 23, 41, 43, 72)
TreeSet contains '10': false
```

## 示例 #2

```scala
// Scala program of contains()
// method

// Import TreeSet
import scala.collection.immutable._

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating TreeSet
        val t1 = TreeSet("g", "e", "e", "k", "s")

// Print the TreeSet
        println(t1)

// Applying contains() method
        val result = t1.contains("k")

// Display output
        print("TreeSet contains 'k': " + result)

}
}
```

**输出：**

```scala
TreeSet(e, g, k, s)
TreeSet contains 'k': true
```