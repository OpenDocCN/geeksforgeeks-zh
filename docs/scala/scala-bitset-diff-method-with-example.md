# Scala BitSet diff()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-diff-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-diff-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。diff()方法用于计算这个集合和另一个集合的差。

> **方法定义:** def +()
> 
> **返回类型:**返回包含不同元素的集合

**示例#1:**

```scala
// Scala program of diff() 
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating BitSet 
        val s1 = BitSet(1, 2, 3, 4, 5) 

        val s2 = BitSet(1, 2, 3) 

        // Applying diff method 
        val s3 = s1.diff(s2) 

        // Displays output 
        for(elem <- s3) 
        println(elem) 

    } 
} 
```

**Output:**

```scala
4
5

```

**例 2:**

```scala
// Scala program of diff() 
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating BitSet 
        val s1 = BitSet(1, 2, 3, 4, 5) 

        val s2 = BitSet(6, 2, 7, 8) 

        // Applying diff method 
        val s3 = s1.diff(s2) 

        // Displays output 
        for(elem <- s3) 
        println(elem) 

    } 
} 
```

**Output:**

```scala
1
3
4
5

```