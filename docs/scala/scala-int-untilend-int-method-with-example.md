# Scala Int 直到(end: Int)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-un tild-int-method-with-example/](https://www.geeksforgeeks.org/scala-int-untilend-int-method-with-example/)

**直到(end: Int)** 方法用于返回从指定结束整数值的起始值到精确的前一个值的范围。

> **方法定义:**de funtil(end:Int):collection .不可变. Range
> 
> **返回类型:**返回范围。

**示例#1:**

```scala
// Scala program of Int until() 
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying until method 
        val result = (1).until(9) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
Range(1, 2, 3, 4, 5, 6, 7, 8)

```

**例 2:**

```scala
// Scala program of Int until() 
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying until method 
        val result = (10).until(17) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
Range(10, 11, 12, 13, 14, 15, 16)

```