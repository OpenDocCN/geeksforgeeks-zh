# 在 Scala 中使用匿名函数和映射方法

> 原文:[https://www . geeksforgeeks . org/使用-匿名-函数-带有-map-in-method-Scala/](https://www.geeksforgeeks.org/using-anonymous-functions-with-the-map-method-in-scala/)

在 Scala 中，可以使用*匿名函数*配合 map 方法。这里我们将讨论多行匿名函数在 map 中的用法。因此，当你看到你的算法变得冗长时，你可以先定义方法，然后将其传递到地图中，或者与*地图*函数一起使用，而不是使用匿名函数。
现在，让我们讨论下面的一些例子。
**例:1#**

```scala
// Scala program of Using anonymous 
// functions with the map method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Defining anonymous function 
        def addTwo(a: Char): Char = (a.toByte + 2).toChar

        // Utilizing anonymous function
        // with map method
        val res= "Geeks".map(addTwo)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
Iggmu

```

在这个例子中，方法*添加两个*有一个类型为 Char 的参数，因为字符串是字符的集合，当我们用所述字符串上的映射函数调用这个*添加两个*方法时，这个映射将一次对一个 Char 起作用。
**例:2#**

```scala
// Scala program of Using anonymous 
// functions with the map method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list of numbers 
        val list= List(1, 3, 4) 

        // Defining an anonymous function
        // multiplyTwo
        def multiplyTwo(i: Int): Int = (i*2).toInt

        // Utilizing anonymous function
        // with map method on a list of
        // integers
        val op = list.map(multiplyTwo)

        // Displays output
        println(op)

    }
}
```

**Output:**

```scala
List(2, 6, 8)

```

这与上面的例子相同，但是这里我们定义了一个匿名的乘法函数，它将列表中的所有整数与指定的整数相乘。