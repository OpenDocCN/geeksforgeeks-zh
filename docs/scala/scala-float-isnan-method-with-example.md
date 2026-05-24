# Scala Float isNaN()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-isnan-method-with-example/](https://www.geeksforgeeks.org/scala-float-isnan-method-with-example/)

如果此浮点值或指定的浮点值不是数字(NaN)，则使用 **isNaN()** 方法返回真，否则返回假。

> **方法定义:** (Float_Number)。isNaN
> 
> **返回类型:**如果该浮点值或指定的浮点值不是数字，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float isNaN()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isNaN method
        val result = (0.0/0.0).isNaN

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of Float isNaN()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isNaN method
        val result = (5.7).isNaN

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```