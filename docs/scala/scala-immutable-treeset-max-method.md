# Scala 不可变 TreeSet max()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-max-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-max-method/)

在 Scala 不可变树集合类中， **max()** 方法用于返回树集合中最大的方法。

> **方法定义:** def 最大值:A
> 
> **返回类型:**返回树集中最大的元素。

**示例#1:**

```scala
// Scala program of max() 
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

        // Applying max method  
        val result = q1.max  

        // Displays output  
        print("Largest element in the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Largest element in the TreeSet: 5

```

**例 2:**

```scala
// Scala program of max() 
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
        val q1 = TreeSet("u", "a", "i", "o", "e")  

        // Print the TreeSet 
        println(q1) 

        // Applying max method  
        val result = q1.max  

        // Displays output  
        print("Largest element in the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
Largest element in the TreeSet: u

```