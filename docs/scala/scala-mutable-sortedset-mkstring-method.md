# Scala 可变排序集 mkString()方法

> 原文:[https://www . geesforgeks . org/Scala-mutatable-sorted set-MK string-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-mkstring-method/)

在 Scala 可变集合中， **mkString()** 方法用于显示字符串中 SortedSet 的所有元素。

> **方法定义:** def mkString: String
> 
> **返回类型:**返回包含 SortedSet 所有元素的字符串。

**示例#1:**

```scala
// Scala program of mkString() 
// method 
import scala.collection.mutable.SortedSet

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(121, 2242, 331, 400) 

        // Applying mkString method 
        val result = s1.mkString

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
1213314002242

```

**例 2:**

```scala
// Scala program of mkString() 
// method 
import scala.collection.mutable.SortedSet

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