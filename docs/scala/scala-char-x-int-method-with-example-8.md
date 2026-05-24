# 斯卡拉查尔

> 原文: [https://www .极客们。org/Scala-char-x-int-method-with-example-8/](https://www.geeksforgeeks.org/scala-char-x-int-method-with-example-8/)

使用 **< (x: Int)** 方法来查找所述字符值是否小于“x”。“x”的类型必须是整数。

> **方法定义:** def < (x: Int):布尔值
> 
> **返回类型:**如果指定的字符值小于“x”，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of <(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Int) method 
        val result = 'D'.<(56)

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
// Scala program of <(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <(x: Int) method
        val result = 'D'.<(74)

        // Displays output
        println(result)

    }
}   
```

**Output:**

```scala
true

```