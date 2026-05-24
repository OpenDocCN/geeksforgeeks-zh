# 斯卡拉查尔

> 原文: [https://www .极客们。org/Scala-char-x-双方法示例-4/](https://www.geeksforgeeks.org/scala-char-x-double-method-with-example-4/)

使用 **< (x: Double)** 方法来查找所述字符值是否小于“x”。“x”的类型必须是 Double。

> **方法定义:** def < (x: Double):布尔值
> 
> **返回类型:**如果指定的字符值小于“x”，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of <(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Double) method 
        val result = 'D'.<(111.65785)

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
// Scala program of <(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Double) method
        val result = 'D'.<(11.65785)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```