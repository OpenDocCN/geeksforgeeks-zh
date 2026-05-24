# Scala Char ==(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-byte-method-with-example-9/](https://www.geeksforgeeks.org/scala-char-x-byte-method-with-example-9/)

使用 **==(x: Byte)** 方法来查找所述字符值是否等于“x”。“x”的类型必须是字节。

> **方法定义:** def ==(x: Byte):布尔值
> 
> **返回类型:**如果所述字符值等于“x”，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of ==(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Byte) method 
        val result = 'D'.==(-127)

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
// Scala program of ==(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Byte) method
        val result = 'Z'.==(90)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```