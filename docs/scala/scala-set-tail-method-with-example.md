# Scala 集尾()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-tail-method-with-example/](https://www.geeksforgeeks.org/scala-set-tail-method-with-example/)

**tail()** 方法用于返回一个集合，该集合包含除该集合的第一个元素之外的所有元素。

> **方法定义:**定义尾部:集合【A】
> 
> **返回类型:**返回一个集合，该集合由集合中除第一个元素以外的所有元素组成。

**示例#1:**

```scala
// Scala program of tail() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(4, 1, 2, 3) 

        // Applying tail method 
        val result = s1.tail

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
Set(1, 2, 3)

```

**例 2:**

```scala
// Scala program of tail() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43) 

        // Applying tail method 
        val result = s1.tail

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
Set(12, 23, 43)

```