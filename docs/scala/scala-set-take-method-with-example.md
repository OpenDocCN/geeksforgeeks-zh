# Scala Set take()方法示例

> 原文:[https://www . geesforgeks . org/Scala-set-take-method-with-example/](https://www.geeksforgeeks.org/scala-set-take-method-with-example/)

**take()** 方法用于返回由集合的前‘n’个元素组成的集合。

> **方法定义:** def take(n: Int): Set[A]
> 其中“n”指定要选择的元素数量。
> 
> **返回类型:**它返回一个由集合的前‘n’个元素组成的集合。

**示例#1:**

```scala
// Scala program of take() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4) 

        // Applying take method 
        val result = s1.take(2) 

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
Set(5, 1)

```

**例 2:**

```scala
// Scala program of take() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43) 

        // Applying take method 
        val result = s1.take(3) 

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
Set(41, 12, 23)

```