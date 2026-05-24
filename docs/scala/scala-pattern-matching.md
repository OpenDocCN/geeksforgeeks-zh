# Scala |模式匹配

> 原文:[https://www.geeksforgeeks.org/scala-pattern-matching/](https://www.geeksforgeeks.org/scala-pattern-matching/)

模式匹配是一种检查给定的令牌序列是否存在特定模式的方法。这是 Scala 中使用最广泛的特性。这是一种根据模式检查值的技术。类似于 Java*[C](https://www.geeksforgeeks.org/switch-statement-cc/)*的 *[开关语句。](https://www.geeksforgeeks.org/switch-statement-in-java/)*

这里用“ **match** ”关键字代替 switch 语句。“match”总是在 Scala 的根类中定义，以使其对所有对象都可用。这可以包含一系列备选方案。每个备选方案都将从**案例**关键词开始。每个 case 语句包括一个模式和一个或多个表达式，如果指定的模式匹配，这些表达式将被求值。为了将模式与表达式分开，使用了**箭头符号(= > )** 。

**例 1:**

```scala
// Scala program to illustrate 
// the pattern matching

object GeeksforGeeks {

      // main method
      def main(args: Array[String]) {

      // calling test method
      println(test(1));
      }

   // method containing match keyword
   def test(x:Int): String = x match {

       // if value of x is 0,
       // this case will be executed
       case 0 => "Hello, Geeks!!"

       // if value of x is 1, 
       // this case will be executed
       case 1 => "Are you learning Scala?"

       // if x doesnt match any sequence,
       // then this case will be executed
       case _ => "Good Luck!!"
   }
}
```

**输出:**

```scala
Are you learning Scala?

```

**说明:**在上面的程序中，如果在*测试*方法调用中通过的 x 的值与任何一种情况匹配，则计算该情况下的表达式。这里我们通过 1 所以*案例 1* 将被评估。case_ = >是默认情况，如果 x 的值不是 0 或 1，将会执行。

**例 2:**

```scala
// Scala program to illustrate 
// the pattern matching

object GeeksforGeeks {

      // main method
      def main(args: Array[String]) {

      // calling test method
      println(test("Geeks"));
      }

   // method containing match keyword
   def test(x:String): String = x match {

       // if value of x is "G1",
       // this case will be executed
       case "G1" => "GFG"

       // if value of x is "G2", 
       // this case will be executed
       case "G2" => "Scala Tutorials"

       // if x doesnt match any sequence,
       // then this case will be executed
       case _ => "Default Case Executed"
   }
}
```

**输出:**

```scala
Default Case Executed

```

**要点:**

*   每个匹配关键字必须至少有一个 case 子句。
*   最后一个“ **_** ”，是一个“**通吃**”的案件，如果两个案件都不匹配就会被执行。案例也被称为*替代品*。
*   模式匹配没有任何 break 语句。
*   模式匹配总是会返回一些值。
*   匹配块是表达式，不是语句。这意味着他们会评估匹配的案例的主体。这是函数式编程的一个非常重要的特征。
*   模式匹配也可以用于赋值和理解，不仅仅是在匹配块中。
*   模式匹配允许用第一匹配策略匹配任何类型的数据。
*   每个 case 语句都返回一个值，整个 match 语句实际上是一个返回匹配值的函数。
*   使用“ **|** ”可以在一行测试多个值。