# Scala 不可变 TreeSet find()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-find-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-find-method/)

在 Scala 不可变的`TreeSet class`中， **find()** 方法用于返回满足树集中给定谓词的元素。

> **方法定义:** def find(p: (A) = > Boolean:选项【A】
> 
> **返回类型:**返回满足给定谓词的第一个元素(如果存在)，否则返回无。

**示例#1:**

```scala
// Scala program of find() 
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

        // Applying find() method  
        val result = t1.find(x => {x % 7 == 0})

        // Displays output 
        println("Element divisible by 7: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(2, 4, 6, 7, 8, 9)
Element divisible by 7: Some(7)

```

**例 2:**

```scala
// Scala program of find() 
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

        // Applying find() method  
        val result = t1.find(x => {x % 10 == 0})

        // Displays output 
        println("Element divisible by 10: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(2, 4, 6, 7, 8, 9)
Element divisible by 10: None

```