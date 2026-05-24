# Scala Float > =(x: Long)方法示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-long-method-with-example-11/](https://www.geeksforgeeks.org/scala-float-x-long-method-with-example-11/)

如果浮点值大于或等于指定的长值，则使用 **> =(x:长)**方法返回真。

> **方法定义:** (Float_Value)。> =(Long_Value)
> **返回类型:**如果浮点值大于或等于指定的长值，则返回 true。

**示例#1:**

```scala
// Scala program of Float >=(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >=(x: Long) function
        val result = (100.0).>=(60)

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
// Scala program of Float >=(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >=(x: Long) function
        val result = (10.0).>=(60)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```