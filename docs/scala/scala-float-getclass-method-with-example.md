# Scala Float getClass()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-get class-method-with-example/](https://www.geeksforgeeks.org/scala-float-getclass-method-with-example/)

利用 **getClass()** 方法返回给定编号的类。

> **方法定义:**(数字)。getClass
> 
> **返回类型:**返回给定数字的类。

**示例#1:**

```scala
// Scala program of Float getClass()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying getClass method
        val result = (2).getClass

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
int

```

**例 2:**

```scala
// Scala program of Float getClass()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying getClass method
        val result = (2.6).getClass

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
double

```