# Scala 迭代器计数()方法示例

> 原文:[https://www . geesforgeks . org/Scala-iterator-count-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-count-method-with-example/)

**count()** 方法属于类**抽象迭代器**的具体值成员。它在类*中定义。它计算指定集合中满足给定谓词的元素数量。*

> **方法定义:** def 计数(p: (A) = >布尔值:Int
> 
> 其中， *p* 是所用的谓语。
> 
> **返回类型:**返回满足谓词 *p* 的元素个数。

**示例#1:**

```scala
// Scala program of count()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(5, 6, 8)

        // Applying count method
        val result = iter.count(x => {x % 3 != 0})

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
2

```

这里，只有两个元素满足所述谓词，因此，返回两个。
**例 2:**

```scala
// Scala program of count()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(4, 6, 10, 11, 13)

        // Applying count method
        val result = iter.count(x => {x % 2 == 0})

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
3

```