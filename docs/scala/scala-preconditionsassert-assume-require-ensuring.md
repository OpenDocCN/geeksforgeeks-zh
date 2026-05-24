# Scala |先决条件(断言、假设、要求、确保)

> 原文:[https://www . geesforgeks . org/Scala-preconditionsassert-假定-要求-确保/](https://www.geeksforgeeks.org/scala-preconditionsassert-assume-require-ensuring/)

**先决条件**指的是 [Scala](https://www.geeksforgeeks.org/scala-programming-language/) 中的一些条件，在继续任何代码或程序之前需要满足这些条件。在 Scala 中，**契约式设计(DbC)** 的过程是一个软件设计过程，它赋予 Scala 先决条件以意义和意义。上面的方法是由 Betrand Mayer 给出的，它为一个代码块提供了一些后置条件和前提条件，如果不满足，就会抛出一个异常。

Scala 先决条件是一组主要的函数，程序员在设计软件时必须遵循不同的条件。这些函数在**预定义的 scala** 包中，并且不需要导入任何单独的包。
方法是:

1.  **断言**–对于一般断言
2.  **假设**–陈述一个公理
3.  **要求**–特别检查输入
4.  **确保**–是一个也已涵盖的岗位条件。

*   **Assert**

    Assert 方法要求在执行某个操作时必须满足某个条件。如果满足这个条件，那么代码可以正常工作，否则会抛出异常。在运行时检查异常。assert()方法因此是一种动态检查不变量的方法。上述方法将布尔语句作为参数，并在整个程序中检查是否有任何地方违反了该语句。它抛出异常或断言错误。

    将以下程序视为申请过程中驾照审批的一部分。如果申请人年龄不等于或大于 18 岁，则会产生错误。

    ```scala
    // Code to check the age of the applicant
    val applicant_age = 16

    // assert method calling
    assert(applicant_age>17)
    ```

    如果年龄超过要求的最小值，进程将向前移动，否则，程序将抛出异常，如下所示:

    ```scala
    Exception in thread "main" java.lang.AssertionError: assertion failed
    ```

    在**预定义的标量**中查找相同的代码，会发现类似上面的代码:

    ```scala
    def assert(assertion: Boolean) { 
      if (!assertion) 
        throw new java.lang.AssertionError("assertion failed") 
    } 
    ```

*   **Assume**

    假设静态分析工具将使用方法。它应该限制程序执行时必须检查的条件数量。如果违反了假设条件，检查器会无声地离开路径，不允许程序更深入。假设()方法的语法与前面提到的 assert()相同，唯一的区别是它的执行。

    以下示例讲述了一个程序，该程序在执行时假设申请人的年龄在任何情况下都大于或等于 18 岁。主要代码已被避免，仅包含调用假定()的代码被合并。

    ```scala
    // Code to check the age of the applicant
    license_approval(17)

    // Method to approve the License application
    def license_approval(applicant_age:Int) {

      assume(applicant_age>=18)
    //……………
    //…………
    //…………
    //The main code for checking the other details of the applicant. 
    //……………
    //…………
    //…………
    }
    ```

    假设()方法为静态检查器提供了一个可以依赖的公理。这减轻了检查人员的负担。如果满足假设()参数的布尔条件，程序将深入代码，否则将引发异常:

    ```scala
    Exception in thread "main" java.lang.AssertionError: assumption failed
    ```

    类似的代码可以在 Predef.scala 包中找到:

    ```scala
    def assume(assumption: Boolean) { 
      if (!assumption) 
        throw new java.lang.AssertionError("assumption failed") 
    } 
    ```

    assert()是一种在所有执行路径中声明一个条件或在整个程序中检查一个不变条件的方法，而另一方面，假设()用于减少静态分析器的负载。它在本地开发了一个分而治之的机制，帮助分析人员假设一个条件并检查代码。

*   **Require:**

    这种方法有处理问题的创新模式。如果某个条件不满足，它通常会责怪方法调用方。如果条件满足，程序继续执行，如果不满足，它抛出一个异常。在布尔条件作为参数之后，assert()和假设()的语法与之前相同。require()函数的工作可以用一个例子来说明:
    下面的例子展示了一个将任意奇数翻倍的方法。如果在函数中传递的数字是奇数，它会顺利工作，如果不是，则会引发异常。

    ```scala
    // Code to double the odd numbers
    def double_odd_numbers(number:Int) : Int = {

        require(number%2==1) // Checking if the number is odd using assume method

        number * 2;

    } 
    // Calling function
    double_odd_numbers(13)
    ```

    如果条件不满足，将引发以下异常:

    ```scala
    Exception in thread "main" java.lang.IllegalArgumentException: requirement failed
    ```

    在 Predef.scala 中查找异常代码时，我们遇到了以下代码:

    ```scala
    def require(requirement: Boolean) { 
      if (!requirement) 
        throw new IllegalArgumentException("requirement failed") 
    } 
    ```

*   **Ensure:**

    与其他条件不同，保证是一个**后条件**。这种方法通常与 require()方法一起使用，以制作一个可行的程序。考虑到上面的例子本身，我们可以通过添加一个保证条件来修改代码，该条件要求输入的数字小于某个限制。

    ```scala
    // Code to double the odd numbers
    def double_odd_numbers(number:Int, lmt:Int) : Int = {

        require(number%2==1) // Checking if the number is odd using assume method

        number * 2;

    } ensuring(number * 2 < lmt) // Ensuring that the number produced is less than the limit. 

    // Calling function
    // The method also requires a limit [parameter to be passed. 
    double_odd_numbers(13, 100)
    ```

    因此，assert()方法要求检查器必须证明后面的条件是一个参数，假设()，另一方面，通过假设某个条件成立，帮助检查器减轻负担。而 require()方法指定函数调用方必须遵循的条件。

    如果程序员试图删除由假定()和断言()方法生成的异常，可以使用**-Xdisable-断言**命令来完成。