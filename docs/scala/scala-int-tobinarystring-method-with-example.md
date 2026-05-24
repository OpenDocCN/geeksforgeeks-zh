# Scala Int toBinaryString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-tobinarystring-method-with-example/](https://www.geeksforgeeks.org/scala-int-tobinarystring-method-with-example/)

**toBinaryString()** 方法用于返回指定整数值的二进制形式。

> **方法定义:** def toBinaryString: String
> 
> **返回类型:**返回指定整数值的二进制形式。

**示例#1:**

```scala
// Scala program of Int toBinaryString()
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 
        // Applying toBinaryString() method  
        val result = (5).toBinaryString

        // Displays output 
        println(result) 

    } 
}  
```

**Output:**

```scala
101

```

**例 2:**

```scala
// Scala program of Int toBinaryString()
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 
        // Applying toBinaryString() method  
        val result = (15).toBinaryString

        // Displays output 
        println(result) 

    } 
}   
```

**Output:**

```scala
1111

```