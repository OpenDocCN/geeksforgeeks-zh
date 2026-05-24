# Scala 中的方法重载

> 原文:[https://www.geeksforgeeks.org/method-overloading-in-scala/](https://www.geeksforgeeks.org/method-overloading-in-scala/)

方法重载是实现**多态性的常用方式。它是以多种形式重新定义函数的能力。用户可以通过在一个共享相同名称的类中定义两个或多个函数来实现函数重载。Scala 可以区分不同方法签名的方法。即这些方法可以具有相同的名称，但是在同一类中具有不同的参数列表(即参数的数量、参数的顺序和参数的数据类型)。**

*   **重载方法根据作为参数传递给方法的参数的数量和类型进行区分。**
*   **我们不能用相同的名称、顺序和参数类型定义多个方法。这将是一个编译器错误。**
*   **编译器在区分重载方法时不考虑返回类型。但是不能用相同的签名和不同的返回类型声明两个方法。它将引发编译时错误。**

#### **为什么我们需要方法重载？？**

**如果我们需要以不同的方式进行相同的操作，即针对不同的输入。在下面描述的例子中，我们对不同的输入进行加法运算。很难为一个动作找到许多不同的有意义的名字。**

#### **重载方法的不同方式**

**方法重载可以通过更改:**

*   **两种方法中的参数数量。**
*   **方法参数的数据类型。**
*   **方法参数的顺序。**

#### **通过改变参数的数量。**

****示例:****

```scala
// Scala program to demonstrate the function 
// overloading by changing the number 
// of parameters 
class GFG
{

    // function 1 with two parameters
    def fun(p:Int, q:Int)
    {
        var Sum = p + q;
        println("Sum in function 1 is:" + Sum);
    }

    // function 2 with three parameters
    def fun(p:Int, q:Int, r:Int)
    {
        var Sum = p + q + r;
        println("Sum in function 2 is:" + Sum);
    }
}
object Main 
{
    // Main function
    def main(args: Array[String]) 
    {

    // Creating object of GFG class
    var obj = new GFG();
    obj.fun(6, 8);
    obj.fun(5, 10, 58);
    }
}
```

****输出:****

```scala
Sum in function 1 is:14
Sum in function 2 is:73 
```

#### **通过更改参数的数据类型**

****示例:****

```scala
// Scala program to demonstrate the function 
// overloading by changing the data types 
// of the parameters 
class GFG
{

    // Adding three integer elements
    def fun(p:Int, q:Int, r:Int)
    {
        var Sum = p + q + r;
        println("Sum in function 1 is:"+Sum);
    }

    // Adding three double elements
    def fun(p:Double, q:Double, r:Double)
    {
        var Sum = p + q + r;
        println("Sum in function 2 is:"+Sum);
    }
}
object Main 
{
    // Main method
    def main(args: Array[String]) 
    {

    // Creating object of GFG class
    var obj = new GFG();
    obj.fun(6, 8, 10);
    obj.fun(5.9, 10.01, 58.7);
    }
}
```

****输出:****

```scala
Sum in function 1 is:24
Sum in function 2 is:74.61 
```

#### **通过改变参数的顺序**

****示例:****

```scala
// Scala program to demonstrate the function 
// overloading by changing the 
// order of the parameters 
class GFG
{

    // Function 1
    def fun(name:String, No:Int)
    {
        println("Name of the watch company is:" + name);
        println("Total number of watch :" + No);
    }

    // Function 2
    def fun(No:Int, name:String )
    {
        println("Name of the watch company is:" + name);
        println("Total number of watch :" + No);
    }
}
object Main 
{
    // Main Function
    def main(args: Array[String])
    {

    // Creating object of GFG class
    var obj = new GFG();
    obj.fun("Rolex", 10);
    obj.fun("Omega", 10);
    }
}
```

****输出:****

```scala
Name of the watch company is:Rolex
Total number of watch :10
Name of the watch company is:Omega
Total number of watch :10 
```

#### **当方法签名相同而返回类型不同时会发生什么？**

**编译器会给出错误，因为仅返回值不足以让编译器找出它必须调用哪个函数。只有当两个方法具有不同的参数类型时(因此，它们具有不同的签名)，方法重载才是可能的。
**例:****

```scala
// Example to show error when method signature is same  
// and return type is different. 
object Main {

        // Main method
        def main(args: Array[String]) {
     println("Sum in function 1 is:" + fun(6, 8) );
     println("Sum in function 2 is:" + fun(6, 8) );
    }

     // function 1 
    def fun(p:Int, q:Int) : Int = {
        var Sum: Int = p + q;
        return Sum;

    }

 // function 2 
    def fun(p:Int, q:Int) : Double = {
        var Sum: Double = p + q + 3.7;
        return Sum;
    }

}
```

****编译时错误:****

> **prog.scala:10:错误:对重载定义的引用不明确，
> 类型的 object Main 中的方法 fun(p:Int，q: Int)Double
> 和类型的 object Main 中的方法 fun(p:Int，q: Int)Int
> 都匹配参数类型(Int，Int)和预期结果类型 Any
> println(“函数 1 中的 Sum 为:“+ fun(6，8))；
> ^
> prog.scala:11:错误:对重载定义的引用不明确，
> 类型的 object Main 中的方法 fun(p:Int，q: Int)Double
> 和类型的 object Main 中的方法 fun(p:Int，q: Int)Int
> 都匹配参数类型(int，int)和预期结果类型 Any
> println(“函数 2 中的 Sum 为:“+ fun(6，8))；
> ^
> prog.scala:22:错误:方法 fun 被定义了两次
> 冲突符号都起源于文件“Prog . Scala”
> def fun(p:int，q:Int) : Double = {
> ^
> 发现三个错误**