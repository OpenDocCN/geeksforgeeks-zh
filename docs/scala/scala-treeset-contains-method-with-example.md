# Scala TreeSet 包含()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-contains-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-contains-method-with-example/)

在 Scala `TreeSet class`中，**包含()**方法用于检查元素是否存在于非的树集中。

> **方法定义:** def 包含(elem: A):布尔值
> 
> **返回类型:**如果元素存在于树集中，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of contains() 
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
        val t1 = TreeSet(41, 12, 23, 43, 1, 72) 

        // Print the TreeSet
        println(t1) 

        // Applying contains() method  
        val result = t1.contains(10)

        // Display output 
        print("TreeSet contains '10': " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 12, 23, 41, 43, 72)
TreeSet contains '10': false

```

**例 2:**

```scala
// Scala program of contains() 
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
        val t1 = TreeSet("g", "e", "e", "k", "s") 

        // Print the TreeSet
        println(t1) 

        // Applying contains() method  
        val result = t1.contains("k")

        // Display output 
        print("TreeSet contains 'k': " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(e, g, k, s)
TreeSet contains 'k': true

```