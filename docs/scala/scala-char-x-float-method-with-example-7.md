# Scala Char > (x: Float)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-float-method-with-example-7/](https://www.geeksforgeeks.org/scala-char-x-float-method-with-example-7/)

使用 **> (x: Float)** 方法来查找所述字符值是否大于“x”。“x”的类型必须是浮点型。

> **方法定义:** def > (x: Float):布尔值
> 
> **返回类型:**如果所述字符值大于“x”，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of >(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >(x: Float) method 
        val result = 'D'.>(99.6)

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
// Scala program of >(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >(x: Float) method
        val result = 'D'.>(55.2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```