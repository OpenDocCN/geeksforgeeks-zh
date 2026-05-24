# Scala BitSet dropRight()方法示例

> 原文:[https://www . geesforgeks . org/Scala-bitset-drop right-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-dropright-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。drop()方法用于选择除 n 个项目之外的所有元素。

> **方法定义:** def 下降()
> 
> **返回类型:**它返回除 n 个项目之外的可迭代集合

**示例#1:**

```scala
// Scala program of drop() 
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

        // Applying dropRight method 
        val s2 = s1.dropRight(2)  

        // Displays output 
        for(elem <- s2) 
        println(elem) 

    } 
} 
```

**Output:**

```scala
1
2
3

```

**例 2:**

```scala
// Scala program of drop() 
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating BitSet 
        val s1 = BitSet(1, 2, 3, 7, 9, 4, 5) 

        // Applying dropRight method 
        val s2 = s1.dropRight(3)  

        // Displays output 
        for(elem <- s2) 
        println(elem) 

    } 
} 
```

**Output:**

```scala
1
2
3
4

```