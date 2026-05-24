# 使用 Scala 中的映射函数将字符串数组转换为 Int 数组的程序

> 原文:[https://www . geesforgeks . org/program-to-transform-a-array-of-string-to-array-of-int-use-map-function-in-Scala/](https://www.geeksforgeeks.org/program-to-transform-an-array-of-string-to-an-array-of-int-using-map-function-in-scala/)

在 Scala 中，利用*映射*函数，字符串数组可以转换为 Int 数组。这里，所述数组的字符串将由 map 函数调用，该函数中有一个*长度*方法作为参数。那么这个字符串数组将返回一个整数数组，其中这些整数是数组中每个字符串的长度。
现在，让我们看看下面的一些例子，以便详细了解它。
**例:1#**

```scala
// Scala program to transform an array of 
// String to an array of Int using map 
// function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an array
        val x = Array("12", "6", "888")

        // Applying map function and also
        // using toInt method as argument
        val y = x.map(_.toInt)

        // Using for loop
        for(z <-y)

        // Displays output
        println(z) 

    }
}
```

**Output:**

```scala
12
6
888

```

这里，字符串数组被转换成整数数组。重复的元素也会重复。
**例:2#**

```scala
// Scala program to transform an array of 
// String to an array of Int using map 
// function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an array where there
        // are spaces as strings
        val arr = Array("", " ", " ")

        // Applying map function and also
        // using length method as argument
        val m = arr.map(_.length)

        // Using for loop to print the 
        // results
        for(res <-m)

        // Displays output
        println(res) 

    }
}
```

**Output:**

```scala
0
1
2

```

在这里，如果字符串中有一个空格，那么长度被计算为 1，如果没有空格，那么长度为零，如果有两个空格，那么长度为 2，以此类推。