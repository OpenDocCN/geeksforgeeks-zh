# Scala |嵌套函数

> 原文:[https://www.geeksforgeeks.org/scala-nested-functions/](https://www.geeksforgeeks.org/scala-nested-functions/)

另一个函数内的函数定义称为**嵌套函数**。不支持 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Java](https://www.geeksforgeeks.org/java/) 等。在其他语言中，我们可以在函数内部调用函数，但它不是嵌套函数。在 Scala 中，我们可以在函数内部定义函数，在其他函数内部定义的函数称为**嵌套函数或局部函数**。
**语法:**

> 定义函数名 1(参数 1，参数 2，..)= {
> def functionname 2()= {
> //代码
> }
> }

**单嵌套函数**
这里有一个单嵌套函数的例子，它以两个数字为参数，返回它们的最大值和最小值。
**例**

## 斯卡拉

```scala
// Scala program of Single Nested Function
object MaxAndMin
{
    // Main method
    def main(args: Array[String])
    {
        println("Min and Max from 5, 7")
                maxAndMin(5, 7);
    }

    // Function
    def maxAndMin(a: Int, b: Int) = {

       // Nested Function
       def maxValue() = {
          if(a > b)
          {
              println("Max is: " + a)
          }
          else
          {
              println("Max is: " + b)
          }
       }

       // Nested Function
       def minValue() = {
          if (a < b)
          {
              println("Min is: " + a)
          }
          else
          {
              println("Min is: " + b)
          }
       }
       maxValue();
       minValue();
    }
}
```

**输出**T2】

```scala
Min and Max from 5, 7
Max is: 7
Min is: 5
```

在上面的代码中，maxAndMin 是一个函数，maxValue 是另一个内部函数，返回 a 和 b 之间的最大值类似地，minValue 是另一个内部函数，也是嵌套函数，该函数返回 a 和 b 之间的最小值
**多重嵌套函数**
下面是多重嵌套函数的一个实现。
**例**

## 斯卡拉

```scala
// Scala program of Multiple Nested Function
object MaxAndMin
{
    // Main method
    def main(args: Array[String])
    {
        fun();
    }

    // Function
    def fun() = {

        geeks();

        // First Nested Function
        def geeks() = {
            println("geeks");

            gfg();

            // Second Nested Function
            def gfg() = {
                println("gfg");

                geeksforgeeks();

                // Third Nested Function
                def geeksforgeeks() = {
                    println("geeksforgeeks");
                }
            }
        }
    }
}
```

**输出**T2】

```scala
geeks
gfg
geeksforgeeks
```

在上面的代码中，fun 是一个函数，geeks、gfg、geeksforgeeks 是嵌套函数或局部函数。