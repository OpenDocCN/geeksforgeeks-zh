# Scala Set filter()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-filter-method-with-example/](https://www.geeksforgeeks.org/scala-set-filter-method-with-example/)

**过滤器()**方法用于选择满足所述谓词的集合的所有元素。

> **方法定义:** def 过滤器(p: (A) = >布尔型:集合[A]
> 
> **返回类型:**它返回一个集合，该集合包含满足给定谓词的集合的所有元素。

**示例#1:**

```scala
// Scala program of filter() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s1 = Set(5, 12, 3, 13) 

        // Applying filter method 
        val result = s1.filter(_ < 10) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
Set(5, 3)

```

**例 2:**

```scala
// Scala program of filter() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s1 = Set(5, 12, 3, 13) 

        // Applying filter method 
        val result = s1.filter(_ < 3) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
Set()

```