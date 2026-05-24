# Scala Double +(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-double-x-char-method-with-example-3/](https://www.geeksforgeeks.org/scala-double-x-char-method-with-example-3/)

**+(x: Char)** 方法用于查找参数中指定的 double 和给定的“x”类型 Char 之和。

> **语法:** def +(x: Char): Double
> **返回:**它返回指定的 Double 和给定的 Char 类型“x”的和。

**例 1:**

```scala
// Scala program of +(x: Char) 
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying +(x: Char) method  
        val result = 5.39432456.+('A') 

        // Displays output 
        println(result) 

    } 
}  
```

**输出:**

```scala
70.39432456

```

**例 2:**

```scala
// Scala program of +(x: Char) 
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying +(x: Char) method  
        val result = 1.3943245623.+('c') 

        // Displays output 
        println(result) 

    } 
}  
```

**输出:**

```scala
100.3943245623

```