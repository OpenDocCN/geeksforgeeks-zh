# Scala List lastIndexOf()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-last indexof-method-with-example/](https://www.geeksforgeeks.org/scala-list-lastindexof-method-with-example/)

**lastIndexOf()** 方法用于查找该方法中作为参数出现的元素的最后一次出现的索引。

> **方法定义:** def lastIndexOf(elem: A，end: Int): Int
> 
> **返回类型:**返回该方法中元素最后一次出现的索引作为参数。

**示例#1:**

```scala
// Scala program of lastIndexOf()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(3, 6, 2, 9, 21, 9)

        // Applying lastIndexOf method
        val result = m1.lastIndexOf(9)

        // Displays output
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
// Scala program of lastIndexOf()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(3, 6, 2, 9, 3, 21, 3)

        // Applying lastIndexOf method
        val result = m1.lastIndexOf(3)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
6

```