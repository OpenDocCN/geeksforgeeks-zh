# Scala BitSet addString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-bitset-addstring-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-addstring-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。addString()方法用于将此可遍历或迭代器的所有元素追加到字符串生成器中。

> **方法定义:** def addString()
> 
> **返回类型:**返回附加了元素的字符串生成器 b。

**示例#1:**

```scala
// Scala program of Bitset addString
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val bitSet: BitSet = BitSet(0, 1, 2, 3) 
        val b = new StringBuilder()

        // Applying BitSet addString() function 
        val  bs1 = bitSet.addString(b)

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
0123

```

**例 2:**

```scala
// Scala program of Bitset addString
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        val bitSet: BitSet = BitSet(11, 22, 33) 
        val b = new StringBuilder()

        // Applying BitSet addString() function 
        val  bs1 = bitSet.addString(b)

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
112233

```