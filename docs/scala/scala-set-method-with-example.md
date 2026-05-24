# Scala Set +()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-method-with-example/](https://www.geeksforgeeks.org/scala-set-method-with-example/)

除非元素已经存在，否则使用 **+()** 方法创建带有附加元素的新集合。

> **方法定义:** def +(elem: A):集合【A】
> 
> **返回类型:**它返回一个带有附加元素的新集合，除非该元素已经存在。

**示例#1:**

```scala
// Scala program of +() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 6, 7) 

        // Applying +() method 
        val result = s1.+(5)

        // Display output
        print(result)    
    } 
} 
```

**Output:**

```scala
Set(5, 1, 6, 2, 7, 3, 4)

```

**例 2:**

```scala
// Scala program of +() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        // Applying +() method 
        val result = s1.+(100)

        // Display output
        print(result)    
    } 
} 
```

**Output:**

```scala
Set(1, 41, 12, 72, 43, 23, 100)

```