# Scala TreeSet exists()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-exists-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-exists-method-with-example/)

在 Scala `TreeSet class`中， **exists()** 方法用于检查谓词是否适用于树集的任何元素。

> **方法定义:** def 存在(p: (A) = >布尔型:布尔型
> 
> **返回类型:**如果谓词对树集合的任何元素都成立，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of exists() 
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
        val t1 = TreeSet(1, 3, 2, 7, 6, 5) 

        // Print the TreeSet
        println(t1) 

        // Applying exists() method  
        val result = t1.exists(x => {x % 7 == 0})

        // Displays output 
        println("Element divisible by 7 exists: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 5, 6, 7)
Element divisible by 7 exists: true

```

**例 2:**

```scala
// Scala program of exists() 
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
        val t1 = TreeSet(1, 3, 2, 7, 6, 5) 

        // Print the TreeSet
        println(t1) 

        // Applying exists() method  
        val result = t1.exists(x => {x == 10})

        // Displays output 
        println("Element 10 exists: " + result)

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 5, 6, 7)
Element 10 exists: false

```