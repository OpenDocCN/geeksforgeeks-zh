# Scala BitSet exists()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-exists-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-exists-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。exists()方法测试谓词是否适用于此可迭代集合的至少一个元素。

> **方法定义:** def 存在()
> 
> **返回类型:**如果该可迭代集合为空，则返回 false，否则返回 true。

**示例#1:**

```scala
// Scala program of exists() 
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

        // Applying exists method 
        val result = s1.exists(y => {y % 3 == 0})  

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
// Scala program of exists() 
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

        // Applying exists method 
        val result = s1.exists(y => {y % 7 == 0})  

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
false

```