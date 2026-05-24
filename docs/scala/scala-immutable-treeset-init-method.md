# Scala 不可变 TreeSet init()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-init-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-init-method/)

在 Scala 不可变的`TreeSet class`中， **init()** 方法用于返回一个新的树集，该树集由除最后一个元素之外的所有元素组成。

> **方法定义:** def init: TreeSet[A]
> 
> **返回类型:**它返回一个新的树集，该树集由除最后一个元素之外的所有元素组成。

**示例#1:**

```scala
// Scala program of init() 
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
        val t1 = TreeSet(1, 3, 2, 7, 6, 5) 

        // Print the TreeSet
        println(t1)

        // Applying init() method  
        val result = t1.init

        // Displays output 
        println("Elements of the TreeSet except the last one: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 5, 6, 7)
Elements of the TreeSet except the last one: TreeSet(1, 2, 3, 5, 6)

```

**例 2:**

```scala
// Scala program of init() 
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
        val t1 = TreeSet(1, 3, 12, 7, 16, 5) 

        // Print the TreeSet
        println(t1)

        // Applying init() method  
        val result = t1.init

        // Displays output 
        println("Elements of the TreeSet except the last one: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 3, 5, 7, 12, 16)
Elements of the TreeSet except the last one: TreeSet(1, 3, 5, 7, 12)

```