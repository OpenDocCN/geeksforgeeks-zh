# Scala SortedSet +()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-method-with-example-2/](https://www.geeksforgeeks.org/scala-sortedset-method-with-example-2/)

除非元素已经存在，否则使用 **+()** 方法创建带有附加元素的新排序集。

> **方法定义:** def +(elem: A): SortedSet[A]
> 
> **返回类型:**它返回一个带有附加元素的新的 SortedSet，除非该元素已经存在。

**示例#1:**

```scala
// Scala program of +() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 3, 4, 6, 7) 

        // Applying +() method 
        val result = s1.+(5)

        // Display output
        print(result)    
    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5, 6, 7)

```

**例 2:**

```scala
// Scala program of +() 
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

        // Applying +() method 
        val result = s1.+(100)

        // Display output
        print(result)    
    } 
} 
```

**Output:**

```scala
TreeSet(1, 12, 23, 41, 43, 72, 100)

```