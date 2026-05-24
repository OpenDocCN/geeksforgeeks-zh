# Scala 列表迭代器()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-iterator-method-with-example/](https://www.geeksforgeeks.org/scala-list-iterator-method-with-example/)

利用**迭代器**方法给出一个迭代器。

> **方法定义:**定义迭代器:迭代器[A]
> 
> **返回类型:**对于非空列表返回非空迭代器，对于空列表返回空迭代器。

**示例#1:**

```scala
// Scala program of iterator
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3, 4, 5)

        // Applying iterator method
        val result = m1.iterator

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
// Scala program of iterator
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an empty list
        val m1 = List() 

        // Applying iterator method
        val result = m1.iterator

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
empty iterator

```