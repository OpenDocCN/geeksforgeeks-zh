# Scala Float is hole()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-isw hole-method-with-example/](https://www.geeksforgeeks.org/scala-float-iswhole-method-with-example/)

如果指定的数字没有小数部分，则使用 **isWhole()** 方法返回真，否则返回假。

> **方法定义:** (Float_Number)。isWhole
> 
> **返回类型:**如果指定的数字没有小数部分，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float isWhole()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isWhole method
        val result = (5).isWhole

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
// Scala program of Float isWhole()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isWhole method
        val result = (5.9).isWhole

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```