# Scala BitSet addString(sb:可变。StringBuilder，start，sep，end)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-bitset-addstringsb-mutatable-stringbuilder-start-sep-end-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-addstringsb-mutable-stringbuilder-start-sep-end-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。`addString(sb: mutable.StringBuilder, start: String, sep: String, end: String)`方法用于使用开始、结束和分隔符字符串将该位集的所有元素追加到字符串生成器中。

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

        val bitSet: BitSet = BitSet(11, 22, 33, 44) 
        val b = new StringBuilder()

        // Applying BitSet addString() function 
        val  bs1 = bitSet.addString(b, "BitSet(", ", ", ")")

        // Displays output 
        println(bs1) 

    } 
} 
```

**Output:**

```scala
BitSet(11, 22, 33, 44)

```