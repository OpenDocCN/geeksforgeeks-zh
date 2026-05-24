# Scala Int < =(x: Double)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-double-method-with-example-8/](https://www.geeksforgeeks.org/scala-int-x-double-method-with-example-8/)

如果指定的 int 值小于或等于 Double 值，则使用 **< =(x: Double)** 方法返回 true，否则返回 false。

> **方法定义:** (Int_Value)。< =(双值)
> 
> **返回类型:**如果指定的 int 值小于或等于 double 值，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int <=(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <=(x: Double) function
        val result = (10).<=(100)

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
// Scala program of Int <=(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <=(x: Double) function
        val result = (500).<=(100)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```