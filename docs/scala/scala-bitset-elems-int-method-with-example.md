# Scala BitSet +(elems: Int*)方法示例

> 原文:[https://www . geesforgeks . org/Scala-bitset-elems-int-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-elems-int-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。使用+(elems: Int*)方法创建一个带有附加元素的新集合，省略重复的元素。

> **方法定义:** def +()
> 
> **返回类型:**返回一个省略重复的新集合。

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

        val b2: Set[Int] = BitSet(5, 6, 7) + 55+56 

        // Displays output 
        println(b2) 

    } 
} 
```

**Output:**

```scala
BitSet(5, 6, 7, 55, 56)

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

        val b2: Set[Int] = BitSet(5, 6, 7) + 5+6+0

        // Displays output 
        println(b2) 

    } 
} 
```

**Output:**

```scala
BitSet(0, 5, 6, 7)

```