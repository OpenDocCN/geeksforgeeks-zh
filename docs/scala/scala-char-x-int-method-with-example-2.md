# Scala Char > > > (x: Int)法同例

> 原文:[https://www . geesforgeks . org/Scala-char-x-int-method-with-example-2/](https://www.geeksforgeeks.org/scala-char-x-int-method-with-example-2/)

利用 **> > > (x: Int)** 方法，找到在 Int 类型的自变量列表中指定的位数右移的字符值，新的左位用零填充。

> **方法定义:**def>T3>(x:Int):Int
> 
> **返回类型:**返回整数。

**例:1#**

```scala
// Scala program of >>>(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >>>(x: Int) method 
        val result = 'A'.>>>(1)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
32

```

**例:2#**

```scala
// Scala program of >>>(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying >>>(x: Int) method
        val result = 'A'.>>>(2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
16

```