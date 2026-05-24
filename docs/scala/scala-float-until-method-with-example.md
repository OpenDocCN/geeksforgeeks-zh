# Scala Float 直至()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-to-method-with-example/](https://www.geeksforgeeks.org/scala-float-until-method-with-example/)

使用**直到()**方法返回从第一点开始到终点的范围。这里第一点是包含性的，但端点是排他性的。

> **方法定义:** (First_Point)。直到(终点)
> 
> **返回类型:**返回创建的范围。

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
// Scala program of Float until()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying until method
        val result = (-6).until(0)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
Range(-6, -5, -4, -3, -2, -1)

```