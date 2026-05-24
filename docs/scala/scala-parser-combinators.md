# Scala 解析器组合器

> 原文:[https://www.geeksforgeeks.org/scala-parser-combinators/](https://www.geeksforgeeks.org/scala-parser-combinators/)

当需要一个解析器生成器时，我们脑海中闪过的一些著名的解析器是:用 C 语言编写的解析器的 *Yacc* 和 *Bison* 以及用 Java 编写的解析器的 ANTLR，但是它们是为特定的编程语言而设计的。这缩短了解析器的使用范围。然而，Scala 提供了一个独特而有用的选择。可以使用内部域特定语言(简称内部 DSL)，而不是使用解析器生成器的独立域特定语言。内部 DSL 将由一个解析器组合器库组成 Scala 中定义的函数和运算符，将作为解析器的构建块。

为了理解这些内容，一个人必须具备编译器的基本知识，并且必须理解正则语言和上下文无关语言。

*   [常规语法](https://www.geeksforgeeks.org/regular-expressions-regular-grammar-and-regular-languages/)
*   [上下文无关语法](https://www.geeksforgeeks.org/classification-of-context-free-grammars/)

第一步总是为要解析的语言写下语法。
**表达式:**每个表达式(用 expr 表示)都是一个术语，后面可以跟一系列的‘+’或‘-’运算符以及其他术语。
**术语:**术语是一个因素，后面可能是一系列“*”或“/”运算符以及其他因素。
**因子:**因子可以是数字文字，也可以是括号中的表达式。

算术表达式解析器示例:

```scala
expr ::= term {"+" term | "-" term}. 
term ::= factor {"*" factor | "/" factor}. 
factor ::= ?FloatingPointNumber | "(" expr ")".

```

|表示替代作品
{ … }表示重复(零次或更多次)

上例的 Scala 代码:

```scala
import scala.util.parsing.combinator._
class Arith extends JavaTokenParsers 
{ 
    def expr: Parser[Any] = term~rep("+"~term | "-"~term) 
    def term: Parser[Any] = factor~rep("*"~factor | "/"~factor) 
    def factor: Parser[Any] = floatingPointNumber | "("~expr~")" 
}
```

算术表达式的解析器包含在一个继承了 JavaTokenParsers 特性的类中。

将上下文无关语法转换为代码的步骤:

1.  每个产品都变成一个方法，因此添加前缀“def”。
2.  每个方法的结果类型都是 Parser[Any]，所以我们需要将::=符号改为:”Parser[Any] =”。
3.  在语法中，顺序组合是隐式的，但在程序中，它是由显式运算符来表示的:~。所以我们需要在一个作品的每两个连续符号之间插入一个“~”。
4.  重复用 rep( …)代替{ … }。
5.  句号(。)在每个产品的末尾被省略，但是可以使用分号(；)也是。

**用下面的代码测试你的解析器是否工作！**

```scala
object ParseExpr extends Arith 
{ 
    def main(args: Array[String]) 
    { 
        println("input : "+ args(0)) 
        println(parseAll(expr, args(0))) 
    } 
}
```

ParseExpr 对象定义了一个主方法，用于解析传递给它的第一个命令行参数。解析由表达式完成:parseAll(表达式，输入)

我们可以使用以下命令运行算术解析器:

```scala
$ scala ParseExpr "4 * (5 + 7)" 
input: 4 * (5 + 7) 
[1.12] parsed: ((4~List((*~(((~((5~List())~List((+ ~(7~List())))))~)))))~List())

```

输出告诉我们，解析器成功地分析了位置为[1.12]的输入字符串。这意味着第一行和第十二列，或者我们可以说整个输入字符串被解析。

我们还可以检查解析器是否处理错误的输入，并给出错误与否。
**例:**

```scala
$ scala ParseExpr "2 * (3 + 7))" 
input: 2 * (3 + 7)) 
[1.12] failure: `-' expected but `)' found
2 * (3 + 7))            ˆ 

```

expr 解析器解析除最后的右括号之外的所有内容，右括号不构成算术表达式的一部分。“parseAll”方法随后发出一条错误消息，称它在右括号处需要一个运算符。