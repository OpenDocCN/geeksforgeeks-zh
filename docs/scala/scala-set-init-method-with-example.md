# Scala Set init()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-init-method-with-example/](https://www.geeksforgeeks.org/scala-set-init-method-with-example/)

**init()** 方法用于查找集合中除最后一个元素之外的所有元素。

> **方法定义:**定义初始化:设置[A]
> 
> **返回类型:**返回集合中除最后一个元素以外的所有元素。

**示例#1:**

```scala
// Scala program of init() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 5) 

        // Applying init method 
        val result = s1.init

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
Set(5, 1, 2, 3)

```

**例 2:**

```scala
// Scala program of init() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(16, 22, 3, 41, 51) 

        // Applying init method 
        val result = s1.init

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
Set(41, 22, 3, 16)

```