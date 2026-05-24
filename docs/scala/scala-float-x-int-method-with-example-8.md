# Scala Float %(x: Int)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-int-method-with-example-8/](https://www.geeksforgeeks.org/scala-float-x-int-method-with-example-8/)

当给定的浮点值除以整数值时，使用 **%(x: Int)** 方法返回余数。

> **方法定义:** (Float_Value)。%(Int_Value)
> 
> **返回类型:**当给定的浮点值除以 int 值时，返回余数。

**示例#1:**

```scala
// Scala program of Float %(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Int) function
        val result = (65.0).%(65)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0.0

```

**例 2:**

```scala
// Scala program of Float %(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Int) function
        val result = (100.0).%(65)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
35.0

```