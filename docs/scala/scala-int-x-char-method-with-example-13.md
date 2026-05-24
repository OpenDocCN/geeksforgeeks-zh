# Scala Int > > (x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-char-method-with-example-13/](https://www.geeksforgeeks.org/scala-int-x-char-method-with-example-13/)

**> > (x: Char)** 方法用于返回一个值，该值是 int 值右移指定 Char 值的结果。这里的字符值是指定字符的 ASCII 值。

> **方法定义:** (Int_Value)。> > (Char_Value)
> **返回类型:**返回一个值，该值是 int 值右移指定字符值的结果。

**示例#1:**

```scala
// Scala program of Int >>(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>(x: Char) function
        val result = (11115).>>('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
5557

```

**例 2:**

```scala
// Scala program of Int >>(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>(x: Char) function
        val result = (11115).>>('B')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
2778

```