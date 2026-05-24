# Scala TreeSet diff()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-diff-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-diff-method-with-example/)

**diff()** 方法用于查找两个树集之间的差异。它从另一个树集中删除一个树集中存在的元素。

> **方法定义:**def diff【B】T2:A】(即:集合。序列[B]):树集[A]
> 
> **返回类型:**它返回一个新的树集，该树集由两个给定树集之间的差异之后的元素组成。

**示例#1:**

```scala
// Scala program of diff() 
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
        val t1 = TreeSet(1, 2, 3, 4, 5)  

        val t2 = TreeSet(3, 4, 5)  

        // Print the TreeSet 
        println("TreeSet_1: " + t1) 

        println("TreeSet_2: " + t2) 

        // Applying diff method  
        val result = t1.diff(t2)  

        // Displays output  
        print("(TreeSet_1 - TreeSet_2): " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet_1: TreeSet(1, 2, 3, 4, 5)
TreeSet_2: TreeSet(3, 4, 5)
(TreeSet_1 - TreeSet_2): TreeSet(1, 2)

```

**例 2:**

```scala
// Scala program of diff() 
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
        val t1 = TreeSet(1, 2, 3, 4, 5)  

        val t2 = TreeSet(3, 4, 5, 6, 7, 8)  

        // Print the TreeSet 
        println("TreeSet_1: " + t1) 

        println("TreeSet_2: " + t2) 

        // Applying diff method  
        val result = t2.diff(t1)  

        // Displays output  
        print("(TreeSet_2 - TreeSet_1): " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet_1: TreeSet(1, 2, 3, 4, 5)
TreeSet_2: TreeSet(3, 4, 5, 6, 7, 8)
(TreeSet_2 - TreeSet_1): TreeSet(6, 7, 8)

```