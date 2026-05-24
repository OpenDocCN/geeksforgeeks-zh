# Scala Float > (x: Short)方法示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-short-method-with-example-10/](https://www.geeksforgeeks.org/scala-float-x-short-method-with-example-10/)

如果浮点值大于指定的短值，则使用 **> (x:短)**方法返回真。

> **方法定义:** (Float_Value)。>(短值)
> **返回类型:**如果浮点值大于指定的短值，则返回真。

**示例#1:**

```scala
// Scala program of Float >(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >(x: Short) function
        val result = (100.0).>(50)

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
// Scala program of Float >(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >(x: Short) function
        val result = (65.0).>(100)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```