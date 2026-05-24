# Scala 迭代器 next()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-next-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-next-method-with-example/)

下一个()方法属于类*抽象迭代器*的抽象值成员。它在类*迭代器*中定义。它给出指定迭代器的下一个元素，并推进迭代器。

> **方法定义:** def next(): A
> 
> **返回类型:**返回指定集合的下一个元素。

**示例#1:**

```scala
// Scala program of next()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(5, 8, 10, 13, 15)

        // Applying next method 
        val result = iter.next

        // Applying next method 
        // again 
        val res = iter.next

        // Displays output
        println(result)
        println(res)

    }
}
```

**Output:**

```scala
5
8

```

**例 2:**

```scala
// Scala program of next()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(1.1, 2.2)

        // Applying next method 
        val result = iter.next

        // Applying next method 
        // again 
        val res = iter.next

        // Displays output
        println(result)
        println(res)

    }
}
```

**Output:**

```scala
1.1
2.2

```