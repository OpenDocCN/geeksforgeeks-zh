# Scala | 函数–基础知识

> 原文: [https://www.geeksforgeeks.org/scala-functions-basics/](https://www.geeksforgeeks.org/scala-functions-basics/)

函数是执行特定任务的语句的集合。人们可以将代码分成独立的函数，记住每个函数必须执行特定的任务。函数用于将一些常见且重复的任务放入单个函数中，因此我们可以简单地调用函数，而不是针对不同的输入反复编写相同的代码。Scala 被认为是函数式编程语言，所以它们扮演着重要的角色。这样更容易调试和修改代码。Scala 函数是`一级值`。

## Scala 函数之间的区别 & 方法
函数是一个可以存储在变量中的对象。但是一个方法总是属于一个有名字、签名字节码等的类。基本上，你可以说一个方法是一个函数，它是某个对象的成员。

### 函数声明和定义
一般来说，函数声明和定义有 6 个组成部分:

*   `def`关键字：在 *Scala* 中用于声明函数。
*   函数名：应该是一个有效的小写驼峰式名称。Scala 中的函数名可以包含诸如 `+`, `~`, `&`, `-`, `++`, `\`, `/` 等字符。
*   参数列表：在 Scala 中，输入参数的逗号分隔列表在括号内定义，后面跟着它们的数据类型。
*   返回类型：定义函数时，用户必须提及参数的返回类型，而函数的返回类型是可选的。如果未指定函数的返回类型，则默认返回类型是`unit`，它等价于 Java 中的 `void`。
*   `=`：在 Scala 中，用户可以创建带或不带 `=`（等号）运算符的函数。如果用户使用它，函数将返回所需的值。如果他不使用它，函数将不会返回任何值，并将像子程序一样工作。
*   函数体：函数体包含在花括号 `{}` 中。执行代码以执行预期的操作。

**语法：**

```scala
def function_name ([parameter_list]) : [return_type] = {

// function body

}
```

**注意：** 如果用户不使用等号和函数体，则隐式方法被声明为*抽象*。

### 函数调用
Scala 中调用函数主要有两种方式。第一种方式是标准方式如下：

```scala
function_name(paramter_list)
```

第二种方式，用户也可以在实例和点标记的帮助下调用函数，如下所示：

```scala
[instance].function_name(paramter_list)
```

**例：**

```scala
object GeeksforGeeks {

  def main(args: Array[String]) {

    // Calling the function
    println("Sum is: " + functionToAdd(5,3));
  }

  // declaration and definition of function
  def functionToAdd(a:Int, b:Int) : Int = 
  {
    var sum:Int = 0
    sum = a + b

    // returning the value of sum
    return sum
  }
}
```

**输出：**

```scala
Sum is: 8
```