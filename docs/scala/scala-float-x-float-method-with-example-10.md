# Scala Float > (x: Float)方法示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-float-method-with-example-10/](https://www.geeksforgeeks.org/scala-float-x-float-method-with-example-10/)

如果第一个浮点值大于指定的第二个浮点值，则使用 **> (x:浮点)**方法返回真。

> **方法定义:** (First_Float_Value)。> (Second_Float_Value)
> **返回类型:**如果第一个浮点值大于指定的第二个浮点值，则返回 true。

**示例#1:**

```scala
// Scala program of Float >(x: float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >(x: float) function
        val result = (100.0).>(50.0)

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
// Scala program of Float >(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >(x: Float) function
        val result = (65.0).>(100.0)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```