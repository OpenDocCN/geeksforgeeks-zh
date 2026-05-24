# Scala 不变树集& ~()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-method-2/](https://www.geeksforgeeks.org/scala-immutable-treeset-method-2/)

在 Scala 不可变`TreeSet class`中， **& ~()** 方法用于返回包含两个树集之间差异的新树集。

> **方法定义:** def & ~(即:TreeSet[A]): TreeSet[A]
> 
> **返回类型:**返回一个包含两个树集差异的新树集。

**示例#1:**

```scala
// Scala program of &~() 
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
        val t1 = TreeSet(2, 1, 3, 1, 4, 5, 6) 

        val t2 = TreeSet(2, 4, 6)

        // Print the TreeSets
        println(t1) 

        println(t2)

        // Applying &~() method  
        val result = t1.&~(t2)

        // Display output 
        print("TreeSet containing difference of two TreeSets: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5, 6)
TreeSet(2, 4, 6)
TreeSet containing difference of two TreeSets: TreeSet(1, 3, 5)

```

**例 2:**

```scala
// Scala program of &~() 
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
        val t1 = TreeSet("g", "e", "e", "k", "s", "f", "o", "r") 

        val t2 = TreeSet("g", "e", "e", "k", "s")

        // Print the TreeSets
        println(t1) 

        println(t2)

        // Applying &~() method  
        val result = t1.&~(t2)

        // Display output 
        print("TreeSet containing difference of two TreeSets: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(e, f, g, k, o, r, s)
TreeSet(e, g, k, s)
TreeSet containing difference of two TreeSets: TreeSet(f, o, r)

```