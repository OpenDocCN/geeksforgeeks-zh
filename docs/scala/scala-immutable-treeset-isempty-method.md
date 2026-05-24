# Scala 不可变 TreeSet isEmpty()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-isempty-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-isempty-method/)

在 Scala 中，不可变的树集类 **isEmpty()** 用于检查树集是否为空。

> **方法定义:**定义为空:布尔值
> 
> **返回类型:**如果树集为空，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of isEmpty() 
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
        val q1 = TreeSet(1, 2, 3, 4, 5)  

        // Print the TreeSet 
        println(q1) 

        // Applying isEmpty method  
        val result = q1.isEmpty  

        // Displays output  
        print("TreeSet is empty: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet is empty: false

```

**例 2:**

```scala
// Scala program of isEmpty() 
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
        val q1 = TreeSet[Int]()  

        // Print the TreeSet 
        println(q1) 

        // Applying isEmpty method  
        val result = q1.isEmpty  

        // Displays output  
        print("TreeSet is empty: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet()
TreeSet is empty: true

```