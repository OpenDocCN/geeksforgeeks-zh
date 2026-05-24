# Scala Char isLower()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-is lower-method-with-example/](https://www.geeksforgeeks.org/scala-char-islower-method-with-example/)

**isLower()** 方法用于检查所述字符值是否为小写。

> **方法定义:**定义:布尔型
> 
> **返回类型:**如果所述字符为小写，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isLower()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isLower() method 
        val result = ('c').isLower

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
// Scala program of isLower()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isLower() method
        val result = ('A').isLower

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```