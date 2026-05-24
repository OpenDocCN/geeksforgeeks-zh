# Scala Char > > (x: Int)方法示例

> 原文:[https://www . geesforgeks . org/Scala-char-x-int-method-with-example-4/](https://www.geeksforgeeks.org/scala-char-x-int-method-with-example-4/)

利用 **> > (x: Int)** 方法找到在 Int 类型的自变量列表中指定的位数右移的字符值，新的左位填充与给定字符值的最左边位相同的值。

> **方法定义:** def > > (x: Int): Int
> 
> **返回类型:**返回整数。

**例:1#**

```scala
// Scala program of >>(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >>(x: Int) method 
        val result = 'D'.>>(1)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
34

```

**例:2#**

```scala
// Scala program of >>(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >>(x: Int) method
        val result = 'D'.>>(2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
17

```