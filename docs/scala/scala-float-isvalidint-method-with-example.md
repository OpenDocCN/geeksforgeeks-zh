# Scala Float is validaint()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-is validaint-method-with-example/](https://www.geeksforgeeks.org/scala-float-isvalidint-method-with-example/)

如果指定的数字为零或在 isValidInt 最小值和最大值的范围内，则使用**is validaint()**方法返回真；否则返回 false。

> **方法定义:** (Float_Number)。isValidInt
> 
> **返回类型:**如果指定的数字为零或在 scala.Int 最小值和最大值范围内，则返回真；否则返回 false。

**示例#1:**

```scala
// Scala program of Float isValidInt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidInt method
        val result = (0).isValidInt

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
// Scala program of Float isValidInt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidInt method
        val result = (5.9).isValidInt

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```