# 斯卡拉查尔<

> 原文: [https://www .极客们。org/Scala-char-x-long-method-example-10/](https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-10/)

利用 **< < (x: Long)** 方法，找到在 Long 类型的参数列表中指定的位数左移的字符值，新的位用零填充。

> **方法定义:** def < < (x: Long): Int
> 
> **返回类型:**返回整数。

**例:1#**

```scala
// Scala program of <<(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <<(x: Long) method 
        val result = 'Z'.<<(100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
386547056640

```

**例:2#**

```scala
// Scala program of <<(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <<(x: Long) method
        val result = 'D'.<<(-100000L)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
292057776128

```