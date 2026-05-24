# Scala 中的隐式参数

> 原文:[https://www.geeksforgeeks.org/implicit-parameters-in-scala/](https://www.geeksforgeeks.org/implicit-parameters-in-scala/)

**隐式参数**是传递给在 [Scala](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/scala-programming-language/&sa=U&ved=2ahUKEwip6bvS6vjpAhXm6XMBHXSSCiEQFjAAegQIAhAB&usg=AOvVaw3Vdi2shkhb_Nl6cW9euC5v) 中带有**隐式**关键字的函数的参数，这意味着这些值将取自调用它们的上下文。简单来说，如果没有值或参数传递给方法或函数，那么编译器将寻找隐式值，并将其作为参数进一步传递。例如，将整数变量更改为字符串变量可以由 Scala 编译器完成，而不是显式调用它。当函数的参数范围中使用**隐式**关键字时，所有参数都被标记为隐式。
**注意:**一个方法只能包含一个隐式关键字。

#### 语法:

> def func1(隐式 x : Int) // x 是隐式的
> def func2(隐式 x : Int，y : Int) // x 和 y 都是隐式的
> def func3 (x : Int)(隐式 y : Int) //只有 y 是隐式的

**例 1:**

## 斯卡拉

```scala
object Main{

    def main(args: Array[String]) 
    {
        val value = 10
        implicit val multiplier = 3
        def multiply(implicit by: Int) = value * by

        // Implicit parameter will be passed here
        val result = multiply 

        // It will print 30 as a result
        println(result) 

    }
}
```

**Output:**

```scala
30
```

**例 2:**

## 斯卡拉

```scala
object Main{

    def main(args: Array[String])
    {
        val message = "hello "
        implicit val name = "world!"
        def disp(implicit nm : String) = message + nm

        // Implicit parameter will be passed here
        val result = disp

        // Implicit parameters will not be passed
        val result2 = disp("GFG!") 
        println("With Implicit parameters:")
        println(result) 
        println("Without Implicit parameters:")
        println(result2)     
    }
}
```

**Output**

```scala
With Implicit parameters:
hello world!
Without Implicit parameters:
hello GFG!

```