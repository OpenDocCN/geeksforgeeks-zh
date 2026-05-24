# Scala Stack /:()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-stack-method-with-example-2/](https://www.geeksforgeeks.org/scala-stack-method-with-example-2/)

在 Scala 中，Scala . collection . mutatable 实现了堆栈数据结构。/:方法对起始值和该可遍历或迭代器的所有元素应用二元运算符，从左到右。

> **方法定义–**def/:[B](z:B)(op:(B，A)？乙:乙
> 
> **返回–**在这个可遍历或迭代器的连续元素之间插入运算的结果。
> 
> **示例#1:**
> 
> ```scala
> // Scala program of mutable stack /:() 
> // method 
>   
> // Import Stack 
> import scala.collection.mutable._
>   
> // Creating object 
> object GfG 
> { 
>   
>     // Main method 
>     def main(args:Array[String]) 
>     { 
>           
>           
>         val st1 = Stack(1, 2, 3) 
>           
>           
>         // Applying /:() method 
>         val result1 = (16 /: st1)(_+_)
>         val result2 = (16 /: st1)(_-_)
>               
>         // Display output 
>         print(result1)
>         print("\n")
>         print(result2)
>           
>     } 
> } 
> ```
> 
> **Output:**
> 
> ```scala
> 22
> 10
> 
> ```
> 
> **例 2:**
> 
> ```scala
> // Scala program of mutable stack /:() method 
>   
> // Import Stack 
> import scala.collection.mutable._
>   
> // Creating object 
> object GfG 
> { 
>   
>     // Main method 
>     def main(args:Array[String]) 
>     { 
>         // Creating a stack 
>         val q2 = List(11, 12, 13, 14, 15) 
>           
>         // Applying /:() method 
>         val result = (6 /: q2)(_+_)
>               
>         // Display output 
>         print(result) 
>           
>     } 
> } 
> ```
> 
> **Output:**
> 
> ```scala
> 71
> 
> ```