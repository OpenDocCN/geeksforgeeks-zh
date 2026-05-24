# Scala Set toList()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-to list-method-with-example/](https://www.geeksforgeeks.org/scala-set-tolist-method-with-example/)

利用 **toList()** 方法返回一个包含集合所有元素的列表。

> **方法定义:**定义为列表:列表[A]
> 
> **返回类型:**它返回一个包含集合所有元素的列表。

**示例#1:**

```scala
// Scala program of toList() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 5) 

        // Applying toList method 
        val result = s1.toList

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
// Scala program of toList() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        // Applying toList method 
        val result = s1.toList

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