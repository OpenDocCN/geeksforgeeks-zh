# Scala Char isTitleCase()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-istitlecase-method-with-example/](https://www.geeksforgeeks.org/scala-char-istitlecase-method-with-example/)

使用 **isTitleCase()** 方法来查找所述字符是否是标题大小写字符。如果一个字符的由 Character.getType(ch)产生的一般类别类型是 TITLECASE_LETTER，则该字符被称为标题大小写字符。

> **方法定义:**定义:布尔型
> 
> **返回类型:**如果所述字符为标题大小写，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isTitleCase()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isTitleCase() method 
        val result = '\u01f2'.isTitleCase

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

**例:2#**

```scala
// Scala program of isTitleCase()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isTitleCase() method
        val result = ('T').isTitleCase

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```