# Scala Int 直到(end: Int，step: Int)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-un tild-int-step-int-method-with-example/](https://www.geeksforgeeks.org/scala-int-untilend-int-step-int-method-with-example/)

**直到(结束:Int，步骤:Int)** 方法用于返回从开始值到指定结束整数值的精确前一个值的范围。这里范围的值是逐级跳跃的。

> **方法定义:** defuntil(end: Int，step: Int): collection .不可变. Range
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
        val result = (10).until(17, 2) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
Range(10, 12, 14, 16)

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
        val result = (1).until(12, 3) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
Range(1, 4, 7, 10)

```