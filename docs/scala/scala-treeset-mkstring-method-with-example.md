# Scala TreeSet mkString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-treeset-MK string-method-with-example/](https://www.geeksforgeeks.org/scala-treeset-mkstring-method-with-example/)

**mkString()** 方法用于显示字符串中树集的所有元素。

> **方法定义:** def mkString: String
> 
> **返回类型:**它返回一个包含 TreeSet 所有元素的字符串。

**示例#1:**

```scala
// Scala program of mkString() 
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
        val t1 = TreeSet(3, 1, 5, 2, 4)  

        // Print the TreeSet 
        println(t1) 

        // Applying mkString method  
        val result = t1.mkString  

        // Displays output  
        print("TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet: 12345

```

**例 2:**

```scala
// Scala program of mkString() 
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

        // Applying mkString method  
        val result = t1.mkString  

        // Displays output  
        print("TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
TreeSet: aeiou

```