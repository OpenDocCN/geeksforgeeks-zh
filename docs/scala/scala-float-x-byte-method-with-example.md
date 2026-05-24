# Scala Float ==(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-byte-method-with-example/](https://www.geeksforgeeks.org/scala-float-x-byte-method-with-example/)

如果浮点值等于字节值，则使用 **==(x: Byte)** 方法返回真，否则返回假。

> **方法定义:** (Float_Value)。==(字节值)
> 
> **返回类型:**如果浮点值等于字节值，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float ==(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Byte) function
        val result = (100.0).==(50)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```

**例 2:**

```scala
// Scala program of Float ==(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying ==(x: Byte) function
        val result = (50.0).==(50)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```