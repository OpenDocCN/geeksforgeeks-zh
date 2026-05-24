# Scala Set map()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-map-method-with-example/](https://www.geeksforgeeks.org/scala-set-map-method-with-example/)

**map()** 方法用于通过将函数应用于一个新集合的所有元素来构建该集合。

> **方法定义:** def 图【B】(f:(A)=>B):不可变。集合[B]
> 
> **返回类型:**应用给定函数后返回包含所有元素的新集合。

**示例#1:**

```scala
// Scala program of map() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(5, 1, 3, 2, 4) 

        // Applying map method 
        val result = s1.map(x => x*x)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
Set(25, 1, 9, 16, 4)

```

**例 2:**

```scala
// Scala program of map() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(5, 1, 3, 2, 4) 

        // Applying map method 
        val result = s1.map(x => x/2)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
Set(2, 0, 1)

```