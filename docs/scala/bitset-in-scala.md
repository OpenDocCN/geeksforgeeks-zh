# Scala 中的位集

> 原文:[https://www.geeksforgeeks.org/bitset-in-scala/](https://www.geeksforgeeks.org/bitset-in-scala/)

一个[集合](https://www.geeksforgeeks.org/set-in-scala-set-1/)是一个只包含不可重复的唯一项目的集合。位集是小整数的集合，是大整数的位。表示为 64 位字的可变大小位的[数组](https://www.geeksforgeeks.org/scala-arrays/)的非负整数集称为**位集**。存储在位集中的最大数字是位集的内存。它扩展了 Set [特性](https://www.geeksforgeeks.org/scala-traits/)。

**语法:**

```scala
var BS : BitSet = BitSet(element1, element2, element3, ....)  

Where BS is the name of created BitSet
```

在 Scala 中，BitSet 有两个版本:`**scala.collection.immutable.BitSet**`和`**scala.collection.mutable.BitSet**`。它们几乎是相同的，但是可变版本改变了位的位置，所以不可变的数据结构对并发性更好。

## 使用 BitSet 执行操作

**初始化位集:**下面是创建或初始化位集的示例。

**示例:**

```scala
// Scala program to initialize a BitSet
import scala.collection.immutable.BitSet

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        println("Initialize a BitSet")

        // Creating HashSet
        val bitSet: BitSet = BitSet(0, 1, 2, 3)
        println(s"Elements are = $bitSet")
    }
} 
```

**Output:**

```scala
Initialize a BitSet
Elements are = BitSet(0, 1, 2, 3)

```

**检查位集中的具体元素:**

**示例:**

```scala
// Scala program of Check specific elements in BitSet
import scala.collection.immutable.BitSet

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        println("Initialize a BitSet")

        // Creating BitSet
        val bitSet: BitSet = BitSet(0, 1, 2, 3)
        println(s"Elements are = $bitSet")

        // Checking
        println(s"Element 2 = ${bitSet(2)}")
        println(s"Element 4 = ${bitSet(4)}")
    }
} 
```

**Output:**

```scala
Initialize a BitSet
Elements are = BitSet(0, 1, 2, 3)
Element 2 = true
Element 4 = false

```

**在比特集中添加一个元素:**我们可以使用+号在比特集中添加一个元素。下面是在 BitSet 中添加元素的示例。

**示例:**

```scala
// Scala program of adding an element in BitSet
import scala.collection.immutable.BitSet

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        println("Initialize a BitSet")

        // Creating BitSet
        val bs: BitSet = BitSet(0, 1, 2, 3)
        println(s"Elements are = $bs")

        // Adding an element in BitSet
        val bs1: BitSet = bs + 10 + 11
        println(s"Adding elements to BitSet = $bs1")
    }
}
```

**Output:**

```scala
Initialize a BitSet
Elements are = BitSet(0, 1, 2, 3)
Adding elements to BitSet = BitSet(0, 1, 2, 3, 10, 11)

```

**在 BitSet 中添加多个元素:**我们可以使用++符号在 BitSet 中添加多个元素。下面是在 BitSet 中添加多个元素的示例。

**示例:**

```scala
// Scala program of adding more elements in BitSet
import scala.collection.immutable.BitSet

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        println("Initialize a BitSet")

        // Creating BitSet
        val bs: BitSet = BitSet(0, 1, 2, 3)
        println(s"Elements are = $bs")

        // Adding elements in BitSet
        val bs1: BitSet = bs ++ BitSet(4, 5, 6)
        println(s"Add more than one elements to BitSet = $bs1")
    }
}
```

**Output:**

```scala
Initialize a BitSet
Elements are = BitSet(0, 1, 2, 3)
Add more than one elements to BitSet  = BitSet(0, 1, 2, 3, 4, 5, 6)

```

**移除位集中的元素:**我们可以使用–号移除位集中的元素。下面是移除 BitSet 中元素的示例。

**示例:**

```scala
// Scala program of removing element in BitSet
import scala.collection.immutable.BitSet

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        println("Initialize a BitSet")

        // Creating BitSet
        val bs: BitSet = BitSet(0, 1, 2, 3)
        println(s"Elements are = $bs")

        // removing elements in BitSet
        val bs1: BitSet = bs - 2
        println(s"remove element from bitset = $bs1")
    }
}
```

**Output:**

```scala
Initialize a BitSet
Elements are = BitSet(0, 1, 2, 3)
remove element from bitset = BitSet(0, 1, 3)

```

**找到两个位集的交集:**我们可以使用&符号找到两个位集的交集。下面是寻找两个位集交集的例子。

**示例:**

```scala
// Scala program of finding the intersection between two BitSets
import scala.collection.immutable.BitSet

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        println("Initialize two BitSets")

        // Creating two BitSet
        val bs: BitSet = BitSet(0, 1, 2, 3)
        println(s"Elements of bitset1 are = $bs")

        val bs1: BitSet = BitSet(4, 5, 3, 6)
        println(s"Elements of bitset2 are = $bs1")

        // finding the intersection between two BitSets
        println(s"Intersection of bitSet1 and bitSet2 = ${bs & bs1}")
    }
}
```

**Output:**

```scala
Initialize two BitSets
Elements of bitset1 are = BitSet(0, 1, 2, 3)
Elements of bitset2 are = BitSet(3, 4, 5, 6)
Intersection of bitSet1 and bitSet2 = BitSet(3)

```

**初始化一个空的位组:**

**示例:**

```scala
// Scala program of Initializing an empty BitSet
import scala.collection.immutable.BitSet

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        // Initializing an empty BitSet
        val emptyBitSet: BitSet = BitSet.empty
        println(s"Empty BitSet = $emptyBitSet")
    }
}
```

**Output:**

```scala
Empty BitSet = BitSet()

```