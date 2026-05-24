# Scala Set isEmpty()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-isempty-method-with-example/](https://www.geeksforgeeks.org/scala-set-isempty-method-with-example/)

利用 **isEmpty()** 方法测试集合是否为空。

> **方法定义:**定义为空:布尔值
> 
> **返回类型:**如果集合为空则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of isEmpty() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 5) 

        // Applying isEmpty method 
        val result = s1.isEmpty

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
false

```

**例 2:**

```scala
// Scala program of isEmpty() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set() 

        // Applying isEmpty method 
        val result = s1.isEmpty

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
true

```