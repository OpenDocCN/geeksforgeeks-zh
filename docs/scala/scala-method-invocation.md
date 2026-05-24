# Scala |方法调用

> 原文:[https://www.geeksforgeeks.org/scala-method-invocation/](https://www.geeksforgeeks.org/scala-method-invocation/)

方法调用是一种演示不同语法的技术，在这种技术中，我们用一个对象动态调用一个类的方法。
Scala 的命名约定与 Java 相同，即:-

*   调用对象/目标和点()之间不应有任何空格。)点和方法名之间也没有空格。

    > obj.display(“名字”)//更正
    > obj.display ("name") //不正确但合法
    > 物体.显示("名称")//不正确但合法

*   方法名和括号之间也不应该有任何空格。

    > println(”学生")//正确
    > println("学生")//不正确但合法

*   参数应该用一个空格和一个逗号分隔。

    > obj.display(“姓名”，22) //更正
    > obj.display ("name "，22) //不正确但合法
    > 物体.显示("名称",22) //不正确但合法

让我们看看不同参数和风格的方法。

**Arity-0 :** 当有 0 个参数要传递给方法时。因此，在方法上添加括号并不是强制性的。它会增强代码的可读性，省略括号会在一定程度上减少字符的数量。

```scala
obj.display() //correct
obj.display   //correct

```

**Arity-1 :** 当只有一个参数要传递给 Arity-1 的方法时。这条规则应该用于纯函数式编程或以函数作为参数的方法，那么在传递的参数周围可以避免括号。这种语法也被称为**中缀符号**。
**例:**

```scala
// Scala program for arity 1 
// Creating object
class x
{
    // Defining method
    def display(str: String)= 
    {
        println(str)
    }
}

// Creating object
object GfG 
{ 
    // Main method 
    def main(args: Array[String]) 
    { 
        val obj = new x
        obj.display("student") // correct
        obj display ("student") // correct
        obj display "student" // correct

    } 
} 
```

**输出:**

```scala
student
student
student
```

**[高阶函数:](https://www.geeksforgeeks.org/higher-order-functions-in-scala/)** 一个函数如果包含其他函数作为参数或返回一个函数作为输出，即与另一个函数一起运行的函数称为高阶函数，则该函数称为高阶函数。值得了解的是，高阶函数同样适用于以函数为参数或以函数为结果的函数和方法。这是可行的，因为 Scala 的编译器允许将方法强制转换成函数。
**例:**

```scala
// Scala program of higher order 
// function 

// Creating object 
object GfG 
{ 
    // Main method 
    def main(args: Array[String]) 
    { 

        // Creating a Set of strings 
        val names = Set("sunil","akhil","rakhi") 

        // Defining a method 
        def captainDesignation = (y: String) => "captain " + y

        // Creating a higher order function 
        // that is assigned to the String elements 
        val result = names.map(y => captainDesignation(y)) 

        // Displays output 
        println("Multiplied List is: " + result) 
    } 
} 
```

**输出:**

```scala
Multiplied List is: Set(captain sunil, captain akhil, captain rakhi)

```

#### 要点

*   当没有副作用时，应该遵循这些语法。
*   这些约定用于提高可读性，并使代码更容易理解。
*   忽略一些多余的字符可以节省一些空间。