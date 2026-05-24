# Scala Float ==(x: Long)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-x-long-method-with-example/](https://www.geeksforgeeks.org/scala-float-x-long-method-with-example/)

如果第一个浮点值等于第二个长值，则使用 **==(x: Long)** 方法返回真，否则返回假。

> **方法定义:** (Float_Value)。==(长值)
> 
> **返回类型:**如果浮点值等于长值则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Float ==(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Long) function
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
// Scala program of Float ==(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Long) function
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