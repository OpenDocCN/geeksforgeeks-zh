# Scala BitSet dropWhile()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-drop while-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-dropwhile-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。drop()方法用于删除满足谓词的元素的最长前缀。

> **方法定义:** def 下降()
> 
> **返回类型:**返回集合中第一个元素不满足 p 的最长后缀。

**示例#1:**

```scala
// Scala program of dropWhile() 
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        var s1 = BitSet(1, 3, 5, 4, 2) 

        // Print the BitSet 
        println(s1) 

        // Applying dropWhile method 
        var res = s1.dropWhile(x => {x % 2 != 0}) 

        // Displays output 
        println(res) 

    } 
} 
```

**Output:**

```scala
BitSet(1, 2, 3, 4, 5)
BitSet(2, 3, 4, 5)

```

**例 2:**

```scala
// Scala program of dropWhile() 
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list  
        var s1 = BitSet(15, 17, 21)  

        // Print the BitSet
        println(s1) 

        // Applying dropWhile method  
        var res = s1.dropWhile(x => {x % 3 == 0})  

        // Displays output 
        println(res) 

    } 
} 
```

**Output:**

```scala
BitSet(15, 17, 21)
BitSet(17, 21)

```