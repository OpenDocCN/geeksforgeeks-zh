# Scala |字符串插值

> 原文:[https://www.geeksforgeeks.org/scala-string-interpolation/](https://www.geeksforgeeks.org/scala-string-interpolation/)

**字符串插值**是指用相关值替换给定字符串中定义的变量或表达式。字符串插值提供了一种处理字符串文字的简单方法。要应用 Scala 的这一特性，我们必须遵循几条规则:

1.  字符串必须以起始字符定义为 **s** / **f** / **raw** 。
2.  字符串中的变量必须具有“{ content }”；作为前缀。
3.  表达式必须包含在大括号({，})和“{content}”中。作为前缀添加。

**语法:**

```scala
// x and y are defined
val str = s"Sum of $x and $y is ${x+y}"
```

<center>**字符串插值器类型**</center>

1.  **s Interpolator:** Within the String, we can access variables, object fields, functions calls, etc.

    **示例 1:** 变量和表达式:

    ```scala
    // Scala program
    // for s interpolator

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        {

            val x = 20
            val y = 10

            // without s interpolator
            val str1 = "Sum of $x and $y is ${x+y}"

            // with s interpolator
            val str2 = s"Sum of $x and $y is ${x+y}"

            println("str1: "+str1)
            println("str2: "+str2)
        }
    }
    ```

    **输出:**

    ```scala
    str1: Sum of $x and $y is ${x+y}
    str2: Sum of 20 and 10 is 30
    ```

    **示例 2:** 函数调用

    ```scala
    // Scala program
    // for s interpolator

    // Creating object
    object GFG
    { 
        // adding two numbers
        def add(a:Int, b:Int):Int
        =
        { 
            a+b 
        }

        // Main method
        def main(args:Array[String])
        {

            val x = 20
            val y = 10

            // without s interpolator
            val str1 = "Sum of $x and $y is ${add(x, y)}"

            // with s interpolator
            val str2 = s"Sum of $x and $y is ${add(x, y)}"

            println("str1: " + str1)
            println("str2: " + str2)
        }
    }
    ```

    **输出:**

    ```scala
    str1: Sum of $x and $y is ${add(x, y)}
    str2: Sum of 20 and 10 is 30
    ```

2.  **f Interpolator:** This interpolation helps in formatting numbers easily.

    要了解格式说明符是如何工作的，请参考[格式说明符](https://www.geeksforgeeks.org/format-specifiers-in-c/)。

    **示例 1:** 最多打印两位小数:

    ```scala
    // Scala program
    // for f interpolator

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        {

            val x = 20.6

            // without f interpolator
            val str1 = "Value of x is $x%.2f"

            // with f interpolator
            val str2 = f"Value of x is $x%.2f"

            println("str1: " + str1)
            println("str2: " + str2)

        }
    }
    ```

    **输出:**

    ```scala
    str1: Value of x is $x%.2f
    str2: Value of x is 20.60
    ```

    **示例 2:** 设置整数宽度:

    ```scala
    // Scala program
    // for f interpolator

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        {

            val x = 11

            // without f interpolator
            val str1 = "Value of x is $x%04d"

            // with f interpolator
            val str2 = f"Value of x is $x%04d"

            println(str1)
            println(str2)
        }
    }
    ```

    **输出:**

    ```scala
    Value of x is $x%04d
    Value of x is 0011
    ```

    如果在使用 **%d** 说明符进行格式化时，我们试图传递一个**双**值，编译器会输出一个错误。如果 **%f** 说明符，通过 **Int** 是可以接受的。

3.  **raw Interpolator:** String Literal should start with ‘raw’. This interpolator treats escape sequences same as any other character in a String.
    **Example :**printing escape sequence:

    ```scala
    // Scala program
    // for raw interpolator

    // Creating object
    object GFG
    { 
        // Main method
        def main(args:Array[String])
        {

            // without raw interpolator
            val str1 = "Hello\nWorld"

            // with raw interpolator
            val str2 = raw"Hello\nWorld"

            println("str1: " + str1)
            println("str2: " + str2)
        }
    }
    ```

    **输出:**

    ```scala
    str1: Hello
    World
    str2: Hello\nWorld
    ```