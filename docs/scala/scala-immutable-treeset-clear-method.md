# Scala 不可变 TreeSet clear()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-clear-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-clear-method/)

在 Scala 不可变`TreeSet class`中， **clear()** 方法被用来删除树集中的所有元素。

> **方法定义:** def clear():单位
> 
> **返回类型:**返回一个空的树集。

**示例#1:**

```scala
// Scala program of clear() 
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
        val t1 = TreeSet(2, 1, 3, 4, 5) 

        // Print the TreeSet
        println("Before clear method: " + t1) 

        // Applying clear() method  
        val result = t1.clear

        // Displays output 
        println("After clear method: " + result)

    } 
} 
```

**Output:**

```scala
Before clear method: TreeSet(1, 2, 3, 4, 5)
After clear method: ()

```

**例 2:**

```scala
// Scala program of clear() 
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
        val t1 = TreeSet("a", "e", "i", "o", "u")

        // Print the TreeSet
        println("Before clear method: " + t1) 

        // Applying clear() method  
        val result = t1.clear

        // Displays output 
        println("After clear method: " + result)

    } 
} 
```

**Output:**

```scala
Before clear method: TreeSet(a, e, i, o, u)
After clear method: ()

```