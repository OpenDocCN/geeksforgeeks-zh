# Scala BitSet ++:[B](即:TraversableOnce[B])方法，示例

> 原文:[https://www . geesforgeks . org/Scala-bitset-bthat-traversableonceb-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-bthat-traversableonceb-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。使用++:[B](that: TraversableOnce[B])方法创建一个集合，该集合包含左侧操作数中的元素以及右侧操作数中的元素。

**方法定义:** def ++:[B](即:TraversableOnce[B])

**返回类型:**它返回一个新的位集，该位集包含该位集的所有元素，后跟该位集的所有元素。

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

        val b1 = BitSet(0, 1, 2, 3) 
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

        val b1 = BitSet(11, 22, 33) 
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