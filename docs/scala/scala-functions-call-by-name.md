# Scala |按名称调用函数

> 原文:[https://www.geeksforgeeks.org/scala-functions-call-by-name/](https://www.geeksforgeeks.org/scala-functions-call-by-name/)

在 **Scala** 中，当参数通过按值调用函数时，它会在调用函数之前计算一次传入表达式或参数的值。但是 Scala 中的一个名为**的函数**会调用该表达式，并在每次函数内部访问时重新计算传入表达式的值。这里用差异和语法展示了一些例子。

### 按值调用

此方法使用模式内语义。对形式参数所做的更改不会传回给调用者。对被调用函数或方法内部的形式参数变量的任何修改只影响单独的存储位置，不会反映在调用环境中的实际参数中。这个方法也被称为按值调用。

**语法:**

```scala
def callByValue(x: Int)
```

```scala
// Scala program of function call-by-value

// Creating object
object GFG 
{
    // Main method
    def main(args: Array[String]) 
    {
        // Defined function
        def ArticleCounts(i: Int) 
        {
            println("Tanya did article " +
                    "on day one is 1 - Total = " + i)
            println("Tanya did article " +
                    "on day two is 1 - Total = " + i)
            println("Tanya did article "+ 
                    "on day three is 1 - Total = " + i)
            println("Tanya did article " +
                    "on day four is 1 - Total = " + i)
        }

        var Total = 0;

        // function call
        ArticleCounts 
        {
            Total += 1 ; Total

        }
    }
}
```

**Output:**

```scala
Tanya did article on day one is 1 - Total = 1
Tanya did article on day two is 1 - Total = 1
Tanya did article on day three is 1 - Total = 1
Tanya did article on day four is 1 - Total = 1

```

这里，通过使用上述程序中的函数**按值调用**机制，文章总数没有增加。

### 点名

按名称调用机制将代码块传递给函数调用，代码块被编译、执行并计算值。将首先打印消息，然后返回值。
**语法:**

```scala
def callByName(x: => Int)
```

**示例:**

```scala
// Scala program of function call-by-name

// Creating object
object main 
{
    // Main method
    def main(args: Array[String])
    {
        // Defined function call-by-name
        def ArticleCounts(i: => Int) 
        {
            println("Tanya did articles " + 
                    " on day one is 1 - Total = " + i)
            println("Tanya did articles "+ 
                    "on day two is 1 - Total = " + i)
            println("Tanya did articles " + 
                    "on day three is 1 - Total = " + i)
            println("Tanya did articles " + 
                    "on day four is 1 - Total = " + i)
        }

        var Total = 0;

        // calling function
        ArticleCounts 
        {
            Total += 1 ; Total
        }
}
}
```

**Output:**

```scala
Tanya did articles  on day one is 1 - Total = 1
Tanya did articles on day two is 1 - Total = 2
Tanya did articles on day three is 1 - Total = 3
Tanya did articles on day four is 1 - Total = 4

```

这里，通过使用上述程序中的函数**名字调用**机制，文章的总计数将增加。
另一个程序的函数调用的名字。

**示例:**

```scala
// Scala program of function call-by-name

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String])
    {
        def something() = 
        {
            println("calling something")
            1 // return value
        }

        // Defined function
        def callByName(x: => Int) = 
        {
            println("x1=" + x)
            println("x2=" + x) 
        }

        // Calling function
        callByName(something)
    }
}
```

**Output:**

```scala
calling something
x1=1
calling something
x2=1

```