# Scala Float ==(x: Short)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-x-short-method-with-example/](https://www.geeksforgeeks.org/scala-float-x-short-method-with-example/)

如果浮点值等于短值，则使用 **==(x:短)**方法返回真，否则返回假。

> **方法定义:** (Float_Value)。==(短值)
> 
> **返回类型:**如果浮点值等于短值则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float ==(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Short) function
        val result = (100.0).==(50)

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
// Scala program of Float ==(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Short) function
        val result = (50.0).==(50)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```