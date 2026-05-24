# 用于 Scala 中的循环

> 原文:[https://www.geeksforgeeks.org/for-loop-in-scala/](https://www.geeksforgeeks.org/for-loop-in-scala/)

在 Scala 中， ***for loop*** 也称为 for-complements。for 循环是一个重复的**控制结构**，它允许我们编写一个执行特定次数的循环。该循环使我们能够在一行中一起执行 n 个步骤。

**语法:**

```scala
for(w <- range){
// Code..
}
```

这里， *w* 是变量， *< -* 运算符被称为生成器，根据名称这个运算符用于从范围中生成单个值，*范围*是保存起始值和结束值的值。这个范围可以用 I 到 j 或者 I 到 j 来表示。

#### 用于循环使用到

在 for 循环中，当我们想要打印从 0 到 n 的值时，我们可以使用 to。或者换句话说，当我们使用 to 和 for 循环时，它包括起始值和结束值，如下图所示，它打印从 0 到 10 的值，而不是像 in to 那样打印从 0 到 9 的值。

**示例:**

## 斯卡拉

```scala
// Scala program to illustrate how to
// create for loop using to
object Main
{
    def main(args: Array[String])
    {
        println("The value of w is:");

        // Here, the for loop starts from 0
        // and ends at 10
        for( w <- 0 to 10)
        {
            println(w);
        }
    }
}
```

**输出:**

```scala
The value of w is:
0
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
```

#### for 循环使用直到

在 for 循环中，我们可以使用直到我们想要打印从 0 到 n-1 的值。或者换句话说，直到 for 循环排除了如下程序所示的结束值，它只打印 0 到 9，而不打印 0 到 10。

**示例:**

## 斯卡拉

```scala
// Scala program to illustrate how to
// create for loop using until
object Main
{
    def main(args: Array[String])
    {
        println("The value of w is:");

        // Here, the for loop starts from 0
        // and ends at 10
        for( w <- 0 until 10)
        {
            println(w);
        }
    }
}
```

**输出:**

```scala
The value of w is:
0
1
2
3
4
5
6
7
8
9
```

#### for 循环中的多个值

我们也可以在单个 for 循环中使用多个范围。这些范围由分号(；).让我们借助一个例子来讨论一下。在下面的例子中，我们使用两个不同的范围到一个循环中，即 w

**示例:**

## 斯卡拉

```scala
// Scala program to illustrate how to
// create multiple ranges in for loop
object Main
{
    def main(args: Array[String])
    {

    // for loop with multiple ranges
        for( w <- 0 to 3; z<- 8 until 10 )
        {
            println("Value of w is :" +w);
            println("Value of y is :" +z);
        }
    }
}
```

**输出:**

```scala
Value of w is :0
Value of y is :8
Value of w is :0
Value of y is :9
Value of w is :1
Value of y is :8
Value of w is :1
Value of y is :9
Value of w is :2
Value of y is :8
Value of w is :2
Value of y is :9
Value of w is :3
Value of y is :8
Value of w is :3
Value of y is :9
```

#### 对集合使用 for 循环

在 Scala 中，我们可以使用 for-loop 和 List 等集合。它提供了一种迭代集合的有效方法。

**语法:**

```scala
for(i <- List){
// Code..
}
```

**示例:**

## 斯卡拉

```scala
// Scala program to illustrate how to
// use for loop with collection
object Main
{
    def main(args: Array[String])
    {
        var rank = 0;
        val ranklist = List(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // For loop with collection
        for( rank <- ranklist){
            println("Author rank is : " +rank);
        }
    }
}
```

**输出:**

```scala
Author rank is : 1
Author rank is : 2
Author rank is : 3
Author rank is : 4
Author rank is : 5
Author rank is : 6
Author rank is : 7
Author rank is : 8
Author rank is : 9
Author rank is : 10
```

#### 使用带过滤器的 for-loop

在 Scala 中，for-loop 允许您使用 for-loop 中的一个或多个 if 语句从给定集合中过滤一些元素。

**语法:**

```scala
for(i<- List 
if condition1; if condition2; if condition3; ...)
{
// code..
}
```

**示例:**

## 斯卡拉

```scala
// Scala program to illustrate how to
// use for loop with filters
object Main
{
    def main(args: Array[String])
    {
        var rank = 0;
        val ranklist = List(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // For loop with filters
        for( rank <- ranklist
        if rank < 7; if rank > 2 )
        {
            println("Author rank is : " +rank);
        }
    }
}
```

**输出:**

```scala
Author rank is : 3
Author rank is : 4
Author rank is : 5
Author rank is : 6
```

**解释:**在上面的例子中，for 循环使用两个过滤器来过滤给定的集合。这些过滤器消除了小于 7 和大于 2 的等级。

#### 使用带产量的 for 循环

在 Scala 中，for 循环的返回值存储在变量中，也可以通过函数返回。为此，您应该使用 yield 关键字作为 for 循环主体的前缀。

**语法:**

```scala
var output = for{ i<- List
if condition 1; if condition 2; 
} 
yield i
```

**示例:**

## 斯卡拉

```scala
// Scala program to illustrate how to
// use for loop with yields
object Main
{
    def main(args: Array[String])
    {
        var rank = 0;
        val ranklist = List(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // For loop with yields
        var output = for{ rank <- ranklist
                    if rank > 4; if rank != 8 }
                    yield rank

        // Display result
        for (rank <- output)
        {
            println("Author rank is : " + rank);
        }
    }
}
```

**输出:**

```scala
Author rank is : 5
Author rank is : 6
Author rank is : 7
Author rank is : 9
Author rank is : 10
```

**说明:**在上面的例子中，输出是一个变量，其中 rank 的所有值都以集合的形式存储。for 循环只显示排名大于 4 且不等于排名 8 的作者的排名。