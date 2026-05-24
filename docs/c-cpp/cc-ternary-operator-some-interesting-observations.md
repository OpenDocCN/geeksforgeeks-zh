# C/C++ 三元运算符–一些有趣的观察

> 原文:[https://www . geesforgeks . org/cc-三元-运算符-某些-有趣-观察/](https://www.geeksforgeeks.org/cc-ternary-operator-some-interesting-observations/)

预测后续 C++ 程序的输出。

```cpp
#include <iostream>
using namespace std;

int main()
{
   int test = 0;
   cout << "First  character " << '1' << endl;
   cout << "Second character " << (test ? 3 : '1') << endl;

   return 0;
}
```

人们会期望两个打印语句的输出是相同的。但是，输出将是，

```cpp
First  character 1
Second character 49
```

为什么第二次报表打印 49？阅读三元表达式。

**三元运算符(C/C++):**

三元运算符具有以下形式，

*exp <sub>1</sub> ？出口 <sub>2</sub> :出口<sub>3</sub>T7】*

表达式 *exp <sub>1</sub>* 将始终被求值。 *exp <sub>2</sub>* 和 *exp <sub>3</sub>* 的执行取决于 *exp <sub>1</sub>* 的结果。如果 *exp <sub>1</sub>* 的结果为非零 *exp <sub>2</sub>* 将被评估，否则*exp*<sub>*3*</sub>将被评估。

**副作用:**

**在执行*exp<sub>2</sub>T8】或*exp<sub>3</sub>T12】之前，将立即评估并更新*exp<sub>1</sub>T4 的任何副作用。换句话说，三元表达式中条件求值后有[序列点](http://en.wikipedia.org/wiki/Sequence_point)。如果 *exp <sub>2</sub>* 或 *exp <sub>3</sub>* 有副作用，只评估其中一种。*****

****返回类型:****

****这是另一个有趣的事实。三元运算符具有返回类型。返回类型取决于 exp <sub>2</sub> 和 exp <sub>3</sub> 到 exp <sub>2</sub> 的*可兑换性，按照通常的\重载转换规则。如果它们不可转换，编译器会抛出一个错误。请看下面的例子，*****

****以下程序编译时没有任何错误。三元表达式的返回类型预计为 *float* (与 exp <sub>2</sub> 的返回类型相同)，exp <sub>3</sub> (即字面上的*zero–int*类型)可隐式转换为 *float。*****

```cpp
**#include <iostream>
using namespace std;

int main()
{
   int test = 0;
   float fvalue = 3.111f;
   cout << (test ? fvalue : 0) << endl;

   return 0;
}**
```

****下面的程序不会编译，因为编译器找不到三元表达式的返回类型或者 exp <sub>2</sub> ( *char 数组*)和 exp <sub>3</sub> ( *int* )之间没有隐式转换。****

```cpp
**#include <iostream>
using namespace std;

int main()
{
   int test = 0;
   cout << test ? "A String" : 0 << endl;

   return 0;
}**
```

****以下程序可能会编译，但在运行时会失败。三元表达式的返回类型被限制为类型( *char ** ，但是表达式返回 *int* ，因此程序失败。实际上，程序会在运行时尝试在第 0 个地址打印字符串。****

```cpp
**#include <iostream>
using namespace std;

int main()
{
   int test = 0;
   cout << (test ? "A String" : 0) << endl;

   return 0;
}**
```

****我们可以观察到 *exp <sub>2</sub>* 被认为是输出类型， *exp <sub>3</sub>* 在运行时会转换为 *exp <sub>2</sub>* 。如果转换是隐式的，编译器会插入存根进行转换。如果转换是显式的，编译器会抛出一个错误。如果任何编译器未能捕捉到这样的错误，程序可能会在运行时失败。****

******最佳实践:******

****正是 C++ 类型系统的强大功能避免了这样的 bug。确保表达式 *exp <sub>2</sub>* 和 *exp <sub>3</sub>* 返回相同类型或至少可安全转换的类型。我们可以看到其他类似 C++ 的成语 *convert union* 进行安全转换。****

****如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。我们很乐意向其他极客学习和更新。****