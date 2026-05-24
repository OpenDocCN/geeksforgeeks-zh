# Scala BitSet +()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-method-with-example-2/](https://www.geeksforgeeks.org/scala-bitset-method-with-example-2/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。除非元素已经存在，否则使用+()方法创建带有附加元素的新集合。

> **方法定义:** def +()
> 
> **返回类型:**返回一个包含该集合所有元素的新集合。

**示例#1:**

```scala
// Scala program of Bitset +
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

        // Applying BitSet +() function 
        val bs1: BitSet = bitSet + 10 + 11

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
Elements in Bitset are = BitSet(0, 1, 2, 3)
BitSet(0, 1, 2, 3, 10, 11)

```

**例 2:**

```scala
// Scala program of Bitset +
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

        // Applying BitSet +() function 
        val bs1: BitSet = bitSet + 1 + 2 + 3

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
Elements in Bitset are = BitSet(0, 1, 2, 3)
BitSet(0, 1, 2, 3)

```