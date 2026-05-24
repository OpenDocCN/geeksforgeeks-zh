# Scala 不可变 TreeSet dropWhile()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-dropwhile-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-dropwhile-method/)

在 Scala 不可变`TreeSet class`中， **dropWhile()** 方法用于从前面删除满足树集中给定谓词的最长前缀。

> **方法定义:**def drop while(p:(A)=>Boolean:TreeSet[A]
> 
> **返回类型:**在删除满足给定谓词的最长前缀后，它返回一个由元素组成的新树集。

**示例#1:**

```scala
// Scala program of dropWhile() 
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
        val t1 = TreeSet(2, 4, 6, 7, 8, 9) 

        // Print the TreeSet
        println(t1) 

        // Applying dropWhile() method  
        val result = t1.dropWhile(x => {x % 2 == 0})

        // Displays output 
        println("TreeSet after using dropWhile() method: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(2, 4, 6, 7, 8, 9)
TreeSet after using dropWhile() method: TreeSet(7, 8, 9)

```

**例 2:**

```scala
// Scala program of dropWhile() 
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
        val t1 = TreeSet(3, 5, 6, 7, 8, 9) 

        // Print the TreeSet
        println(t1) 

        // Applying dropWhile() method  
        val result = t1.dropWhile(x => {x % 2 != 0})

        // Displays output 
        println("TreeSet after using dropWhile() method: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(3, 5, 6, 7, 8, 9)
TreeSet after using dropWhile() method: TreeSet(6, 7, 8, 9)

```