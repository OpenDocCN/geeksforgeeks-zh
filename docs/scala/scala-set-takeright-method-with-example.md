# Scala Set takeRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-taker ight-method-with-example/](https://www.geeksforgeeks.org/scala-set-takeright-method-with-example/)

**takeRight()** 方法用于返回由集合的最后 n 个元素组成的集合。

> **方法定义:**def taker ight(n:Int):Set[A]
> 其中“n”指定要选择的元素数量。
> 
> **返回类型:**它返回一个由集合的最后‘n’个元素组成的集合。

**示例#1:**

```scala
// Scala program of takeRight() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 1) 

        // Applying takeRight method 
        val result = s1.takeRight(4) 

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
Set(1, 2, 3, 4)

```

**例 2:**

```scala
// Scala program of takeRight() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43) 

        // Applying takeRight method 
        val result = s1.takeRight(3) 

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
Set(12, 23, 43)

```