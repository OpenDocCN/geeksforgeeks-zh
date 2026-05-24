# Scala Int > > > (x: Char)法同例

> 原文:[https://www . geesforgeks . org/Scala-int-x-char-method-with-example-14/](https://www.geeksforgeeks.org/scala-int-x-char-method-with-example-14/)

**> > > (x: Char)** 方法用于返回一个值，该值是 int 值右移指定 Char 值的结果。这里左边的位用零填充。并且字符值是指定字符的 ASCII 值。

> **方法定义:** (Int_Value)。> > > (Char_Value)
> **返回类型:**返回一个值，该值是 int 值右移指定 Char 值的结果。

**示例#1:**

```scala
// Scala program of Int >>>(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>>(x: char) function
        val result = (11135).>>>('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
5567

```

**例 2:**

```scala
// Scala program of Int >>>(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>>(x: char) function
        val result = (11135).>>>('B')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
2783

```