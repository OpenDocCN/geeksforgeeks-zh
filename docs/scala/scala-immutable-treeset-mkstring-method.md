# Scala 不可变 TreeSet mkString()方法

> 原文:[https://www . geesforgeks . org/Scala-不可变-treeset-mkstring-method/](https://www.geeksforgeeks.org/scala-immutable-treeset-mkstring-method/)

在 Scala 不可变的 TreeSet 类中， **mkString()** 方法用于显示字符串中 TreeSet 的所有元素。

> **方法定义:** def mkString: String
> 
> **返回类型:**它返回一个包含 TreeSet 所有元素的字符串。

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