# Scala 不可变 TreeSet foreach()方法

> 原文:[https://www . geeksforgeeks . org/Scala-不可变-treeset-foreach-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-foreach-method/)

在 Scala 不可变的`TreeSet class`中， **foreach()** 方法被用来将给定的函数应用于树集中的所有元素。

> **方法定义:** def foreach[U](f: (A) = > U):单位
> 
> **返回类型:**将给定的函数应用到 TreeSet 的每个元素后，返回所有元素。

**示例#1:**

```scala
// Scala program of foreach() 
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

        // Applying foreach method to print the TreeSet
        print("Elements in the TreeSet: ") 
        t1.foreach(x => print(x + " "))  

    } 
} 
```

**Output:**

```scala
TreeSet(2, 4, 6, 7, 8, 9)
Elements in the TreeSet: 2 4 6 7 8 9

```

**例 2:**

```scala
// Scala program of foreach() 
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

        // Applying foreach method  
        t1.foreach(x => println(x + " times " + x +" = " + x*x))  

    } 
} 
```

**Output:**

```scala
TreeSet(2, 4, 6, 7, 8, 9)
2 times 2 = 4
4 times 4 = 16
6 times 6 = 36
7 times 7 = 49
8 times 8 = 64
9 times 9 = 81

```