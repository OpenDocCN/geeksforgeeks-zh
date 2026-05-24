# 标量中的 Currying 函数示例

> 原文:[https://www . geeksforgeeks . org/currying-functions-in-Scala-with-examples/](https://www.geeksforgeeks.org/currying-functions-in-scala-with-examples/)

**Scala 中的 Currying** 简单来说就是一种转换函数的技术或者过程。该函数将*多个参数*转换为一个接受单个参数的函数。它广泛应用于多种功能语言中。

**语法**

```scala
def function name(argument1, argument2) = operation
```

让我们用一个简单的例子来理解，
**例子:**

```scala
// Scala program add two numbers
// using currying Function
object Curry
{
    // Define currying function
    def add(x: Int, y: Int) = x + y;

    def main(args: Array[String])
    {
        println(add(20, 19));
    }
}
```

**输出:**

```scala
39
```

在这里，我们定义了 **add** 函数，该函数接受两个参数(x 和 y)，该函数简单地将 x 和 y 相加并给出结果，在主函数中调用它。

**声明 currying 函数的另一种方式**
假设，我们必须将这个 add 函数转换为 Curried 函数，也就是*将接受两个(多个)参数的函数*转换为接受一个(单个)参数的函数。

**语法**

```scala
def function name(argument1) = (argument2) => operation
```

**例**

```scala
// Scala program add two numbers
// using Currying function

object Curry
{
    // transforming the function that 
    // takes two(multiple) arguments into 
    // a function that takes one(single) argument.
    def add2(a: Int) = (b: Int) => a + b;

    // Main method
    def main(args: Array[String])
    {
        println(add2(20)(19));
    }
}
```

**输出:**

```scala
39
```

这里，我们定义了 add2 函数，它只接受一个参数 **a** ，我们将返回第二个函数，其值为 add2。第二个函数也会接受一个参数，比如说 **b** ，这个函数在 main 中被调用时，会接受两个括号(add2()())，其中第一个括号属于函数 add2，第二个括号属于第二个函数。它将返回两个数字的相加，即 **a+b** 。因此，我们修改了 add 函数，这意味着我们将接受两个参数的函数转换为接受一个参数的函数，并且函数本身返回结果。

<center>**使用部分应用的 curry Function**</center>

我们有另一种方法来使用这个 Curried function，那就是**部分应用的 function** 。所以，让我们举一个简单的例子来理解。我们在主函数中定义了一个变量和

**例**

```scala
// Scala program add two numbers
// using Currying function
object Curry
{
    def add2(a: Int) = (b: Int) => a + b;

    // Main function
    def main(args: Array[String])
    {
        // Partially Applied function.
        val sum = add2(29);
        println(sum(5));
    }
}
```

**输出:**

```scala
34
```

在这里，将函数赋值时只传递一个参数。第二个参数与值一起传递，这些参数相加并打印结果。

此外，还有另一种方式(语法)来编写 currying 函数。

**语法**

```scala
def function name(argument1) (argument2) = operation
```

**例**

```scala
// Scala program add two numbers
// using Currying function
object Curry
{
    // Curring function declaration
    def add2(a: Int) (b: Int) = a + b;

    def main(args: Array[String])
    {
        println(add2(29)(5));
    }
}
```

**输出:**

```scala
34
```

对于这种语法，部分应用程序函数也会改变。
**例**

```scala
// Scala program add two numbers
// using Currying function
object Curry
{
    // Curring function declaration
    def add2(a: Int) (b: Int) = a + b;

    def main(args: Array[String])
    {
       // Partially Applied function.
        val sum=add2(29)_;
        println(sum(5));
    }
}
```

**输出:**

```scala
34
```

这里，在调用函数 add2 求和值后，只增加了 **'_'** 。