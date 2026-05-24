# Scala TreeSet tail()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-tail-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-tail-method-with-example/)

**tail()** 方法用于返回一个新的树集，该树集由除第一个元素之外的所有元素组成。

> **方法定义:** def 尾:TreeSet[A]
> 
> **返回类型:**它返回一个新的树集，该树集由除第一个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of tail() 
// method 

// Import TreeSet
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet(1, 3, 2, 7, 6, 5) 

        // Print the TreeSet
        println(t1)

        // Applying tail() method  
        val result = t1.tail

        // Displays output 
        println("Elements of the TreeSet except the first one: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 5, 6, 7)
Elements of the TreeSet except the first one: TreeSet(2, 3, 5, 6, 7)

```

**例 2:**

```scala
// Scala program of tail() 
// method 

// Import TreeSet
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet("a", "e", "i", "o", "u") 

        // Print the TreeSet
        println(t1)

        // Applying tail() method  
        val result = t1.tail

        // Displays output 
        println("Elements of the TreeSet except the first one: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
Elements of the TreeSet except the first one: TreeSet(e, i, o, u)

```