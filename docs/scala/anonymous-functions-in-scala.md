# Scala 中的匿名函数

> 原文:[https://www.geeksforgeeks.org/anonymous-functions-in-scala/](https://www.geeksforgeeks.org/anonymous-functions-in-scala/)

在 Scala 中，一个**匿名函数**也被称为函数文字。不包含名称的函数称为匿名函数。匿名函数提供轻量级函数定义。当我们想要创建一个内联函数时，它非常有用。
**语法:**

```scala
(z:Int, y:Int)=> z*y
Or
(_:Int)*(_Int)
```

*   在上面的第一个语法中，= >被称为转换器。转换器用于使用右侧的表达式将符号左侧的参数列表转换为新结果。
*   在上面的第二种语法中，_ character 被称为通配符，是一种表示在匿名函数中只出现一次的参数的简写方式。

**【带参数的匿名函数】**
当一个函数文字在一个对象中被实例化时，被称为函数值。或者换句话说，当一个匿名函数被分配给一个变量时，我们可以像调用函数一样调用这个变量。我们可以在匿名函数中定义多个参数。

**例 1:**

```scala
// Scala program to illustrate the anonymous method
object Main 
{
    def main(args: Array[String]) 
    {

        // Creating anonymous functions
        // with multiple parameters Assign
        // anonymous functions to variables 
        var myfc1 = (str1:String, str2:String) => str1 + str2

        // An anonymous function is created 
        // using _ wildcard instead of 
        // variable name because str1 and
        // str2 variable appear only once 
        var myfc2 = (_:String) + (_:String)

        // Here, the variable invoke like a function call
        println(myfc1("Geeks", "12Geeks"))
        println(myfc2("Geeks", "forGeeks"))
    }
}
```

**输出:**

```scala
Geeks12Geeks
GeeksforGeeks

```

**【无参数匿名函数】**
我们可以定义一个无参数匿名函数。在 Scala 中，我们可以将匿名函数作为参数传递给另一个函数。
**例 2:**

```scala
// Scala program to illustrate anonymous method
object Main 
{
    def main(args: Array[String]) 
    {

        // Creating anonymous functions 
        // without parameter 
        var myfun1 = () => {"Welcome to GeeksforGeeks...!!"}
        println(myfun1())

        // A function which contain anonymous 
        // function as a parameter
        def myfunction(fun:(String, String)=> String) = 
        {
            fun("Dog", "Cat")
        }

        // Explicit type declaration of anonymous
        // function in another function
        val f1 = myfunction((str1: String,
                    str2: String) => str1 + str2)

        // Shorthand declaration using wildcard
        val f2 = myfunction(_ + _)
        println(f1)
        println(f2)
    }
}
```

**输出:**

```scala
Welcome to GeeksforGeeks...!!
DogCat
DogCat

```