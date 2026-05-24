# Scala Char signum()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-signum-method-with-example/](https://www.geeksforgeeks.org/scala-char-signum-method-with-example/)

**signum()** 方法用于返回作为参数传递给它的字符值的 Sign 函数。如果传递的参数大于零，那么它将返回 1，如果它等于零，那么它将返回零，如果它小于零，那么它将返回-1。

> **方法定义:**定义符号:Int
> 
> **返回类型:**返回整数。

**例:1#**

```scala
// Scala program of signum()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying signum() method 
        val result = ('F').signum

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1

```

**例:2#**

```scala
// Scala program of signum()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying signum() method
        val result = ('a').signum

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1

```