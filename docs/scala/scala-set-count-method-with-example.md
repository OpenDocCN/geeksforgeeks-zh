# Scala Set count()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-count-method-with-example/](https://www.geeksforgeeks.org/scala-set-count-method-with-example/)

**计数()**方法用于计数集合中的元素数量。

> **方法定义:** def 计数(p: (A) = >布尔值:Int
> 
> **返回类型:**返回集合中存在的元素数量。

**示例#1:**

```scala
// Scala program of count()
// method

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating sets 
        val s1 = Set(1, 2, 3, 4, 5) 

        // Applying count method 
        val result = s1.count(z=>true) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
5

```

**例 2:**

```scala
// Scala program of count()
// method

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating sets 
        val s1 = Set() 

        // Applying count method 
        val result = s1.count(z=>true) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
0

```