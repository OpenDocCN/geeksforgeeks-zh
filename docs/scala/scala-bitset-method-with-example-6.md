# Scala BitSet ++()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-method-with-example-6/](https://www.geeksforgeeks.org/scala-bitset-method-with-example-6/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。使用+()方法通过将另一个集合中包含的所有元素添加到这个集合中来创建一个新的集合，省略重复的元素。

> **方法定义:** def ++()
> 
> **返回类型:**返回添加了给定元素的新集合，

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
        val b2: BitSet = BitSet(4, 5, 6, 7) 

        // Applying BitSet ++() function 
        val bs1: BitSet = b1 ++ b2

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
BitSet(0, 1, 2, 3, 4, 5, 6, 7)

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
        val b2: BitSet = BitSet(15, 16, 17 ) 

        // Applying BitSet ++() function 
        val bs1: BitSet = b1 ++ b2

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
BitSet(0, 1, 2, 3, 15, 16, 17)

```