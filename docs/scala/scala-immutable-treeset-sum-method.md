# Scala 不可变 TreeSet sum()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-sum-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-sum-method/)

在 Scala 不可变树集合类中， **sum()** 方法用于返回树集合所有元素的总和。

> **方法定义:**定义和:A
> 
> **返回类型:**返回树集合所有元素的总和。

**示例#1:**

```scala
// Scala program of sum() 
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

        // Applying sum method  
        val result = t1.sum

        // Displays output  
        print("Sum of all the elements of the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Sum of all the elements of the TreeSet: 15

```

**例 2:**

```scala
// Scala program of sum() 
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
        val t1 = TreeSet(3, 1, 5, 7, 9)  

        // Print the TreeSet 
        println(t1) 

        // Applying sum method  
        val result = t1.sum

        // Displays output  
        print("Sum of all the elements of the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 3, 5, 7, 9)
Sum of all the elements of the TreeSet: 25

```