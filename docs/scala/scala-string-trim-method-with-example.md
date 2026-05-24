# Scala String trim()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-trim-method-with-example/](https://www.geeksforgeeks.org/scala-string-trim-method-with-example/)

**trim()** 方法用于省略所述字符串中的前导和尾随空格。

> **方法定义:**弦修剪()
> 
> **返回类型:**去掉所有空格后返回指定的字符串。

**例:1#**

```scala
// Scala program of trim()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying trim method
        val result = "     Nidhi Singh ".trim()

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
Nidhi Singh

```

**例:2#**

```scala
// Scala program of trim()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying trim method
        val result = "     Nidhi Singh GfG ".trim()

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
Nidhi Singh GfG

```