# Scala 不可变 TreeSet toSeq()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-toseq-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-toseq-method/)

在 Scala 不可变树集类中， **toSeq()** 方法用于返回包含树集所有元素的序列。

> **方法定义:**def to eq:Seq[A]
> 
> **返回类型:**它返回一个包含树集所有元素的序列。

**示例#1:**

```scala
// Scala program of toSeq() 
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