# Scala Set &()法同例

> 原文:[https://www . geeksforgeeks . org/Scala-set-method-with-example-3/](https://www.geeksforgeeks.org/scala-set-method-with-example-3/)

**& ()** 方法用于创建一个新的集合，该集合由两个给定集合中存在的所有元素组成。

> **方法定义:**
> 
> **返回类型:**它返回一个新的集合，该集合由两个给定集合中存在的所有元素组成。

**示例#1:**

```scala
// Scala program of &() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        val s2 = Set(1, 100, 5, 12, 23)

        // Applying &() method 
        val result = s1.&(s2)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Set(1, 12, 23)

```

**例 2:**

```scala
// Scala program of &() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 3, 5, 7) 

        val s2 = Set(2, 4, 6, 8)

        // Applying &() method 
        val result = s1.&(s2)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Set()

```