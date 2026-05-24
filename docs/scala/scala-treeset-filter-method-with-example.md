# Scala TreeSet filter()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-filter-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-filter-method-with-example/)

在 Scala `TreeSet class`中， **filter()** 方法用于返回一个新的树集，该树集由满足给定谓词的所有元素组成。

> **方法定义:** def 过滤器(pred: (A) = >布尔型:TreeSet[A]
> 
> **返回类型:**它返回一个新的 TreeSet，该 TreeSet 由满足给定谓词的所有元素组成。

**示例#1:**

```scala
// Scala program of filter() 
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

        // Applying filter() method  
        val result = t1.filter(x => {x % 2 == 1})

        // Displays output 
        println("Odd Elements: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 5, 6, 7)
Odd Elements: TreeSet(1, 3, 5, 7)

```

**例 2:**

```scala
// Scala program of filter() 
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

        // Applying filter() method  
        val result = t1.filter(x => {x % 2 == 0})

        // Displays output 
        println("Even Elements: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 5, 6, 7)
Even Elements: TreeSet(2, 6)

```