# Scala Set -()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-method-with-example-2/](https://www.geeksforgeeks.org/scala-set-method-with-example-2/)

-()方法用于创建一个新的集合，并从该集合中移除给定的元素。

> **方法定义:** def -(elem: A): Set[A]
> 
> **返回类型:**它返回一个新的集合，给定的元素从该集合中移除。

**示例#1:**

```scala
// Scala program of -() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(4, 1, 5, 3, 2, 100) 

        // Applying -() method 
        val result = s1.-(100)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Set(5, 1, 2, 3, 4)

```

**例 2:**

```scala
// Scala program of -() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        // Applying -() method 
        val result = s1.-(1)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Set(41, 12, 72, 43, 23)

```