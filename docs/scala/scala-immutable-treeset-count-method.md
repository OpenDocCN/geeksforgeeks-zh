# Scala 不可变 TreeSet count()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-count-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-count-method/)

在 Scala 不可变`TreeSet class`中， **count()** 方法用于计算满足给定谓词的树集中的元素数量。

> **方法定义:** def 计数(p: (A) = >布尔值:Int
> 
> **返回类型:**它返回满足给定谓词的树集中元素数量的计数。

**示例#1:**

```scala
// Scala program of count() 
// method 

// Import TreeSet
import scala.collection.immutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet(2, 1, 3, 4, 5) 

        // Print the TreeSet
        println(t1) 

        // Applying count() method  
        val result = t1.count(x => {x % 2 == 0})

        // Display output 
        print("Number of even element in the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Number of even element in the TreeSet: 2

```

**例 2:**

```scala
// Scala program of count() 
// method 

// Import TreeSet
import scala.collection.immutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSet
        val t1 = TreeSet(2, 1, 3, 4, 5) 

        // Print the TreeSet
        println(t1) 

        // Applying count() method  
        val result = t1.count(x => {x % 2 != 0})

        // Display output 
        print("Number of odd element in the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Number of odd element in the TreeSet: 3

```