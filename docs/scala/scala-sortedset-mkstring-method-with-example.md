# Scala SortedSet mkString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-MK string-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-mkstring-method-with-example/)

**mkString()** 方法用于显示字符串中 SortedSet 的所有元素。

> **方法定义:** def mkString: String
> 
> **返回类型:**返回包含 SortedSet 所有元素的字符串。

**示例#1:**

```scala
// Scala program of mkString() 
// method 
import scala.collection.immutable.SortedSet

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(1, 2, 3, 4) 

        // Applying mkString method 
        val result = s1.mkString

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
1234

```

**例 2:**

```scala
// Scala program of mkString() 
// method 
import scala.collection.immutable.SortedSet

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet("Geeks", "Will", "Rule") 

        // Applying mkString method 
        val result = s1.mkString

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
GeeksRuleWill

```