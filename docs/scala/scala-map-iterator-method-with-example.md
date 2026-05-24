# 带示例的 Scala 映射迭代器方法

> 原文:[https://www . geeksforgeeks . org/Scala-map-iterator-method-with-example/](https://www.geeksforgeeks.org/scala-map-iterator-method-with-example/)

利用**迭代器**方法给出一个迭代器。

> **方法定义:**定义迭代器:迭代器[(A，B)]
> 
> **返回类型:**对于非空映射返回非空迭代器，对于空映射返回空迭代器。

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

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2) 

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

        // Creating a map
        val m1 = Map() 

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