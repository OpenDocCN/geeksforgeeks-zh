# Scala Set dropWhile()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-drop while-method-with-example/](https://www.geeksforgeeks.org/scala-set-dropwhile-method-with-example/)

**dropWhile()** 方法用于从满足所述条件的集合中删除元素的最长前缀。

> **方法定义:**def drop while(p:(A)=>Boolean:Set[A]
> 
> **返回类型:**从满足规定条件的集合中删除最长的元素前缀后，返回包含所有元素的集合。

**示例#1:**

```scala
// Scala program of dropWhile() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        var s1 = Set(1, 3, 5, 4, 2) 

        // Print the set
        println(s1)

        // Applying dropWhile method 
        var res = s1.dropWhile(x => {x % 2 != 0}) 

        // Displays output 
        println(res) 

    } 
} 
```

**Output:**

```scala
Set(5, 1, 2, 3, 4)
Set(2, 3, 4)

```

**例 2:**

```scala
// Scala program of dropWhile() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a list 
        var s1 = Set(1, 3, 5, 4, 2) 

        // Print the set
        println(s1)

        // Applying dropWhile method 
        var res = s1.dropWhile(x => true) 

        // Displays output 
        println(res) 

    } 
} 
```

**Output:**

```scala
Set(5, 1, 2, 3, 4)
Set()

```