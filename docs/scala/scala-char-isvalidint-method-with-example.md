# Scala Char is validaint()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-is validaint-method-with-example/](https://www.geeksforgeeks.org/scala-char-isvalidint-method-with-example/)

**is validaint()**方法用于查找所述字符是否在 Int 类型的范围内。

> **方法定义:**def is validaint:Boolean
> 
> **返回类型:**如果所述字符在类型 Int 的范围内，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isValidInt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidInt() method 
        val result = ('\u9999').isValidInt

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
// Scala program of isValidInt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidInt() method
        val result = ('\u0555').isValidInt

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```