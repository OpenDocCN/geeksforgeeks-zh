# Scala Float isPosInfinity()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-isposinity-method-with-example/](https://www.geeksforgeeks.org/scala-float-isposinfinity-method-with-example/)

如果浮点值或指定的浮点值为正无穷大，则使用**isposininity()**方法返回真，否则返回假。

> **方法定义:** (Float_Number)。isPosInfinity
> 
> **返回类型:**如果浮点值或指定的浮点值为正无穷大，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float isPosInfinity()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isPosInfinity method
        val result = (7.965).isPosInfinity

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
// Scala program of Float isPosInfinity()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isPosInfinity method
        val result = (0.0/0.0).isPosInfinity

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```