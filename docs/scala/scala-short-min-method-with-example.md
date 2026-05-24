# Scala 短 min()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-short-min-method-with-example/](https://www.geeksforgeeks.org/scala-short-min-method-with-example/)

利用 **min()** 方法寻找两个指定短类型的最小值。

> **方法定义:** def min(即:短):短
> 
> **返回类型:**以最小值返回 Short 类型的编号。

**例:1#**

```scala
// Scala program of min()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying min() method 
        val result = (1000).min(998)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
998

```

**例:2#**

```scala
// Scala program of min()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying min() method
        val result = (445).min(1000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
445

```