# Scala Float to(end: Float，step: Float)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-float-toend-float-step-float-method-with-example/](https://www.geeksforgeeks.org/scala-float-toend-float-step-float-method-with-example/)

**到(结束:Float，步骤:Float)** 方法用于返回从所述 FLoat 值到“结束”的范围，该范围在参数列表中给出，并且在参数列表中也指定了一些步骤。

> **方法定义:**定义为(结束:浮动，步骤:浮动):包含
> 
> **返回类型:**返回范围。

**示例#1:**

```scala
// Scala program of Float to() 
// method 
// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 
        // Applying to() method 
        val result = (0.0).to(9.0, 4.0) 

        // Displays output 
        println(result) 

    } 
}   
```

**Output:**

```scala
NumericRange(0.0, 4.0, 8.0)

```

**例 2:**

```scala
// Scala program of Float to() 
// method 
// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 
        // Applying to() method 
        val result = (5.0).to(30.0, 4.0) 

        // Displays output 
        println(result) 

    } 
}  
```

**Output:**

```scala
NumericRange(5.0, 9.0, 13.0, 17.0, 21.0, 25.0, 29.0)

```