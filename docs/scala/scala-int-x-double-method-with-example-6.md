# Scala Int > (x: Double)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-double-method-with-example-6/](https://www.geeksforgeeks.org/scala-int-x-double-method-with-example-6/)

如果指定的 int 值大于 Double 值，则使用 **> (x: Double)** 方法返回 true。

> **方法定义:** (Int_Value)。>(双值)
> 
> **返回类型:**如果指定的 int 值大于 double 值，则返回 true。

**示例#1:**

```scala
// Scala program of Int >(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >(x: Double) function
        val result = (65).>(10)

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
// Scala program of Int >(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >(x: Double) function
        val result = (50).>(100)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```