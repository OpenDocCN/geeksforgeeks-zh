# 带分隔符的 Scala SortedSet mkString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-sorted set-MK string-method-with-separator-with-example/](https://www.geeksforgeeks.org/scala-sortedset-mkstring-method-with-a-separator-with-example/)

**mkString()** 方法用于显示字符串中排序集的所有元素以及分隔符。

> **方法定义:**def mkString(sep:String):String
> 
> **返回类型:**它返回字符串中 SortedSet 的所有元素以及分隔符。

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
        val result = s1.mkString(", ")

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
1, 2, 3, 4

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
        val result = s1.mkString(" ")

        // Display output
        println(result)
    } 
}
```

**Output:**

```scala
Geeks Rule Will

```