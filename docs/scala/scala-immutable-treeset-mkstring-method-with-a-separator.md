# 带分隔符的 Scala 不可变 TreeSet mkString()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-MK string-method-with-a-separator/](https://www.geeksforgeeks.org/scala-immutable-treeset-mkstring-method-with-a-separator/)

在 Scala 不可变树集类中， **mkString()** 方法用于显示字符串中树集的所有元素以及分隔符。

> **方法定义:**def mkString(sep:String):String
> 
> **返回类型:**它返回字符串中树集的所有元素以及分隔符。

**示例#1:**

```scala
// Scala program of mkString() 
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

        // Applying mkString method  
        val result = t1.mkString(", ")

        // Displays output  
        print("TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(1, 2, 3, 4, 5)
TreeSet: 1, 2, 3, 4, 5

```

**例 2:**

```scala
// Scala program of mkString() 
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

        // Applying mkString method  
        val result = t1.mkString(", ")

        // Displays output  
        print("TreeSet: " + result) 

    } 
} 
```

**Output:**

```scala
TreeSet(a, e, i, o, u)
TreeSet: a, e, i, o, u

```