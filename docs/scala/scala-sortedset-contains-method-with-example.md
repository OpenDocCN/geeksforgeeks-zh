# Scala SortedSet 包含()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-contains-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-contains-method-with-example/)

contains()方法用于检查 SortedSet 中是否存在元素。

> **方法定义:** def 包含(elem: A):布尔值
> 
> **返回类型:**如果该元素出现在 SortedSet 中，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of contains() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(41, 12, 23, 43, 1, 72) 

        // Applying contains() method 
        val result = s1.contains(1)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of contains() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(41, 12, 23, 43, 1, 72) 

        // Applying contains() method 
        val result = s1.contains(10)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
false

```