# Scala BitSet apply()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-bitset-apply-method-with-example/](https://www.geeksforgeeks.org/scala-bitset-apply-method-with-example/)

Scala 位集是由非负整数组成的集合，这些整数被表示为大小可变的位数组，这些位被打包成 64 位的字。+()方法用于测试该集合中是否包含某些元素。

> **方法定义:**定义应用()
> 
> **返回类型:**如果集合中包含 elem，则为真，否则为假。

**示例#1:**

```scala
// Scala program of apply() 
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

        // Applying apply method 
        val result = s1.apply(3) 

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
// Scala program of apply() 
// method 
import scala.collection.immutable.BitSet 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating BitSet 
        val s1 = BitSet(10, 20, 30, 40, 50, 70) 

        // Applying apply method 
        val result = s1.apply(60) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
false

```