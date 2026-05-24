# 斯卡拉国际

T2】原文:[https://www . geeksforgeeks . org/Scala-int-x-char-method-with-example-8/](https://www.geeksforgeeks.org/scala-int-x-char-method-with-example-8/)

如果指定的 int 值小于 Char 值，则使用 **< (x: Char)** 方法返回 true，否则返回 false。这里的字符值是指定字符的 ASCII 值。

> **方法定义:** (Int_Value)。< (Char_Value)
> **返回类型:**如果指定的 int 值小于 Char 值，则返回 true，否则返回 false。

**示例#1:**

## 斯卡拉

```scala
// Scala program of Int <(x: Char)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <(x: Char) function
        val result = (10).<('A')

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

## 斯卡拉

```scala
// Scala program of Int <(x: Char)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <(x: Char) function
        val result = (500).<('A')

        // Displays output
        println(result)

    }
}
```

**Output:** 

```scala
false
```