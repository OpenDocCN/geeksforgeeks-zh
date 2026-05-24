# Scala Char isControl()方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-is control-method-with-example/](https://www.geeksforgeeks.org/scala-char-iscontrol-method-with-example/)

利用 **isControl()** 方法检查所述字符是否为控制字符。其中，控制字符是格式化字符和其他非打印字符，如确认、标记、CR、FF、LF 和 VT。

> **方法定义:**定义为控制:布尔型
> 
> **返回类型:**如果所述字符是控制字符，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isControl()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isControl() method 
        val result = 'a'.isControl

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

**例:2#**

```scala
// Scala program of isControl()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isControl() method
        val result = '\n'.isControl

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```