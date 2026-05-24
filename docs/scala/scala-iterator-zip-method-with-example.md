# Scala 迭代器 zip()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-zip-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-zip-method-with-example/)

**zip()** 方法属于抽象迭代器类的具体值成员。它是在迭代器类中定义的。

> **方法定义:**值结果= iter.zip(iter1)
> 
> **返回类型:**它返回一个新的 Scala 迭代器，在迭代器中保存对应的元素对，返回的元素数量的大小是两个迭代器大小的最小值。

**示例#1:**

```scala
// Scala program of zip()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating the first Iterator 
        val iter = Iterator(1, 2, 3, 4, 5, 6)

        // Creating the second iterator
        val iter1 = Iterator(7, 8, 9, 10)

        // Applying zip method 
        val result = iter.zip(iter1)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
non-empty iterator

```

**例 2:**

```scala
// Scala program of zip()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating the first Iterator 
        val iter = Iterator()

        // Creating the second iterator
        val iter1 = Iterator(0, 0, 0, 0)

        // Applying zip method 
        val result = iter.zip(iter1)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
empty iterator

```