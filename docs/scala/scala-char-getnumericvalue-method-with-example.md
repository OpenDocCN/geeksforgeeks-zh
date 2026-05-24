# Scala Char getNumericValue()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-getnumericvalue-method-with-example/](https://www.geeksforgeeks.org/scala-char-getnumericvalue-method-with-example/)

**getNumericValue()** 方法用于返回给定字符的数值。

> **方法定义:**定义 getNumericValue: Int
> 
> **返回类型:**返回整数。

**例:1#**

```scala
// Scala program of getNumericValue()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying getNumericValue() method 
        val result = ('Z').getNumericValue

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
35

```

**例:2#**

```scala
// Scala program of getNumericValue()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying getNumericValue() method
        val result = 'B'.getNumericValue

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
11

```