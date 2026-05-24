# Scala Set ++()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-method-with-example-5/](https://www.geeksforgeeks.org/scala-set-method-with-example-5/)

++()方法用于将一个集合的元素添加到另一个集合中。

> **方法定义:** def ++(elems: A):集合【A】
> 
> **返回类型:**返回包含两个集合元素的新集合。

**示例#1:**

```scala
// Scala program of ++() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 3, 5) 

        val s2 = Set(2, 4, 6)

        // Applying ++() method 
        val result = s1 ++ s2

        // Display output
        print(result) 

    } 
} 
```

**Output:**

```scala
Set(5, 1, 6, 2, 3, 4)

```

**例 2:**

```scala
// Scala program of ++() 
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

        // Applying ++() method 
        val result = s1 ++ s2

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Set(5, 1, 41, 12, 72, 43, 23, 100)

```