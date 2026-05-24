# Scala 不可变 TreeSet drop()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-drop-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-drop-method/)

在 Scala 不可变的`TreeSet class`中， **drop()** 方法被用来删除树集中的前 n 个元素。

> **方法定义:** def drop(n: Int): TreeSet[A]
> 
> **返回类型:**它返回一个新的树集，除了前 n 个元素之外，所有元素都包含在其中。

**示例#1:**

```scala
// Scala program of drop() 
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
        val t1 = TreeSet(2, 4, 6, 7, 8, 9) 

        // Print the TreeSet
        println(t1) 

        // Applying drop() method  
        val result = t1.drop(2)

        // Displays output 
        println("TreeSet after using drop(2) method: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(2, 4, 6, 7, 8, 9)
TreeSet after using drop(2) method: TreeSet(6, 7, 8, 9)

```

**例 2:**

```scala
// Scala program of drop() 
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
        val t1 = TreeSet(2, 4, 6, 7, 8, 9) 

        // Print the TreeSet
        println(t1) 

        // Applying drop() method  
        val result = t1.drop(3)

        // Displays output 
        println("TreeSet after using drop(3) method: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(2, 4, 6, 7, 8, 9)
TreeSet after using drop(3) method: TreeSet(7, 8, 9)

```