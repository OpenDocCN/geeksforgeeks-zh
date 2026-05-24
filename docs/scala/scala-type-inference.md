# Scala |类型推断

> 原文:[https://www.geeksforgeeks.org/scala-type-inference/](https://www.geeksforgeeks.org/scala-type-inference/)

Scala 类型推断使指定变量的类型成为可选的，前提是处理类型不匹配。有了类型推断功能，我们可以花更少的时间写出编译器已经知道的东西。Scala 编译器通常可以推断表达式的类型，因此我们不必显式声明它。
我们先来看看 scala 中如何声明不可变变量的语法。

```scala
val variable_name : Scala_data_type = value
```

**示例:**

```scala
// Scala program of type interference
object Geeks 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        // prints a double value
        val a : Double = 7.893
        println(a)  
        println(a.getClass)

    } 
} 
```

**输出:**

```scala
7.893
double

```

在上例中，getClass 方法用于将变量的类型打印到控制台。在上面的例子中，变量“a”的类型是 double。

但是，通过类型推断，Scala 自动检测变量的类型，而无需用户明确指定。
**例:**

```scala
// Scala program of type interference
object Geeks { 

    // Main method 
    def main(args: Array[String]) 
    { 
        // type inference
        println("Scala Data Types")
        val number = 5
        val big_number = 100000000L
        val small_number = 1
        val double_number = 2.50
        val float_number = 2.50f
        val string_of_characters = "This is a string of characters"
        val byte = 0xc
        val character = 'D'
        val empty = ()

        println(number)
        println(big_number)
        println(small_number)
        println(double_number)
        println(float_number)
        println(string_of_characters)
        println(byte)
        println(character)
        println(empty)

    } 
} 
```

**输出:**

```scala
Scala Data Types
5
100000000
1
2.5
2.5
This is a string of characters
12
D
()

```

请注意，没有为上述变量显式指定数据类型。

**函数的 Scala 类型推断**
现在我们来看看 Scala 中函数的类型推断是如何工作的。
我们先来看看函数在 Scala 中是如何声明的。
**语法:**

```scala
 def function_name ([parameter_list]) : [return_type] = {

  // function body

}
```

**示例:**

```scala
// Scala program of multiply two numbers
object Geeks 
{ 

    // Main method 
    def main(args: Array[String])
    { 

        // Calling the function 
        println("Product of the two numbers is: " + Prod(5, 3)); 
    } 

    // declaration and definition of Product function 
    def Prod(x:Int, y:Int) : Int =
    { 
        return x*y 
    } 
} 
```

**输出:**

```scala
Product of the two numbers is: 15

```

在上面的例子中，我们可以从声明中看出，指定的返回类型是 Int。通过 Scala 类型推断，Scala 自动检测函数的类型，而无需用户明确指定。
**例:**

```scala
// Scala program of type interference
object Geeks 
{ 

    def factorial(n: Int)= { 

        var f = 1
        for(i <- 1 to n) 
        { 
            f = f * i; 
        } 

        f 
    } 

    // Driver Code 
    def main(args: Array[String]) 
    { 
        println(factorial(5)) 
    }

}
```

**输出:**

```scala
120

```

```scala
def factorial(n: Int)= 
```

在上例中，省略了冒号和返回类型。

同样，在上面的例子中，我们省略了语句“返回 f”到“f”，因为我们没有指定返回类型。
如果不是“f”，而是“return f”，那么编译器会显示以下错误。

```scala
prog.scala:11: error: method factorial has return statement; needs result type
        return f
        ^

```

这显示了 Scala 类型推断的能力，但是对于递归方法，编译器不能推断结果类型。上面的阶乘函数也可以递归实现。
以下是无类型推断的阶乘函数的递归定义。
**例:**

```scala
// Scala program of using recursion
object Geeks { 

    // factorial function
    def factorial(n: Int): Int =
    { 
        if (n == 0) 
            return 1
        else
            return n * factorial(n-1) 
    } 

    // Driver Code 
    def main(args: Array[String]) 
    { 
        println(factorial(5)) 
    } 

}
```

**输出:**

```scala
120

```

**示例:**带 Scala 类型推理

```scala
// Scala program of type interference
object Geeks 
{ 

    // Defining function with type interfrence
    def factorial(n: Int) =
    { 
        if (n == 0) 
            1
        else
            n * factorial(n-1) 
    } 

    // Driver Code 
    def main(args: Array[String]) 
    { 
        println(factorial(5)) 
    } 

}
```

**输出:**

```scala
Compile Errors :
prog.scala:8: error: recursive method factorial needs result type
            n * factorial(n-1)
                ^

```