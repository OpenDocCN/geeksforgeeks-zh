# Scala Int *(x: Char)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-char-method-with-example-2/](https://www.geeksforgeeks.org/scala-int-x-char-method-with-example-2/)

使用 ***(x: Char)** 方法返回指定的 int 值和 Char 值的乘积。这里的字符值是指定字符的 ASCII 值。

> **方法定义:** (Int_Value)。*(字符值)
> 
> **返回类型:**返回指定的 int 值和 char 值的乘积。

**示例#1:**

```scala
// Scala program of Int *(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int *(x: Char) function
        val result = (100).*('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
6500

```

**例 2:**

```scala
// Scala program of Int *(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int *(x: Char) function
        val result = (10).*('B')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
660

```