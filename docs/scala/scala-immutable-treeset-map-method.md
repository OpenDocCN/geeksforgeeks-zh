# Scala 不可变 TreeSet map()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-map-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-map-method/)

在 Scala 中，不可变树集类 **map()** 方法用于通过对给定树集的所有元素应用一个函数来构建一个新的树集。

> **方法定义:** def 图【B】(f:(A)=>B):树集【B】
> 
> **返回类型:**应用给定函数后，返回包含所有元素的新树集。

**示例#1:**

```scala
// Scala program of map() 
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

        // Applying map method  
        val result = q1.map(x => x*x)  

        // Displays output  
        print("TreeSet with squared elements: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet with squared elements: TreeSet(1, 4, 9, 16, 25)

```

**例 2:**

```scala
// Scala program of map() 
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

        // Applying map method  
        val result = q1.map(x => x*x*x)  

        // Displays output  
        print("TreeSet with cubed elements: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet with cubed elements: TreeSet(1, 8, 27, 64, 125)

```