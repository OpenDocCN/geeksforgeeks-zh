# Scala |命名参数

> 原文:[https://www.geeksforgeeks.org/scala-named-arguments/](https://www.geeksforgeeks.org/scala-named-arguments/)

在 Scala 中，当参数通过带有命名参数的函数时，我们可以用参数名来标记参数。这些命名参数与函数的命名参数交叉匹配。在正常情况下，未命名参数使用参数位置来调用函数或构造函数，但是这些命名参数允许我们通过简单地交换顺序来改变传递给函数的参数的顺序。
**语法:**

```scala
Function Definition : def createArray(length:int, capacity:int);
Function calling : createArray(capacity=20, length:10);

```

**注意事项–**

> **- >如果有些论点是命名的，有些不是，那么未命名的论点必须排在第一位**
> `function(0, b = "1")`
> 
> **- >订单互换有效**
> `function(b = "1", a = 0)`
> 
> **- >不接受，错误:以命名参数**
> `function(b = "1", 0)`命名位置
> 
> **- >不接受，参数‘a’在第一个位置指定为‘0’两次，再次指定为 a = 1**
> `function(0, a = 1)`

**注意:**如果 x 参数表达式的形式为 **x = expr** 并且 x 不是方法的参数名，则该参数被视为某个变量 x 的赋值表达式。

**示例:**

```scala
// Scala program using Named arguments

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String])
    {
        // passed with named arguments 
        printIntiger(X = 6, Y = 8);
    }

    // Defining a method
    def printIntiger( X:Int, Y:Int ) = 
    {
        println("Value of X : " + X );
        println("Value of Y : " + Y );
    }
}
```

**Output:**

```scala
Value of X : 6
Value of Y : 8

```

在上面的例子中，我们创建了 printIntiger 函数，然后调用了该函数。我们在调用函数时使用函数参数名。我们在这里传递了参数 X = 6，Y = 8**X**和 **Y** 是参数的名称。

**示例:**

```scala
// Scala program using Named arguments

// Creating object
object GFG
{

    // Main method
    def main(args: Array[String]) 
    {     
        // without named arguments 
        printName("geeks","for","geeks");

        // passed arguments according to order
        printName(first = "Geeks", middle="for", 
                                last = "Geeks");

        // passed arguments with different order
        printName(last = "Geeks", first = "Geeks", 
                                    middle="for");
    }

    // Defining function
    def printName( first: String, middle: String, 
                                    last: String ) = 
    {
        println("Ist part of name: " + first )
        println("IInd part of name: " + middle )
        println("IIIrd part of name: " + last )
    }
}
```

**Output:**

```scala
Ist part of name: geeks
IInd part of name: for
IIIrd part of name: geeks
Ist part of name: Geeks
IInd part of name: for
IIIrd part of name: Geeks
Ist part of name: Geeks
IInd part of name: for
IIIrd part of name: Geeks

```

正如我们在上面的例子中看到的，我们创建了 printName 函数，然后我们调用了该函数。这里，我们在调用函数时使用函数参数名。通过改变参数的顺序，比如 print name(last =“Geeks”，first =“Geeks”，middle =“for”)，我们可以得到相同的结果。