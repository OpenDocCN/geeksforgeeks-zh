# 斯卡拉国际<

> 原文: [https://www .极客们。org/Scala-int-x-char-method-带示例-15/](https://www.geeksforgeeks.org/scala-int-x-char-method-with-example-15/)

**< < (x: Char)** 方法用于返回一个值，该值是 int 值左移指定 Char 值的结果。这里的字符值是指定字符的 ASCII 值。

> **方法定义:** (Int_Value)。< < (Char_Value)
> **返回类型:**返回一个值，该值是 int 值左移指定 Char 值的结果。

**示例#1:**

```scala
// Scala program of Int <<(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <<(x: Char) function
        val result = (158597).<<('A')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
317194

```

**例 2:**

```scala
// Scala program of Int <<(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <<(x: Char) function
        val result = (1587).<<('B')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
6348

```