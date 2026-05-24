# Scala Char 比较()方法与示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-compare-method-with-example/](https://www.geeksforgeeks.org/scala-char-compare-method-with-example/)

**compare()** 方法用于将所述字符值与参数列表中的值进行比较。

> **方法定义:**定义比较(y: Char): Int
> 
> **返回类型:**返回 Int。其中，如果所述字符值大于“x”，则返回正整数，如果小于“x”，则返回负整数，如果等于“x”，则返回零。

**例:1#**

```scala
// Scala program of compare()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying compare() method 
        val result = 'a'.compare('A')

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
// Scala program of compare()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying compare() method
        val result = 'B'.compare('B')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```