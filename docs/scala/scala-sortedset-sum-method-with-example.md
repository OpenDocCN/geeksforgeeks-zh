# Scala SortedSet sum()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-sorted set-sum-method-with-example/](https://www.geeksforgeeks.org/scala-sortedset-sum-method-with-example/)

利用 **sum()** 方法求排序集所有元素的和。

> **方法定义:**定义和:A
> 
> **返回类型:**返回 SortedSet 中所有元素的总和。

**示例#1:**

```scala
// Scala program of sum() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(4, 1, 2, 3) 

        // Applying sum method 
        val result = s1.sum

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
10

```

**例 2:**

```scala
// Scala program of sum() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a SortedSet 
        val s1 = SortedSet(4, 1, 2, 3, 6, 5, 8) 

        // Applying sum method 
        val result = s1.sum

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
29

```