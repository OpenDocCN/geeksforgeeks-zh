# Scala TreeSet toSeq()方法示例

> 原文:[https://www . geesforgeks . org/Scala-treeset-toseq-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-toseq-method-with-example/)

**toSeq()** 方法用于返回由树集合的所有元素组成的序列。

> **方法定义:**def to eq:Seq[A]
> 
> **返回类型:**它返回一个包含树集所有元素的序列。

**示例#1:**

```scala
// Scala program of toSeq() 
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
        val t1 = TreeSet(1, 2, 3, 4, 5, 6)  

        // Print the TreeSet 
        println(t1) 

        // Applying toSeq method  
        val result = t1.toSeq

        // Display output 
        print("Elements in the Seq: ") 

        for (ele <- result)  
            print(ele + " ") 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5, 6)
Elements in the Seq: 1 2 3 4 5 6

```

**例 2:**

```scala
// Scala program of toSeq() 
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
        val t1 = TreeSet("u", "a", "i", "o", "e")  

        // Print the TreeSet 
        println(t1) 

        // Applying toSeq method  
        val result = t1.toSeq

        // Display output 
        print("Elements in the Seq: ") 

        for (ele <- result)  
            print(ele + " ") 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
Elements in the Seq: a e i o u

```