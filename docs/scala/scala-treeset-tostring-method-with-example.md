# Scala TreeSet toString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-treeset-tostring-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-tostring-method-with-example/)

**toString()** 方法用于返回 TreeSet 对象的字符串表示。

> **方法定义:** def toString(): String
> 
> **返回类型:**返回 TreeSet 对象的字符串表示形式。

**示例#1:**

```scala
// Scala program of toString() 
// method 

// Import TreeSet
import scala.collection.mutable._

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
import scala.collection.mutable._

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