# Scala Float 是一个带有示例的 Infinity()方法

> 原文:[https://www . geeksforgeeks . org/Scala-float-is regin unity-method-with-example/](https://www.geeksforgeeks.org/scala-float-isneginfinity-method-with-example/)

如果浮点值或指定的浮点值是负无穷大数，则使用**isneginfonity()**方法返回真，否则返回假。

> **方法定义:** (Float_Number)。是区域
> 
> **返回类型:**如果浮点值或指定的浮点值为负无穷大，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float isNegInfinity()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isNegInfinity method
        val result = (8.9).isNegInfinity

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

**例 2:**

```scala
// Scala program of Float isNegInfinity()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isNegInfinity method
        val result = (-7.965).isNegInfinity

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```