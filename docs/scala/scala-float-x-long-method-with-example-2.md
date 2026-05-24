# Scala Float < =(x: Long)方法示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-long-method-with-example-2/](https://www.geeksforgeeks.org/scala-float-x-long-method-with-example-2/)

如果浮点值小于或等于长值，则使用 **< =(x: Long)** 方法返回真，否则返回假。

> **方法定义:** (Float_Value)。< =(长值)
> 
> **返回类型:**如果浮点值小于或等于长值，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float <=(x: long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <=(x: Long) function
        val result = (100.0).<=(50)

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
// Scala program of Float <=(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <=(x: Long) function
        val result = (50.0).<=(100)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```