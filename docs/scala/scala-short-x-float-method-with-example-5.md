# Scala Short %(x: Float)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-short-x-float-method-with-example-5/](https://www.geeksforgeeks.org/scala-short-x-float-method-with-example-5/)

使用 **%(x: Float)** 方法来求所述短值除以 Float 类型的“x”的余数。

> **方法定义:** def %(x: Float): Float
> 
> **返回类型:**返回 Float。

**例:1#**

```scala
// Scala program of %(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Float) method 
        val result = (995).%(2.1)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1.699999999999958

```

**例:2#**

```scala
// Scala program of %(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying %(x: Float) method
        val result = (449).%(4.5)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
3.5

```