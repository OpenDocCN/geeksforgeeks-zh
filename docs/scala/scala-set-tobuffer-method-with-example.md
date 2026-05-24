# Scala Set toBuffer()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-to buffer-method-with-example/](https://www.geeksforgeeks.org/scala-set-tobuffer-method-with-example/)

**toBuffer()** 方法用于返回由集合的所有元素组成的缓冲区。

> **方法定义:**def to Buffer【B】>:A:Buffer【B】
> 
> **返回类型:**它返回一个包含集合所有元素的缓冲区。

**示例#1:**

```scala
// Scala program of toBuffer() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 5) 

        // Applying toBuffer method 
        val result = s1.toBuffer

        // Display output
        for (elem <- result)
            println(elem)

    } 
} 
```

**Output:**

```scala
5
1
2
3
4

```

**例 2:**

```scala
// Scala program of toBuffer() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        // Applying toBuffer method 
        val result = s1.toBuffer

        // Display output
        for (elem <- result)
            println(elem)

    } 
} 
```

**Output:**

```scala
1
41
12
72
43
23

```