# Scala Int！=(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-char-method-with-example-5/](https://www.geeksforgeeks.org/scala-int-x-char-method-with-example-5/)

**！=(x: Char)** 方法用于在 int 值不等于指定的 Char 值时返回 true，否则返回 false。这里的字符值是指定字符的 ASCII 值。

> **方法定义:** (Int_Value)。！=(字符值)
> 
> **返回类型:**如果 int 值不等于指定的 char 值，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int !=(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int !=(x: Char) function
        val result = (100).!=('A')

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
// Scala program of Int !=(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int !=(x: char) function
        val result = (65).!=('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```