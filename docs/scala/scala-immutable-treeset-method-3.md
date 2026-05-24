# Scala 不可变 TreeSet +()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-method-3/](https://www.geeksforgeeks.org/scala-immutable-treeset-method-3/)

在 Scala 不可变`TreeSet class`中， **+()** 方法用于向树集合添加元素，除非它已经存在。

> **方法定义:** def +(elem: A): TreeSet[A]
> 
> **返回类型:**它返回一个带有附加元素的新树集，除非该元素已经存在。

**示例#1:**

```scala
// Scala program of +() 
// method 

// Import TreeSet
import scala.collection.immutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSets
        val t1 = TreeSet("a", "e", "i", "o") 

        // Print the TreeSets
        println(t1) 

        // Applying +() method  
        val result = t1 + ("u")

        // Display output 
        print("After adding an element: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o)
After adding an element: TreeSet(a, e, i, o, u)

```

**例 2:**

```scala
// Scala program of +() 
// method 

// Import TreeSet
import scala.collection.immutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating TreeSets
        val t1 = TreeSet(2, 1, 5, 4, 1) 

        // Print the TreeSets
        println(t1) 

        // Applying +() method  
        val result = t1 + (3)

        // Display output 
        print("After adding an element: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 4, 5)
After adding an element: TreeSet(1, 2, 3, 4, 5)

```