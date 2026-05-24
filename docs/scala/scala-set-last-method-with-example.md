# Scala Set last()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-last-method-with-example/](https://www.geeksforgeeks.org/scala-set-last-method-with-example/)

利用 **last()** 方法返回集合的最后一个元素。

> **方法定义:**定义最后:答
> 
> **返回类型:**返回集合的最后一个元素。

**示例#1:**

```scala
// Scala program of last() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4) 

        // Applying last method 
        val result = s1.last

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
4

```

**例 2:**

```scala
// Scala program of last() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set("geeks", "for", "geeks", "classes") 

        // Applying last method 
        val result = s1.last

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
classes

```