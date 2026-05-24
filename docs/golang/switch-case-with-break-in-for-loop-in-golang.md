# 在 Golang

带插入式 for Loop 的开关柜

> Original: [https://www.geeksforgeeks.org/switch-case-with-break-in-for-loop-in-golang/](https://www.geeksforgeeks.org/switch-case-with-break-in-for-loop-in-golang/)

[Switch 语句](https://www.geeksforgeeks.org/switch-statement-in-go/)是多路分支语句。 它提供了一种基于值(也称为表达式的情况)将执行转移到代码的不同部分的有效方法。 一个交换机中可以有各种 Switch-Case 语句。 每种情况后面都有要比较的值。 当打开的变量等于其对应的 CASE 时，该 CASE 后面的语句将一直执行，直到到达 BREAK 语句。

当到达 Break 语句时，开关终止，控制流跳转到 Switch 语句后面的下一行，并且不执行相同情况或循环中的其他后续命令。 Switch 语句最后还可以有一个可选的缺省条件，以给出要执行的缺省条件。 当所有情况都不为真时，默认情况可用于执行任务。 让我们举个例子来理解一下：

**代码：**

开始

```go
// Golang Program to show the Switch 
// Case with Break in For Loop
package main 
import "fmt"

func main() {

    forLoop:for number := 1; number < 10; number++ {
        fmt.Printf("%d", number)
        switch {
        case number == 1:
            fmt.Println("-- One")
        case number == 2:
            fmt.Println("-- Two")
        case number == 3:
            fmt.Println("-- Three")
        case number == 4:
            fmt.Println("-- Four")
         case number == 5:
            fmt.Println("-- Five")
        case number == 6:
            fmt.Println("-- Six")
        case number > 2:
            fmt.Println("-- Greater than two")
            break forLoop
        case number == 8:
            fmt.Println("-- Eight")
        case number == 9:
            fmt.Println("-- Nine")
        default:
            fmt.Println("-- Number not identified")
        }
    }
}
```

发帖主题：Re：Колибри0.7.8.0

**解释：**在默认用例之前的最后一个用例中，我们使用了 Break 语句，该语句用于中断*forLoop***。** 当数字在循环中从 1 迭代到 9 时，它们将通过从顶部开始的开关箱进行有条件的测试。 例如，当 number=1 时，它将打印一个，依此类推。 只有在第一个开关箱条件不满足后，程序才检查下一个开关箱条件。 数字加 1，一旦循环遇到 7，第一个匹配的开关情况条件就是“**数字>2**”。

在这种情况下，我们已经应用了 Break 语句，只要 forLoop 遇到该语句，它就会从循环中断，而不执行后面的命令。 如图所示，数字 8 从未打印过，这是因为循环前面有一条 Break 语句。 我们看到，虽然数字仍然是**9**，而且也有条件，但是它们不会被执行，因为循环遇到它前面的 Break 语句，因此，它后面的语句不能执行。

**注意：**Break 语句非常重要，因为如果您不应用它，编译器将抛出错误“*Label for Loop Defined and Not Used”*，即使数字在 10 之后停止递增，程序也不会作为一个整体执行。因此，请记住小心使用 Break 语句。