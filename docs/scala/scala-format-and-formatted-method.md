# Scala |格式和格式化方法

> 原文:[https://www . geesforgeks . org/Scala-format-and-format-method/](https://www.geeksforgeeks.org/scala-format-and-formatted-method/)

有时在竞争性编程中，以给定的指定格式打印输出是很重要的。大多数用户都熟悉 c 语言中的 printf 函数。让我们看看如何在 Scala 中格式化输出。当一个字符串包含值和其后的文本时，需要格式化来更改值和添加包含它的文本。
**例:**

```scala
I have written 30 articles
```

**注:**

*   在 Scala 中，字符串的格式化可以通过两种方法完成，即 format()方法和 format()方法。
*   这些方法都是从名为 StringLike 的特性着手的。

**Format method**

***【格式】*** 方法可用于格式化字符串，您甚至可以向其传递参数，其中 *%d* 用于整数， *%f* 用于浮点或双精度。
**示例:**

```scala
// Scala program of format 
// method

// Creating object
object GFG
{

    // Main method
    def main(args: Array[String])
    {

        // Creating format string
        val x = "There are %d books and" + 
                    "cost of each book is %f"

        // Assigning values 
        val y = 15
        val z = 345.25

        // Applying format method
        val r = x.format(y, z)

        // Displays format string 
        println(r)
    }
}
```

**Output:**

```scala
There are 15 books and cost of each book is 345.250000

```

**示例:**

```scala
// Scala program of format for
// strings and characters.

// Creating object
object GFG
{

    // Main method
    def main(args: Array[String])
    {

        // Creating format string
        val x = "Geet%c is a %s."

        // Assigning values 
        val a = 'a'
        val b = "coder"

        // Applying format method
        val r = x.format(a, b)

        // Displays format string 
        println(r)
    }
}
```

**Output:**

```scala
Geeta is a coder.

```

这里，%s 用于字符串，%c 用于字符。

**Formatted method**

这个方法可以用于整数、双精度和字符串，因为它可以应用于任何对象。
**例:**

```scala
// Scala program for formatted
// method

// Creating object
object GFG
{

    // Main method
    def main(args: Array[String])
    {

        // Assigning values 
        val x = 30

        // Applying formatted method
        val r = x.formatted("I have written %d articles.")

        // Displays format string 
        println(r)
    }
}
```

**Output :**

```scala
I have written 30 articles.

```

这里，格式字符串作为参数在格式化方法中传递。