# 斯卡拉查尔

> 原文: [https://www .极客们。org/Scala-char-x-char-method-with-example-6/](https://www.geeksforgeeks.org/scala-char-x-char-method-with-example-6/)

使用 **< (x: Char)** 方法来查找所述字符值是否小于“x”。“x”的类型必须是 Char。

> **方法定义:** def < (x: Char):布尔值
> 
> **返回类型:**如果指定的字符值小于“x”，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of <(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Char) method 
        val result = 'D'.<('A')

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
// Scala program of <(x: Char)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Char) method
        val result = 'D'.<('E')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```