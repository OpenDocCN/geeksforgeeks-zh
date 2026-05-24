# Scala Char isWhole()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-isw hole-method-with-example/](https://www.geeksforgeeks.org/scala-char-iswhole-method-with-example/)

利用 **isWhole(()** 方法检查所述字符是否有小数成分。

> **方法定义:** def isWhole:布尔值
> 
> **返回类型:**如果所述字符是整数，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isWhole()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isWhole() method 
        val result = ('A').isWhole

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
// Scala program of isWhole()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isWhole() method
        val result = ('0').isWhole

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```