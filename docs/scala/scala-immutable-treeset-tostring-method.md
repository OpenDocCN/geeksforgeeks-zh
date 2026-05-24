# Scala 不可变 TreeSet toString()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-tostring-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-tostring-method/)

在 Scala 不可变树集类中， **toString()** 方法用于返回树集对象的字符串表示。

> **方法定义:** def toString(): String
> 
> **返回类型:**返回 TreeSet 对象的字符串表示形式。

**示例#1:**

```scala
// Scala program of toString() 
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
        val t1 = TreeSet(1, 2, 3, 4, 5, 6)  

        // Print the TreeSet 
        println(t1) 

        // Applying toString method  
        val result = t1.toString

        // Display output 
        print("String representation of the TreeSet object: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5, 6)
String representation of the TreeSet object: TreeSet(1, 2, 3, 4, 5, 6)

```

**例 2:**

```scala
// Scala program of toString() 
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
        val t1 = TreeSet("u", "a", "i", "o", "e") 

        // Print the TreeSet 
        println(t1) 

        // Applying toString method  
        val result = t1.toString

        // Display output 
        print("String representation of the TreeSet object: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
String representation of the TreeSet object: TreeSet(a, e, i, o, u)

```