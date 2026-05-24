# Scala | yield 关键字

> 原文:[https://www.geeksforgeeks.org/scala-yield-keyword/](https://www.geeksforgeeks.org/scala-yield-keyword/)

**yield** 关键字将在循环迭代完成后返回一个结果。 [for 循环](https://www.geeksforgeeks.org/for-loop-in-scala/)在内部使用缓冲区来存储迭代结果，当完成所有迭代时，它会从该缓冲区产生最终结果。它不像命令式循环那样工作。返回的集合类型与我们倾向于迭代的类型相同，因此一个[地图](https://www.geeksforgeeks.org/scala-map/)产生一个地图，[列表](https://www.geeksforgeeks.org/scala-lists/)产生一个列表，依此类推。

**语法:**

```scala
var result = for{ var x **注意:**花括号用来保存变量和条件，结果是一个变量，只要 x 的所有值都以集合的形式保存。**示例:**

```
// Scala program to illustrate yield keyword

// Creating object
object GFG 
{ 
    // Main method
    def main(args: Array[String]) 
    { 
        // Using yield with for
        var print = for( i <- 1 to 10) yield i 
        for(j<-print)
        { 
            // Printing result
            println(j) 
        } 
    } 
} 
```scala

**输出:**

```
1
2
3
4
5
6
7
8
9
10
```scala

在上例中，与 yield 语句一起使用的 for 循环实际上创建了一个列表序列。**示例:**

```
// Scala program to illustrate yield keyword

// Creating object
object GFG 
{ 
    // Main method
    def main(args: Array[String]) 
    { 
        val a = Array( 8, 3, 1, 6, 4, 5)

        // Using yield with for
        var print=for (e <- a if e > 4) yield e
        for(i<-print)
        { 
            // Printing result
            println(i) 
        } 
    } 
} 
```scala

**输出:**

```
8
6
5
```scala

在上例中，与 yield 语句一起使用的 for 循环实际上创建了一个数组。因为我们说产量 e，它是一个**数组【n1，n2，n3，....】**。 **e 是我们的发电机 **if (e > 4)** 可以是一个守卫，过滤掉那些看起来不大于 4 的数字。- >** 

->
```