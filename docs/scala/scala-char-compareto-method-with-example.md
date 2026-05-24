# Scala Char compareTo()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-compare to-method-with-example/](https://www.geeksforgeeks.org/scala-char-compareto-method-with-example/)

**compareTo()** 方法用于将所述字符值与参数列表中的值进行比较。与比较法相同。

> **方法定义:**定义比较(arg0:字符):Int
> 
> **返回类型:**返回 Int。其中，如果所述字符值大于“x”，则返回正整数，如果小于“x”，则返回负整数，如果等于“x”，则返回零。

**例:1#**

```scala
// Scala program of compareTo()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying compareTo() method 
        val result = 'a'.compareTo('A')

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
// Scala program of compareTo()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying compareTo() method
        val result = 'B'.compareTo('B')

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```