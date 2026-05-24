# Scala 迭代器大小()方法示例

> 原文:[https://www . geesforgeks . org/Scala-iterator-size-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-size-method-with-example/)

**size()** 方法属于类*抽象迭代器*的具体值成员。它在类 *IterableOnceOps* 中定义。它被用来查找所述集合的大小。对于无限大小的集合，它不会终止。

> **方法定义:** def 大小:Int
> 
> **返回类型:**返回指定集合的大小..

**示例#1:**

```scala
// Scala program of size()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(2.2, 3.6, 6.6, 9.9, 2.1)

        // Applying size method
        val iter1 = iter.size

        // Displays output
        println(iter1)

    }
}
```

**输出:**

```scala
5

```