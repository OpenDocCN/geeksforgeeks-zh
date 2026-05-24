# Scala 设置大小()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-size-method-with-example/](https://www.geeksforgeeks.org/scala-set-size-method-with-example/)

利用 **size()** 方法求出集合中元素的个数。

> **方法定义:**定义大小:整数
> 
> **返回类型:**返回集合中的元素个数。

**示例#1:**

```scala
// Scala program of size() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 5) 

        // Applying size method 
        val result = s1.size

        // Display output
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
// Scala program of size() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 0) 

        // Applying size method 
        val result = s1.size

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
2

```