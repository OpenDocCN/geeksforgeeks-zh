# Scala BitSet ++[B](即:GenTraversableOnce[B])方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-bthat-gentraversableonceb-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-bthat-gentraversableonceb-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。++[B](即:GentraversableOne[B])
方法用于创建一个位集，该位集包含左侧操作数的元素，后跟右侧操作数的元素。

**方法定义:** def ++[B](即:GenTraversableOnce[B])

**返回类型:**它返回一个包含该位集所有元素的新位集。

**示例#1:**

```scala
// Scala program of Bitset ++
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val b1: BitSet = BitSet(0, 1, 2, 3) 
        val b2 = List("a", "B") 

        // Applying BitSet ++() function 
        val bs1 = b1 ++ b2

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
Set(0, 1, a, 2, B, 3)

```

**例 2:**

```scala
// Scala program of Bitset ++
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val b1: BitSet = BitSet(0, 1, 2, 3 ) 
        val b2 = List("A" ) 

        // Applying BitSet ++() function 
        val bs1 = b1 ++ b2

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
Set(0, 1, A, 2, 3)

```