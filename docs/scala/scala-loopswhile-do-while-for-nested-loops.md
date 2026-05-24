# Scala | Loops(while，do..而对于嵌套循环)

> 原文:[https://www . geeksforgeeks . org/Scala-loops while-do-while-for-nested-loops/](https://www.geeksforgeeks.org/scala-loopswhile-do-while-for-nested-loops/)

编程语言中的循环是一种功能，当某些条件评估为真时，它有助于重复执行一组指令/函数。循环使程序员的任务更简单。Scala 提供了不同类型的循环来处理程序中基于条件的情况。Scala 中的循环是:

*   [同时循环](https://www.geeksforgeeks.org/while-and-do-while-loop-in-scala/)
*   [做..while Loop](https://www.geeksforgeeks.org/while-and-do-while-loop-in-scala/)
*   回路的
*   嵌套循环

while 循环

while 循环通常在括号中带一个条件。如果条件为**真**，则执行 while 循环体内的代码。当我们不知道希望循环执行的次数，但是我们知道循环的终止条件时，就使用 while 循环。它也被称为*入口控制循环*，因为在执行循环之前会检查条件。while 循环可以看作是一个重复的 if 语句。
**语法:**

```scala
while (condition)
{
    // Code to be executed
}
```

**流程图:**

![](img/8b3cf39fb8baa8287b523ffc17b66d3f.png)

*   While 循环从检查条件开始。如果评估为真，则执行循环体语句，否则执行循环后的第一条语句。因此，它也被称为入口控制回路。
*   一旦条件被评估为真，循环体中的语句就被执行。通常，这些语句包含正在为下一次迭代处理的变量的更新值。
*   当条件变为假时，循环终止，这标志着其生命周期的结束。

**例:**

## 斯卡拉

```scala
// Scala program to illustrate while loop
object whileLoopDemo
{

    // Main method
    def main(args: Array[String])
    {
        var x = 1;

        // Exit when x becomes greater than 4
        while (x <= 4)
        {
            println("Value of x: " + x);

            // Increment the value of x for
            // next iteration
            x = x + 1;
        }
    }
}
```

**输出:**

```scala
Value of x: 1
Value of x: 2
Value of x: 3
Value of x: 4
```

**无限 While 循环:** While 循环可以执行无限次，这意味着该循环没有终止条件。换句话说，我们可以说有些条件总是成立的，这会导致 while 循环执行无限次，或者我们可以说它永远不会终止。
**示例:**下面的程序将无限时间打印指定的语句，并在联机 IDE 上给出运行时错误*kill(SIGKILL)*。

## 斯卡拉

```scala
// Scala program to illustrate Infinite while loop
object infinitewhileLoopDemo
{

    // Main method
    def main(args: Array[String])
    {
        var x = 1;

        // this loop will never terminate
        while (x < 5)
        {
            println("GeeksforGeeks")
        }
    }
}
```

**输出:**

```scala
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
.
.
.
.
```

做..while 循环

做..while 循环与 while 循环几乎相同。唯一不同的是..而循环至少运行一次。第一次执行后检查条件。做..当我们希望循环至少运行一次时，使用 while 循环。也称为**退出受控循环**，因为在执行循环后会检查条件。
**语法:**

```scala
do {

// statements to be Executed

} while(condition);
```

**流程图:**

![](img/3d14b35e4ea67e9888038d7f47bb1148.png)

**例:**

## 斯卡拉

```scala
// Scala program to illustrate do..while loop
object dowhileLoopDemo
{

    // Main method
    def main(args: Array[String])
    {
        var a = 10;

        // using do..while loop
        do
        {
            print(a + " ");
            a = a - 1;
        }while(a > 0);
    }
}
```

**输出:**

```scala
10 9 8 7 6 5 4 3 2 1 
```

用于循环

循环的*功能与 while 循环相似，但语法不同。当循环语句的执行次数事先已知时，for 循环是优选的。“Scala 中的 for 循环”有许多变体，我们将在后续文章中讨论。基本上，它是一个重复控制结构，允许程序员编写一个需要执行特定次数的循环。
**例:*** 

## 斯卡拉

```scala
// Scala program to illustrate for loop
object forloopDemo {

   // Main Method
   def main(args: Array[String]) {

      var y = 0;

      // for loop execution with range
      for(y <- 1 to 7)
      {
         println("Value of y is: " + y);
      }
   }
}
```

**输出:**

```scala
Value of y is: 1
Value of y is: 2
Value of y is: 3
Value of y is: 4
Value of y is: 5
Value of y is: 6
Value of y is: 7
```

嵌套循环

在循环中包含一个循环的循环称为嵌套循环。它可以在 for 循环中包含 for 循环，或者在 while 循环中包含 while 循环。while 循环也可能包含 for 循环，反之亦然。
**例:**

## 斯卡拉

```scala
// Scala program to illustrate nested loop
object nestedLoopDemo {

  // Main Method   
  def main(args: Array[String]) {

    var a = 5;
    var b = 0;

    // outer while loop
    while (a < 7)
    {
       b = 0;

       // inner while loop
       while (b < 7 )
       {

           // printing the values of a and b
          println("Value of a = " +a, " b = "+b);
          b = b + 1;
       }

       // new line
       println()

       // incrementing the value of a
       a = a + 1;

       // displaying the updated value of a
       println("Value of a Become: "+a);

       // new line
       println()
    }

  }
}
```

**输出:**

```scala
(Value of a = 5, b = 0)
(Value of a = 5, b = 1)
(Value of a = 5, b = 2)
(Value of a = 5, b = 3)
(Value of a = 5, b = 4)
(Value of a = 5, b = 5)
(Value of a = 5, b = 6)

Value of a Become: 6

(Value of a = 6, b = 0)
(Value of a = 6, b = 1)
(Value of a = 6, b = 2)
(Value of a = 6, b = 3)
(Value of a = 6, b = 4)
(Value of a = 6, b = 5)
(Value of a = 6, b = 6)

Value of a Become: 7
```