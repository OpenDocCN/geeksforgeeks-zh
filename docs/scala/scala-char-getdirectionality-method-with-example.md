# Scala Char getDirectionality()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-get directionality-method-with-example/](https://www.geeksforgeeks.org/scala-char-getdirectionality-method-with-example/)

**getDirectionality()** 方法用于返回指示字符值的方向性属性的字节。

> **方法定义:**定义获取方向:字节
> 
> **返回类型:**返回字节。

**例:1#**

```scala
// Scala program of getDirectionality()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying getDirectionality() method 
        val result = ('7').getDirectionality

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
3

```

**例:2#**

```scala
// Scala program of getDirectionality()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying getDirectionality() method
        val result = 'B'.getDirectionality

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```