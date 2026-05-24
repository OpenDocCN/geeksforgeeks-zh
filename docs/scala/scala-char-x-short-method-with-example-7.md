# 斯卡拉查尔

> 原文: [https://www .极客们。org/Scala-char-x-short-method-example-7/](https://www.geeksforgeeks.org/scala-char-x-short-method-with-example-7/)

使用 **< (x: Short)** 方法来查找所述字符值是否小于“x”。“x”的类型必须是“短”。

> **方法定义:** def < (x:短):布尔值
> 
> **返回类型:**如果指定的字符值小于“x”，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of <(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Short) method 
        val result = 'D'.<(10000)

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
// Scala program of <(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Short) method
        val result = 'D'.<(-10000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```