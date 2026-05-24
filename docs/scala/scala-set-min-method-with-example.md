# Scala Set min()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-min-method-with-example/](https://www.geeksforgeeks.org/scala-set-min-method-with-example/)

max()方法用于查找所述列表中所有元素的最小元素。

> **方法定义:**定义最小值:A
> 
> **返回类型:**返回指定列表中所有元素中最小的一个。

**示例#1:**

```scala
// Scala program of min() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3) 

        // Applying min method 
        val result = s1.min

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
1

```

**例 2:**

```scala
// Scala program of min() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(5, 11, 23, 72, 14, 21, 118) 

        // Applying min method 
        val result = s1.min

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
5

```