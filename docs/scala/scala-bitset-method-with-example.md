# Scala BitSet–()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bit set-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。使用–()方法通过移除另一个集合的所有元素，从该集合创建一个新集合。

> **方法定义:**def–()
> 
> **返回类型:**它返回一个新的集合，该集合包含当前集合中除*元素*之外的所有元素。

**示例#1:**

```scala
// Scala program of Bitset --
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val b1: BitSet = BitSet(0, 1, 2, 3, 4, 5) 
        val b2: BitSet = BitSet(4, 5) 

        // Applying BitSet --() function 
        val bs1: BitSet = b1 -- b2

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
BitSet(0, 1, 2, 3)

```

**例 2:**

```scala
// Scala program of Bitset --
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val b1: BitSet = BitSet(0, 1, 2, 3, 15, 16) 
        val b2: BitSet = BitSet(15, 16, 0 ) 

        // Applying BitSet --() function 
        val bs1: BitSet = b1 -- b2

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
BitSet(1, 2, 3)

```