# Scala 不可变 TreeSet last()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-last-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-last-method/)

在 Scala 中，不可变的 TreeSet 类 **last()** 方法用于返回 TreeSet 的最后一个元素。

> **方法定义:**定义最后:答
> 
> **返回类型:**返回树集合的最后一个元素。

**示例#1:**

```scala
// Scala program of last() 
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

        // Applying last method  
        val result = q1.last  

        // Displays output  
        print("Last element of the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Last element of the TreeSet: 5

```

**例 2:**

```scala
// Scala program of last() 
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

        // Applying last method  
        val result = q1.last  

        // Displays output  
        print("Last element of the TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
Last element of the TreeSet: u

```