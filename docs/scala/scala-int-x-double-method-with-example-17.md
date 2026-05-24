# 斯卡拉国际<

> 原文: [https://www .极客们。org/Scala-int-x-double-method-example-17/](https://www.geeksforgeeks.org/scala-int-x-double-method-with-example-17/)

**< < (x: Double)** 方法用于返回一个值，该值是 int 值左移指定的 Double 值的结果。

> **方法定义:** (Int_Value)。< < (Double_Value)
> **返回类型:**返回一个值，该值是 int 值左移指定的 Double 值的结果。

**示例#1:**

```scala
// Scala program of Int <<(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <<(x: Double) function
        val result = (15).<<(2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
60

```

**例 2:**

```scala
// Scala program of Int <<(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int <<(x: Double) function
        val result = (15).<<(3)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
120

```