# Scala BitSet -()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-method-with-example-5/](https://www.geeksforgeeks.org/scala-bitset-method-with-example-5/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。-()方法用于创建一个新的集合，并从该集合中移除给定的元素。

> **方法定义:** def -(elem)
> 
> **返回类型:**返回包含该集合所有元素但不包含*元素*的新集合

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

        val bitSet: BitSet = BitSet(0, 1, 2, 3) 
        println(s"Elements in Bitset are = $bitSet") 

        // Applying BitSet -() function 
        val bs1: BitSet = bitSet - 0

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
Elements in Bitset are = BitSet(0, 1, 2, 3)
BitSet(1, 2, 3)

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

        val bitSet: BitSet = BitSet(0, 1, 2, 3 ) 
        println(s"Elements in Bitset are = $bitSet") 

        // Applying BitSet -() function 
        val bs1: BitSet = bitSet - (1, 3)

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
Elements in Bitset are = BitSet(0, 1, 2, 3)
BitSet(0, 2)

```