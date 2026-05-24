# Scala 不可变 TreeSet equals()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-equals-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-equals-method/)

在 Scala 不可变`TreeSet class`中，**等于()**方法用于检查两个树集是否由完全相同的元素组成。

> **方法定义:** def 等于(o: Any):布尔值
> 
> **返回类型:**如果两个树集相等，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of equals() 
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
        val t1 = TreeSet(1, 3, 2, 7, 6, 5) 

        val t2 = TreeSet(1, 3, 2, 7, 6, 5) 

        // Print the TreeSets
        println("t1: " + t1)

        println("t2: " + t2)

        // Applying equals() method  
        val result = t1.equals(t2)

        // Displays output 
        println("Both the TreeSets are equal: " + result)

    } 
} 
```

**Output:**

```scala
t1: TreeSet(1, 2, 3, 5, 6, 7)
t2: TreeSet(1, 2, 3, 5, 6, 7)
Both the TreeSets are equal: true

```

**例 2:**

```scala
// Scala program of equals() 
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
        val t1 = TreeSet(1, 3, 2, 7, 6, 5) 

        val t2 = TreeSet(3, 2, 7, 6, 5) 

        // Print the TreeSets
        println("t1: " + t1)

        println("t2: " + t2)

        // Applying equals() method  
        val result = t1.equals(t2)

        // Displays output 
        println("Both the TreeSets are equal: " + result)

    } 
} 
```

**Output:**

```scala
t1: TreeSet(1, 2, 3, 5, 6, 7)
t2: TreeSet(2, 3, 5, 6, 7)
Both the TreeSets are equal: false

```