# Scala 不可变 TreeSet size()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-size-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-size-method/)

在 Scala 不可变的 TreeSet 类中， **size()** 方法用于返回 TrreSet 中存在的元素数量。

> **方法定义:**定义大小:整数
> 
> **返回类型:**返回树集中存在的元素数量。

**示例#1:**

```scala
// Scala program of size() 
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
        val t1 = TreeSet(3, 1, 5, 2, 4)  

        // Print the TreeSet 
        println(t1) 

        // Applying size method  
        val result = t1.size

        // Displays output  
        print("Size of the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Size of the TreeSet: 5

```

**例 2:**

```scala
// Scala program of size() 
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
        val t1 = TreeSet(3, 1, 5, 2, 4, 10, 6, 9, 7, 8)  

        // Print the TreeSet 
        println(t1) 

        // Applying size method  
        val result = t1.size

        // Displays output  
        print("Size of the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
Size of the TreeSet: 10

```