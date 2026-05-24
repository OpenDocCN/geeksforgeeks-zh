# Scala BitSet++:[B]T2:Int](即:GenTraversableOnce[B])方法，带示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-bintt hat-gentraversableonceb-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-bintthat-gentraversableonceb-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。++:[B>:Int](即:GenTraversableOnce[B])方法用于创建一个集合，该集合包含左侧操作数的元素以及右侧操作数的元素。

**方法定义:**def++:[B]T2:【Int】(即:GenTraversableOnce[B])

**返回类型:**它返回一个新的类型集合*即*，其中包含该集合的所有元素。

**示例#1:**

```scala
// Scala program of Bitset ++
// method 
import scala.collection.immutable.BitSet 
import scala.collection.mutable.LinkedList 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val b1: BitSet = BitSet(0, 1, 2, 3) 
        val b2 = LinkedList(100)

        // Applying BitSet ++() function 
        val bs1 = b1 ++: b2

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
LinkedList(0, 1, 2, 3, 100)

```

**例 2:**

```scala
// Scala program of Bitset ++
// method 
import scala.collection.immutable.BitSet 
import scala.collection.mutable.LinkedList 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val b1: BitSet = BitSet(11, 22, 33) 
        val b2 = LinkedList("A", "B")

        // Applying BitSet ++() function 
        val bs1 = b1 ++: b2

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
LinkedList(0, 1, 2, 3, A, B)

```