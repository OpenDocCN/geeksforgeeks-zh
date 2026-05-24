# Scala TreeSet apply()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-apply-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-apply-method-with-example/)

在 Scala `TreeSet class`中， **apply()** 方法用于检查树集中是否存在某个元素。

> **方法定义:**定义应用(elem: A):布尔值
> 
> **返回类型:**如果给定元素存在于树集中，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of apply() 
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
        val t1 = TreeSet(2, 1, 3, 4, 5) 

        // Print the TreeSet
        println(t1) 

        // Applying apply() method  
        val result = t1.apply(3)

        // Displays output 
        println("TreeSet contains '3': " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet contains '3': true

```

**例 2:**

```scala
// Scala program of apply() 
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
        val t1 = TreeSet(2, 1, 3, 4, 5) 

        // Print the TreeSet
        println(t1) 

        // Applying apply() method  
        val result = t1.apply(0)

        // Displays output 
        println("TreeSet contains '0': " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet contains '0': false

```