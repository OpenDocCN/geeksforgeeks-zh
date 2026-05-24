# Scala 可变排序集+()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-method-2/](https://www.geeksforgeeks.org/scala-mutable-sortedset-method-2/)

在 Scala 可变集合中， **+()** 方法用于创建一个新的带有附加元素的 SortedSet，除非该元素已经存在。

> **方法定义:** def +(elem: A): SortedSet[A]
> 
> **返回类型:**它返回一个带有附加元素的新的 SortedSet，除非该元素已经存在。

**示例#1:**

```scala
// Scala program of +() 
// method 
import scala.collection.mutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(4, 8, 9, 1, 7) 

        // Applying +() method 
        val result = s1.+(5)

        // Display output
        print(result) 
    } 
} 
```

**Output:**

```scala
TreeSet(1, 4, 5, 7, 8, 9)

```

**例 2:**

```scala
// Scala program of +() 
// method 
import scala.collection.mutable.SortedSet 

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