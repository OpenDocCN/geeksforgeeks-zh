# 斯卡拉查尔

> 原文: [https://www .极客们。org/Scala-char-x-byte-method-example-7/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-7/)

使用 **< (x:字节)**方法来查找所述字符值是否小于“x”。“x”的类型必须是字节。

> **方法定义:** def < (x:字节):布尔值
> 
> **返回类型:**如果指定的字符值小于“x”，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of <(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Byte) method 
        val result = 'D'.<(127)

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
// Scala program of <(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Byte) method
        val result = 'D'.<(-127)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```