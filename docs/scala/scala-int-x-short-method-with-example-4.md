# Scala Int %(x: Short)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-short-method-with-example-4/](https://www.geeksforgeeks.org/scala-int-x-short-method-with-example-4/)

当指定的 int 值除以 Short 值时，使用 **%(x: Short)** 方法返回余数。

> **方法定义:** (Int_Value)。%(Short_Value)
> **返回类型:**当指定的 int 值除以 Short 值时返回余数。

**示例#1:**

```scala
// Scala program of Int %(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int %(x: Short) function
        val result = (100).%(50)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```

**例 2:**

```scala
// Scala program of Int %(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int %(x: Short) function
        val result = (100).%(40)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
20

```