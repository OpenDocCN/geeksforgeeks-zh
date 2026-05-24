# Scala BitSet & (GenSet[])方法示例

> 原文:[https://www . geesforgeks . org/Scala-bitset-genset-method-with-example-2/](https://www.geeksforgeeks.org/scala-bitset-genset-method-with-example-2/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。&~(GenSet[])方法用于通过执行按位“与”来计算该位集和另一位集的差。

> **方法定义:** def &(发电机组[]
> 
> **返回类型:**它返回一个新的位集，该位集由该位集中的所有元素组成。

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
        val b2 = Set(1, 100, 55, 32, 23) 

        // Applying BitSet &(GenSet[]) function 
        val bs1 = b1 & (b2)

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
BitSet(1, 23)

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

        // Applying BitSet &(GenSet[]) function 
        val bs1 = b1 & Set(1, 100, 55, 32, 23) 

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
BitSet(1, 23)

```