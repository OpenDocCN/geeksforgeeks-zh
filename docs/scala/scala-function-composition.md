# Scala |函数组合

> 原文:[https://www.geeksforgeeks.org/scala-function-composition/](https://www.geeksforgeeks.org/scala-function-composition/)

**功能组合**是一种功能与其他功能混合的方式。在组合过程中，一个函数保存对另一个函数的引用，以便完成它的任务。
函数合成有几种不同的方式，如下所示

*   **compose : Composing method works with **val** functions.
    **Syntax :**

    ```scala
    (function1 compose function2)(parameter)

    ```

    在上面的语法中，函数 2 首先使用传递的参数&然后传递，然后返回一个要传递给函数 1 的值。

    **例 1:**

    ```scala
    // A Scala program to illustrate 
    // compose method with val function

    // Creatin object
    object GFG
    {
        // Main method 
        def main(args: Array[String]) 
        { 
            println((add compose mul)(2))

            // adding more methods
            println((add compose mul compose sub)(2))
        } 

        val add=(a: Int)=> {
            a + 1
        }

        val mul=(a: Int)=> {
            a * 2
        }

        val sub=(a: Int) =>{
            a - 1
        }
    }
    ```

    **输出:**

    ```scala
    5
    3

    ```

    在上面的例子中，首先调用 mul 函数，得到 4(2 * 2)，然后调用 add 函数，得到 5(4 + 1)。类似地(添加复合 mul 复合 sub)(2)将打印 3(步骤 1:2–1 = 1，步骤 2 : 1 * 2 = 2，步骤 3 : 2 + 1 = 3)。** *   ****andThen : andThen method also works with **val** functions.
    **Syntax :**

    ```scala
    (function1 andThen function2)(parameter)

    ```

    在上面的语法中，函数 1 首先使用传递的参数&然后传递，然后返回一个要传递给函数 2 的值。
    或与下图相同:

    ```scala
    function2(function1(parameter))

    ```

    **例 2:**

    ```scala
    // A Scala program to illustrate 
    //andThen method with val function

    // Creating object
    object GFG 
    {
        // Main method 
        def main(args: Array[String]) 
        { 
            println((add andThen mul)(2))

            // Adding more methods
            println((add andThen mul andThen sub)(2))
        } 

        val add=(a: Int)=> {
            a + 1
        }

        val mul=(a: Int)=> {
            a * 2
        }

        val sub=(a: Int) =>{
            a - 1
        }
    } 
    ```

    **输出:**

    ```scala
    6
    5

    ```

    在上面的例子中，首先添加一个被调用的函数，我们得到 3(2 + 1)，然后再添加一个被调用的函数，我们得到 6(3 * 2)。类似地，add(然后 mul 然后 sub)(2))将打印 5(步骤 1 : 2 + 1 = 3，步骤 2 : 3 * 2 = 6，步骤 3:6–1 = 5)。**** *   ******Passing methods to methods : Methods are passed to other methods.
    **Syntax :**

    ```scala
    function1(function2(parameter))

    ```

    它的工作原理与复合函数相同，但是它使用 def 和 val 方法。
    **例 3:**

    ```scala
    // A Scala program to illustrate 
    // passing methods to methods

    // Creating object
    object GFG 
    {
        // Main method 
        def main(args: Array[String]) 
        { 
            println(add(mul(2)))

            // Adding more methods
            println(add(mul(sub(2))))
        } 

        val add=(a: Int)=> {
            a + 1
        }

        val mul=(a: Int)=> {
            a * 2
        }

        val sub=(a: Int) =>{
            a - 1
        }
    } 
    ```

    **输出:**

    ```scala
    5
    3

    ```

    在上面的例子中，首先调用 mul 函数，得到 4(2 * 2)，然后调用 add 函数，得到 5(4 + 1)。类似地，add(mul(sub(2))将打印 3(步骤 1:2–1 = 1，步骤 2 : 1 * 2 = 2，步骤 3 : 2 + 1 = 3)。******