# Scala BitSet -(elems: Int*)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-bitset-elems-int-method-with-example-2/](https://www.geeksforgeeks.org/scala-bitset-elems-int-method-with-example-2/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。使用的-(elems: Int*)方法需要移除两个或更多元素。

> **方法定义:** def +()
> 
> **返回类型:**包含所有元素的新集合，除了每个给定元素少出现一次。

**示例#1:**

```scala
// Scala program of Bitset -
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val b2: Set[Int] = BitSet(5, 6, 7, 55, 56, 57) - 55 - 56 

        // Displays output 
        println(b2) 

    } 
} 
```

**Output:**

```scala
BitSet(5, 6, 7, 57)

```

**例 2:**

```scala
// Scala program of Bitset -
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val b2: Set[Int] = BitSet(5, 6, 7) - 5 - 6 - 0

        // Displays output 
        println(b2) 

    } 
} 
```

**Output:**

```scala
BitSet(7)

```