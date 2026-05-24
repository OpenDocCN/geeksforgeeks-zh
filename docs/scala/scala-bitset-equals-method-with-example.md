# Scala BitSet equals()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-equals-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-equals-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。equals()方法将此集合与另一个对象进行比较以获得相等性。

> **方法定义:** def 等于()
> 
> **返回类型:**如果该集合包含与该集合相同的元素，则返回真。

**示例#1:**

```scala
// Scala program of equals() 
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
        val s2 = BitSet(5, 2, 3, 1, 4) 

        // Applying equals method 
        val result = s1.equals(s2) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of equals() 
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating BitSet 
        val s1 = BitSet(11, 10, 2019)  
        val s2 = BitSet(9, 10, 2018)  

        // Applying equals method 
        val result = s1.equals(s2) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
false

```