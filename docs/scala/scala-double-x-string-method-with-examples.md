# Scala Double +(x: String)方法示例

> 原文:[https://www . geesforgeks . org/Scala-double-x-string-method-with-examples/](https://www.geeksforgeeks.org/scala-double-x-string-method-with-examples/)

**+(x: String)** 方法用于查找参数中指定的 double 和给定的字符串‘x’类型的和。

> **语法:**def+(x:String):Double
> **返回:**它返回指定的 Double 和给定的字符串类型“x”的和。

**例 1:**

```scala
// Scala program of +(x: String) 
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying +(x: String) method  
        val result = 1.3943245623.+("Geeks") 

        // Displays output 
        println(result) 

    } 
}  
```

**输出:**

```scala
1.3943245623Geeks

```

**例 2:**

```scala
// Scala program of +(x: String) 
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying +(x: String) method  
        val result = 2.394324562334.+("gfg") 

        // Displays output 
        println(result) 

    } 
}    
```

**输出:**

```scala
2.394324562334gfg

```