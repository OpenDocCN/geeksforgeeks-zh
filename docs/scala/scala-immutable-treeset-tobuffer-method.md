# Scala 不可变 TreeSet toBuffer()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-tobuffer-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-tobuffer-method/)

在 Scala 不可变树集类中， **toBuffer()** 方法用于返回包含树集所有元素的缓冲区。

> **方法定义:**def to Buffer【B】>:A:Buffer【B】
> 
> **返回类型:**它返回一个包含 TreeSet 所有元素的缓冲区。

**示例#1:**

```scala
// Scala program of toBuffer() 
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
        val t1 = TreeSet(3, 1, 5, 2, 4)  

        // Print the TreeSet 
        println(t1) 

        // Applying toBuffer method  
        val result = t1.toBuffer

        // Display output 
        print("Elements in the buffer: ") 

        for(elem <- result) 
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
Elements in the buffer: 1 2 3 4 5

```

**例 2:**

```scala
// Scala program of toBuffer() 
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
        val t1 = TreeSet("u", "a", "i", "o", "e")  

        // Print the TreeSet 
        println(t1) 

        // Applying toBuffer method  
        val result = t1.toBuffer

        // Display output 
        print("Elements in the buffer: ") 

        for(elem <- result) 
            print(elem + " ") 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
Elements in the buffer: a e i o u

```