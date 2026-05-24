# Scala Char > > (x: Long)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-x-long-method-with-example-5/](https://www.geeksforgeeks.org/scala-char-x-long-method-with-example-5/)

利用 **> > (x: Long)** 方法，找到在 Long 类型的自变量列表中指定的位数右移的字符值，新的左位填充与给定字符值的最左边位相同的值。

> **方法定义:** def > > (x: Long): Int
> 
> **返回类型:**返回整数。

**例:1#**

```scala
// Scala program of >>(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

            // Applying >>(x: Long) method 
            val result = 'B'.>>(100000L)

            // Displays output
            println(result)

    }
} 
```

**Output:**

```scala
0

```

**例:2#**

```scala
// Scala program of >>(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >>(x: Long) method
        val result = 'D'.>>(-100000L)

        // Displays output
        println(result)

    }
}   
```

**Output:**

```scala
0

```