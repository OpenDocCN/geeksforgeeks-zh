# 【varargs 量表

> 哎哎哎:# t0]https://www . geeksforgeeks . org/scale-varargs/

大部分编程语言都为我们提供了 ***变长参数*** 对函数的移动性， **Scala** 也不例外。它允许我们指出函数的最后一个参数是可变长度参数。它可以重复多次。它允许我们指出函数的最后一个参数是可变长度参数，因此它可能会重复多次。我们想通过多少争论就通过多少。这允许程序员将可变长度的参数列表传递给函数。在函数内部，声明的内部参数的类型实际上保存为数组[数据类型]，例如可以声明为类型**字符串*** 实际上是*数组[字符串]* 。
**注:-** 我们在最后一个参数上放置*使其可变长。
**语法:–**

```scala

def Nameoffunction(args: Int *) : Int = { s foreach println. }

```

以下是 varargs 的一些限制:

*   列表中的最后一个参数必须是重复参数。
    `def sum(a :Int, b :Int, args: Int *)`

*   包含 varargs 的方法中的任何参数都没有默认值。*   所有值必须是相同的数据类型，否则会出错。
    `> sum(5, 3, 1000, 2000, 3000, "one")
    > error: type mismatch;
    found : String("one")
    required: Int` *   Inside the body args is an array, so all values are packed into an array

    **示例:**

    ```scala
    // Scala program of varargs
    object GFG 
    { 

        // Driver code
        def main(args: Array[String])
        { 

            // Calling the function 
            println("Sum is: " + sum(5, 3, 1000, 2000, 3000)); 
        } 

        // declaration and definition of function 
        def sum(a :Int, b :Int, args: Int *) : Int =
        {
            var result = a + b

            for(arg <- args)
            {
                result += arg
            }

            return result
        }
    } 
    ```

    **输出:**

    ```scala
    Sum is: 6008
    ```

    在上面的例子中，我们可以看到函数的最后一个参数是一个可变长度的参数。这里 1000 是可变长度参数。参数 **arg** 被添加到**结果**变量中。名称参数是类型**整数**。
    **例:**

    ```scala
    // Scala program of varargs
    object GFG
    { 
        // Driver code
        def main(args: Array[String]) 
        {

            // calling of function     
            printGeek("Geeks", "for", "geeks")

        }

        // declaration and definition of function
        def printGeek(strings: String*) 
        {
            strings.map(println)
        }

    } 
    ```

    **输出:**

    ```scala
    Geeks
    for
    geeks

    ```

    在上面的例子中，我们已经使用 ***** 语法定义了它，所以它是一个变量参数。名称参数的类型是**字符串**。