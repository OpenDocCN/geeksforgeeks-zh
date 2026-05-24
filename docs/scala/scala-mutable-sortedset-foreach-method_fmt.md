# Scala 可变排序集合 foreach()方法

> 原文: [https://www.geeksforgeeks.org/scala-mutable-sortedset-foreach-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-foreach-method/)

在 Scala 可变集合中，`SortedSet` 的 `foreach()` 方法用于将给定函数应用于 `SortedSet` 的所有元素。

## 方法定义

`def foreach(f: (A) => Unit): Unit`

## 返回类型

将给定的函数应用到 `SortedSet` 的所有元素后，返回它们。

## 示例 1

```scala
// Scala program of foreach()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(13, 22, 19, 21)

        // Applying foreach method
        s1.foreach(x => println(x))
    }
}
```

### 输出

```scala

```

## 示例 2

```scala
// Scala program of foreach()
// method
import scala.collection.mutable.SortedSet

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {
        // Creating a SortedSet
        val s1 = SortedSet(5, 7, 8, 3, 2)

        // Applying foreach method
        s1.foreach(x => println(x + " times " + x + " = " + x*x))
    }
}
```

### 输出

```scala
2 times 2 = 4
3 times 3 = 9
5 times 5 = 25
7 times 7 = 49
8 times 8 = 64
```