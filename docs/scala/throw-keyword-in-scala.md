# 在 Scala 中抛出关键字

> 原文:[https://www.geeksforgeeks.org/throw-keyword-in-scala/](https://www.geeksforgeeks.org/throw-keyword-in-scala/)

Scala 中的 throw 关键字用于从方法或任何代码块中显式抛出异常。在 scala 中，throw 关键字用于显式抛出异常并捕获它。它也可以用来抛出自定义异常。java 和 scala 中的异常处理非常相似。只不过 scala 只将所有类型的异常都视为运行时异常，因此它不会强迫我们处理它们，而是在 catch 块中使用模式匹配。throw 是一个在 scala 中没有结果类型的表达式。如果结果实际上不能评估任何东西，我们可以用它来代替任何其他表达式。
**重要的事情要记住:**

*   抛出表达式的返回类型为“无”。
*   Throw 是用于抛出异常的关键字，而 throw 是用于声明异常的关键字。
*   Catch 块使用模式匹配来处理异常

**语法:**

```scala
 throw exception object
Example:
 throw new ArithmeticException("divide by 0") 

```

**示例:**

> val x =
> if(n % 10 = = 0)
> 5
> else
> 抛出新的 RuntimeException(“n 必须是 10 的倍数”)

**解释:**
如果 n 是 10 的倍数，那么 5 被赋给 x，但是如果 n 不是 10 的倍数，那么在 x 可以被初始化为任何东西之前抛出一个异常。正因为如此，我们可以说投掷具有任何一种价值。在 scala 中，抛出异常和 Java 是一样的。我们创建一个异常对象，然后用 throw 关键字抛出它:

**示例:**

```scala

// Scala program of throw keyword

// Creating object
object Main 
{
    // Define function 
    def validate(article:Int)=
    {  
        // Using throw keyword
        if(article < 20)  
            throw new ArithmeticException("You are not eligible for internship")  
        else println("You are eligible for internship")  
    }  

    // Main method
    def main(args: Array[String])
    {
            validate(22)
    }
}
```

**输出:**

```scala
You are eligible for internship
```

在上面的代码中，如果我们的文章少于 20 篇，我们就没有输出。

当错误发生时，scala 方法可以抛出异常，而不是正常返回。在下面的例子中，我们观察到一个从函数中抛出的异常。

```scala
// Scala program of throw keyword

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String]) 
    {

    try
    {
        func();

    } 
    catch 
    {
        case ex: Exception => println("Exception caught in main: " + ex);

    }
    }

    // Defining function
    def func()
    {
        // Using throw exception
        throw new Exception("Exception thrown from func");

    }
}
```

**输出:**

```scala
Exception caught in main: java.lang.Exception: Exception thrown from func

```