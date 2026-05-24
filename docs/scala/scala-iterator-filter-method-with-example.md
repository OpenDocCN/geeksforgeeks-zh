# Scala 迭代器过滤器()方法示例

> 原文:[https://www . geesforgeks . org/Scala-iterator-filter-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-filter-method-with-example/)

**filter()** 方法属于类*抽象迭代器*的具体值成员。它是在类*迭代器*和 *IterableOnceOps* 中定义的。它选择所述迭代器中满足所用谓词的所有元素。

> **方法定义:** def 过滤器(p: (A) = >布尔型:迭代器[A]
> 
> **返回类型:**它返回一个新的迭代器，该迭代器包含满足给定谓词的所述迭代器的所有元素。

**示例#1:**

```scala
// Scala program of filter()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(7, 8, 5, 4, 13)

        // Applying filter method
        val x = iter.filter(x => {x % 2 == 0})

        // Applying next method
        val result = x.next()

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
8

```

**例 2:**

```scala
// Scala program of filter()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(3, 9, 5, 1, 13)

        // Applying filter method
        val x = iter.filter(x => {x % 3 != 0})

        // Applying next method
        val result = x.next()

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
5

```