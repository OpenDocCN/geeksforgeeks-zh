# Scala Set toArray()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-to array-method-with-example/](https://www.geeksforgeeks.org/scala-set-toarray-method-with-example/)

**toArray()** 用于返回一个由集合中所有元素组成的数组。

> **方法定义:**定义为数组:数组[A]
> 
> **返回类型:**它返回一个由集合的所有元素组成的数组。

**示例#1:**

```scala
// Scala program of toArray() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 7) 

        // Applying toArray method 
        val result = s1.toArray

        // Display output
        for (elem <- result)
            println(elem)

    } 
} 
```

**Output:**

```scala
1
2
7
3
4

```

**例 2:**

```scala
// Scala program of toArray() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        // Applying toArray method 
        val result = s1.toArray

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