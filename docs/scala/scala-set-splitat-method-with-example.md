# Scala Set splitAt()方法示例

> 原文:[https://www . geesforgeks . org/Scala-set-splitat-method-with-example/](https://www.geeksforgeeks.org/scala-set-splitat-method-with-example/)

**splitAt()** 方法用于在指定位置将给定集合分割成前缀/后缀对。

> **方法定义:** def splitAt(n: Int): (Set[A]，Set[A])
> 其中，n 是我们需要拆分的位置。
> 
> **返回类型:**它返回一对由这个集合的前 n 个元素和其他元素组成的集合。

**示例#1:**

```scala
// Scala program of splitAt() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(4, 12, 2, 31) 

        // Applying splitAt method 
        val result = s1.splitAt(2)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
(Set(4, 12), Set(2, 31))

```

**例 2:**

```scala
// Scala program of splitAt() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4) 

        // Applying splitAt method 
        val result = s1.splitAt(2)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
(Set(1, 2),Set(3, 4))

```