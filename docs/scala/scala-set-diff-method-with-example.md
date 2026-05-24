# Scala Set diff()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-diff-method-with-example/](https://www.geeksforgeeks.org/scala-set-diff-method-with-example/)

**diff()** 方法用于计算一个集合和另一个集合的差。

> **方法定义:**定义差异(即:集合[A]):集合[A]
> 
> **返回类型:**返回一个集合，这个集合是两个集合的差。

**示例#1:**

```scala
// Scala program of diff()
// method

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating sets 
        val s1 = Set(1, 2, 3, 4, 5)

        val s2 = Set(1, 2, 3)

        // Applying diff method 
        val s3 = s1.diff(s2) 

        // Displays output 
        for(elem <- s3)  
        println(elem) 

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
// Scala program of diff()
// method

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating sets 
        val s1 = Set(1, 2, 3, 4, 5)

        val s2 = Set(6, 2, 7, 8)

        // Applying diff method 
        val s3 = s1.diff(s2) 

        // Displays output 
        for(elem <- s3)  
        println(elem) 

    } 
} 
```

**Output:**

```scala
5
1
3
4

```