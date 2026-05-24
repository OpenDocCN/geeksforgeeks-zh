# Scala Float isValidByte()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-is valid byte-method-with-example/](https://www.geeksforgeeks.org/scala-float-isvalidbyte-method-with-example/)

如果指定的数字为零或在标量范围内，则使用 **isValidByte()** 方法返回真。字节最小值和最大值；否则返回 false。

> **方法定义:** (Float_Number)。isValidByte
> 
> **返回类型:**如果指定的数字为零或在标量范围内，则返回真。字节最小值和最大值；否则返回 false。

**示例#1:**

```scala
// Scala program of Float isValidByte()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidByte method
        val result = (0).isValidByte

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
// Scala program of Float isValidByte()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidByte method
        val result = (5.9).isValidByte

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```