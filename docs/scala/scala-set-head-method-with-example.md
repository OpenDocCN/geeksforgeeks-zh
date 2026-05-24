# Scala Set head()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-head-method-with-example/](https://www.geeksforgeeks.org/scala-set-head-method-with-example/)

利用 **head()** 方法显示集合的第一个元素。

> **方法定义:**定义标题:A
> 
> **返回类型:**返回集合的第一个元素。

**示例#1:**

```scala
// Scala program of head() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(5, 1, 2, 3, 4) 

        // Applying head method 
        val result = s1.head

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
// Scala program of head() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 16, 22, 3, 51) 

        // Applying head method 
        val result = s1.head

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
41

```