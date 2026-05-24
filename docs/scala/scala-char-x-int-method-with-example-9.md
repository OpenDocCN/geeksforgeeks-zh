# 斯卡拉查尔<

> 原文: [https://www .极客们。org/Scala-char-x-int-method-with-example-9/](https://www.geeksforgeeks.org/scala-char-x-int-method-with-example-9/)

利用 **< < (x: Int)** 方法找到在 Int 类型的参数列表中指定的位数左移的字符值，新的位用零填充。

> **方法定义:** def < < (x: Int): Int
> 
> **返回类型:**返回整数。

**例:1#**

```scala
// Scala program of <<(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <<(x: Int) method 
        val result = 'D'.<<(23)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
570425344

```

**例:2#**

```scala
// Scala program of <<(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying <<(x: Int) method
        val result = 'D'.<<(-23)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
34816

```