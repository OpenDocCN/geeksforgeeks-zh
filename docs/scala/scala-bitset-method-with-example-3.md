# Scala BitSet &()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-method-with-example-3/](https://www.geeksforgeeks.org/scala-bitset-method-with-example-3/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。&()方法用于通过执行按位“与”来计算该位集和另一位集之间的交集。

> **方法定义:**定义&()
> 
> **返回类型:**它返回一个由该位集中所有元素组成的新位集。

**示例#1:**

```scala
// Scala program of Bitset &
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val b1: BitSet = BitSet(41, 12, 23, 43, 1, 72) 
        val b2: BitSet = BitSet(1, 100, 5, 12, 23) 

        // Applying BitSet &() function 
        val bs1: BitSet = b1 & (b2)

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
BitSet(1, 12, 23)

```

**例 2:**

```scala
// Scala program of Bitset &
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val b1: BitSet = BitSet(41, 12, 23, 43, 1, 72) 

        // Applying BitSet &() function 
        val bs1: BitSet = b1 & BitSet(1, 100, 5, 12, 23) 

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
BitSet(1, 12, 23)

```