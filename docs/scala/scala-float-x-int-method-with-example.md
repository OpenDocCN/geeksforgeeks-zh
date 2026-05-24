# Scala Float ==(x: Int)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-x-int-method-with-example/](https://www.geeksforgeeks.org/scala-float-x-int-method-with-example/)

如果浮点值等于 Int 值，则使用 **==(x: Int)** 方法返回 true，否则返回 false。

> **方法定义:** (Float_Value)。==(int_Value)
> 
> **返回类型:**如果浮点值等于 int 值则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Float ==(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Int) function
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
// Scala program of Float ==(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Int) function
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