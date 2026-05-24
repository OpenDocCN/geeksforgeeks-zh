# Scala Set toString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-tostring-method-with-example/](https://www.geeksforgeeks.org/scala-set-tostring-method-with-example/)

**toString()** 方法用于返回由集合的所有元素组成的字符串。

> **方法定义:** def toString(): String
> 
> **返回类型:**它返回一个由集合的所有元素组成的字符串。

**示例#1:**

```scala
// Scala program of toString() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 5) 

        // Applying toString method 
        val result = s1.toString

        // Display output
        println(result)

    } 
} 
```

**Output:**

```scala
Set(5, 1, 2, 3, 4)

```

**例 2:**

```scala
// Scala program of toString() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        // Applying toString method 
        val result = s1.toString

        // Display output
        println(result)

    } 
} 
```

**Output:**

```scala
Set(1, 41, 12, 72, 43, 23)

```