# Scala Float 直到(结束:Float，步骤:Float)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-float-untild-float-step-float-method-with-example/](https://www.geeksforgeeks.org/scala-float-untilend-float-step-float-method-with-example/)

**直到(结束:浮点，步骤:浮点)**方法用于返回从指定结束浮点值的起始值到精确先前值的范围。这里范围的值是逐级跳跃的。

> **方法定义:** defuntil(end: Float，step: Float): collection .不可变. Range
> 
> **返回类型:**返回范围。

**示例#1:**

```scala
// Scala program of Float until() 
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying until method 
        val result = (1.0).until(12.0, 3.0) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
NumericRange(1.0, 4.0, 7.0, 10.0)

```

**例 2:**

```scala
// Scala program of Float until() 
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying until method 
        val result = (3.0).until(20.0, 2.0) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
NumericRange(3.0, 5.0, 7.0, 9.0, 11.0, 13.0, 15.0, 17.0, 19.0)

```