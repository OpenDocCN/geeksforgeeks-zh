# Scala Set dropRight()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-drop right-method-with-example/](https://www.geeksforgeeks.org/scala-set-dropright-method-with-example/)

**dropRight()** 用于返回除最后‘n’个元素之外的所有元素。

> **方法定义:** def dropRight(n: Int): Set[A]
> 
> **返回类型:**它返回一个集合，该集合包含除最后‘n’个元素之外的所有元素。

**示例#1:**

```scala
// Scala program of dropRight()
// method

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating sets 
        val s1 = Set(1, 2, 3, 4, 5)

        // Applying dropRight method 
        val s2 = s1.dropRight(1) 

        // Displays output 
        for(elem <- s2)  
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

```

**例 2:**

```scala
// Scala program of dropRight()
// method

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating sets 
        val s1 = Set(1, 2, 3, 4, 5)

        // Applying dropRight method 
        val s2 = s1.dropRight(2) 

        // Displays output 
        for(elem <- s2)  
        println(elem) 

    } 
} 
```

**Output:**

```scala
5
1
2

```