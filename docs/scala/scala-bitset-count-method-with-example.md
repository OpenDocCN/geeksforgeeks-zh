# Scala BitSet count()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-count-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-count-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。count()方法用于计算可遍历或迭代器中的元素数量

> **方法定义:** def 计数()
> 
> **返回类型:**返回元素个数

**示例#1:**

```scala
// Scala program of count() 
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating BitSet 
        val s1 = BitSet(1, 2, 3, 4, 5) 

        // Applying count method 
        val result = s1.count(z=>true) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
5

```

**例 2:**

```scala
// Scala program of count() 
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

        // Applying count method 
        val result = s1.count(z=>true) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
3

```