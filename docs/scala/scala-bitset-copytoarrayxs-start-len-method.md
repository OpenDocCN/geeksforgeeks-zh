# Scala BitSet copyToArray(xs，start，len)方法

> 原文:[https://www . geesforgeks . org/Scala-bitset-copytoarrayxs-start-len-method/](https://www.geeksforgeeks.org/scala-bitset-copytoarrayxs-start-len-method/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。使用+()方法将该位集的元素复制到数组中。

> **方法定义:** def copyToArray()
> 
> **返回类型:**位集数组的副本

**示例#1:**

```scala
// Scala program of copyToArray() 
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating BitSet 
        val s1 = BitSet(1, 2, 3) 

        val arr: Array[Int] = Array(0, 0, 0, 0, 0) 

        // Applying copyToArray method 
        s1.copyToArray(arr, 1, 2) 

        // Displays output 
        for(elem <- arr) 
        println(elem) 

    } 
} 
```

**Output:**

```scala
0
1
2
0
0

```

**例 2:**

```scala
// Scala program of copyToArray() 
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating BitSet 
        val s1 = BitSet(11, 22, 33) 

        val arr: Array[Int] = Array(0, 0, 0, 0, 0, 0) 

        // Applying copyToArray method 
        s1.copyToArray(arr, 2, 3) 

        // Displays output 
        for(elem <- arr) 
        println(elem) 

    } 
} 
```

**Output:**

```scala
0
0
11
22
33
0

```