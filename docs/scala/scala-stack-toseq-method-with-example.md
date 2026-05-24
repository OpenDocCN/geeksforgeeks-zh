# Scala Stack toSeq()方法示例

> 原文:[https://www . geesforgeks . org/Scala-stack-toseq-method-with-example/](https://www.geeksforgeeks.org/scala-stack-toseq-method-with-example/)

在 Scala `Stack class`中， **toSeq()** 方法被用来返回一个包含堆栈所有元素的序列。

> **方法定义:**def to eq:Seq[A]
> 
> **返回类型:**它返回一个由栈的所有元素组成的序列。

**示例#1:**

```scala
// Scala program of toSeq() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating stack
        val s1 = Stack(1, 2, 3, 4, 5, 6) 

        // Print the stack 
        println(s1) 

        // Applying toSeq method  
        val result = s1.toSeq

        // Display output 
        print("Elements in the Seq: ") 

        for (ele <- result)  
            print(ele + " ")  

    } 
} 
```

**Output:**

```scala
Stack(1, 2, 3, 4, 5, 6)
Elements in the Seq: 1 2 3 4 5 6

```

**例 2:**

```scala
// Scala program of toSeq() 
// method 

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating stack
        val s1 = Stack(5, 2, 13, 7, 1, 3) 

        // Print the stack 
        println(s1) 

        // Applying toSeq method  
        val result = s1.toSeq

        // Display output 
        print("Elements in the Seq: ") 

        for (ele <- result)  
            print(ele + " ")  

    } 
} 
```

**Output:**

```scala
Stack(5, 2, 13, 7, 1, 3)
Elements in the Seq: 5 2 13 7 1 3

```