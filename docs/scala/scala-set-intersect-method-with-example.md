# Scala Set intersect()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-intersect-method-with-example/](https://www.geeksforgeeks.org/scala-set-intersect-method-with-example/)

利用**交集()**方法计算两个集合的交集。

> **方法定义:**定义交集(即:集合[A]):集合[A]
> 
> **返回类型:**它返回一个包含两个集合中元素的集合。

**示例#1:**

```scala
// Scala program of intersect() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 5) 

        val s2 = Set(11, 12, 13, 4, 5) 

        // Applying intersect method 
        val s3 = s1.intersect(s2) 

        s3.foreach(x => println(x))
    } 
} 
```

**Output:**

```scala
5
4

```

**例 2:**

```scala
// Scala program of intersect() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 5) 

        val s2 = Set(11, 2, 3, 4, 5) 

        // Applying intersect method 
        val s3 = s1.intersect(s2) 

        s3.foreach(x => println(x))
    } 
} 
```

**Output:**

```scala
5
2
3
4

```