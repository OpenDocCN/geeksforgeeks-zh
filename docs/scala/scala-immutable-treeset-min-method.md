# Scala 不可变 TreeSet min()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-min-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-min-method/)

在 Scala 不可变树集合类中， **min()** 方法用于返回树集合的最小元素。

> **方法定义:**定义最小值:A
> 
> **返回类型:**返回树集中最小的元素。

**示例#1:**

```scala
// Scala program of min() 
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

        // Applying min method  
        val result = q1.min  

        // Displays output  
        print("Smallest element in the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Smallest element in the TreeSet: 1

```

**例 2:**

```scala
// Scala program of min() 
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

        // Applying min method  
        val result = q1.min  

        // Displays output  
        print("Smallest element in the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
Smallest element in the TreeSet: a

```