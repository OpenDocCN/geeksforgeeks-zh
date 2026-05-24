# Scala Int %(x: Char)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-char-method-with-example-4/](https://www.geeksforgeeks.org/scala-int-x-char-method-with-example-4/)

当指定的 int 值除以 Char 值时，使用 **%(x: Char)** 方法返回余数。这里的字符值是指定字符的 ASCII 值。

> **方法定义:** (Int_Value)。%(Char_Value)
> **返回类型:**当指定的 int 值除以 Char 值时返回余数。

**示例#1:**

```scala
// Scala program of Int %(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int %(x: Char) function
        val result = (100).%('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
35

```

**例 2:**

```scala
// Scala program of Int %(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int %(x: Char) function
        val result = (10).%('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
10

```