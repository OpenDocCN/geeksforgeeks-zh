# Scala Set mkString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-MK string-method-with-example/](https://www.geeksforgeeks.org/scala-set-mkstring-method-with-example/)

**mkString()** 方法用于显示字符串中集合的所有元素。

> **方法定义:** def mkString: String
> 
> **返回类型:**返回包含集合中所有元素的字符串。

**示例#1:**

```scala
// Scala program of mkString() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4) 

        // Applying mkString method 
        val result = s1.mkString

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
1234

```

**例 2:**

```scala
// Scala program of mkString() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set("Geeks", "Will", "Rule") 

        // Applying mkString method 
        val result = s1.mkString

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
GeeksWillRule

```