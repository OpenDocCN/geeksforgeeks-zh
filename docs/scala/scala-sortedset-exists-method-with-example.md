# Scala SortedSet exists()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-exists-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-exists-method-with-example/)

**exists()** 方法用于测试谓词是否适用于 SortedSet 的某些元素。

> **方法定义:** def 存在(p: (A) = >布尔型:布尔型
> 
> **返回类型:**如果所述谓词对 SortedSet 的某些元素成立，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of exists() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a list 
        val s1 = SortedSet(1, 2, 3, 4, 5) 

        // Applying exists method 
        val result = s1.exists(y => {y % 3 == 0}) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of exists() 
// method 
import scala.collection.immutable.SortedSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a list 
        val s1 = SortedSet(1, 2, 3, 4, 5) 

        // Applying exists method 
        val result = s1.exists(y => {y % 7 == 0}) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
false

```