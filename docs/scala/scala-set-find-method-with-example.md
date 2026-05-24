# Scala Set find()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-find-method-with-example/](https://www.geeksforgeeks.org/scala-set-find-method-with-example/)

**find()** 方法用于查找满足给定谓词(如果存在)的集合的第一个元素。

> **方法定义:** def find(p: (A) = > Boolean:选项【A】
> 
> **返回类型:**返回满足给定谓词的集合的第一个元素。

**示例#1:**

```scala
// Scala program of find() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s1 = Set(5, 12, 3, 13) 

        // Applying find method 
        val result = s1.find(_ == 3) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
Some(3)

```

**例 2:**

```scala
// Scala program of find() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a set 
        val s1 = Set(5, 12, 3, 13) 

        // Applying find method 
        val result = s1.find(_ == 10) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
None

```