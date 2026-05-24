# 【DART 和 C++ 的区别

> 原文:[https://www . geesforgeks . org/dart-and-c 之间的差异/](https://www.geeksforgeeks.org/difference-between-dart-and-c/)

竞争性编程教人以最快的方式找到最简单的解决方案。而 C++ 一直以来几乎被所有有竞争力的程序员所喜爱。C++ 语言能够提高调试和解决问题的速度，这是这项脑力运动的必需品。

**为什么 C++ 是竞争编程中需求量很大的语言？**

*   C++ 是比雅尼·斯特劳斯特鲁普在 1980 年开发的。从那时起，它就被程序员们积极地用于现实世界的<u>等应用，如游戏开发、浏览器、银行、图形、高级计算等等。这是 C++ 没有失去地位的原因之一。</u>
*   <u>***<u>内置函数:</u>*** C++ 有丰富的与之相关的内置函数。例如:排序可以在 C++ 中使用: *sort(A，* *A+n)* 完成，其中“A”是一个数组，“n”表示数组的长度。</u>
*   <u>***<u>一个非常庞大的库:</u>***c++ 中的模板帮助程序员快速处理基本的数据结构和函数。它们包括列表、堆栈、数组等。另外，许多头文件可以通过使用单个 [STL(标准模板库)](geeksforgeeks.org/the-c-standard-template-library-stl/)来替换。它实际上让有竞争力的程序员的生活变得更容易。</u>
*   <u>***<u>速度:</u>*** 与 Python 和 Java 等语言相比，C++ 非常快。无论是编译还是 I/O 操作，与使用解释器和复杂代码的这些语言相比，C++ 都是迅捷的。</u>

<u>这使得 C++ 成为目前竞争激烈的编程世界中最好、最受欢迎的语言。</u>

<u>**DART 是 C++ 的对手吗？**</u>

<u>DART 基本上是一种客户端优化的语言，旨在为服务器端和浏览器端的应用程序提供服务。它也用于移动应用。如今，Dart 被认为在应用程序开发中取代了使用 Flutter 的 [Kotlin](https://www.geeksforgeeks.org/kotlin-programming-language/) ，因为它避免了对像 XML 和 JSX 这样的独立声明性布局语言的需求。虽然 C++ 是一种具有通用特性的面向对象的编程语言，但是 Dart 是一种面向对象的、基于网络的编程语言。因此，它可以很容易地编译成浏览器应用程序的 JavaScript。此外，我们可以在服务器端使用 Dart 虚拟机来替换 Node.js。这使得 Dart 能够在现代应用程序中抹去 C++ 家族的印记。</u>

<u>**基本差异**</u>

<u>让我们来看看 Dart 和 C++ 的基本不同之处。如何用这两种语言阅读和显示你的名字？</u>

<u>**1。读取用户输入:** C++ 使用‘CIN’和‘scanf’命令读取用户输入。</u>

## <u>C++ </u>

```cpp
#include <iostream>
using namespace std;
int main() {
    string name;
    cin>>name;
    return 0;
}
```

## <u>镖</u>

```cpp
import 'dart:io';
void main(){
  var name = stdin.readLineSync();
}
```

<u>**2。显示输出:** C++ 使用“cout”和“printf”命令显示输出。而 Dart 使用 Python 中的普通打印语句或“写”命令。此外，括号用于指定要在 Dart 语言中显示的元素。</u>

## <u>C++ </u>

```cpp
#include <iostream>
using namespace std;
int main()
{
    string name;
    cin>>name;
    cout<<name;
    return 0;
}
```

## <u>镖</u>

```cpp
import 'dart:io';
void main(){
  var name = stdin.readLineSync();
   stdout.write(name);
}
```

<u>**3。语言类型:** C++ 是面向对象的语言。它支持基本的面向对象特性，如多态性、封装、类、对象、抽象等。</u>

<u>*你知道吗？*</u>

<u>C++ 是一种不纯的面向对象语言。原因包括:</u>

*   <u>在 C++ 中使用全局变量违反了封装。</u>
*   <u>类的使用并不像在 Java 中那样重要，如果使用的话，它们必须在主函数中指定。这防止了在 C++ 中使用多个类。</u>

<u>另一方面，Dart 语言是一种基于网络的编程语言。它也是面向对象、基于类和垃圾收集的语言。它具有扩展集合的扩展操作符等功能。最重要的是，Dart 语言用于**反应式编程，它可以支持用户界面小部件等功能。它还处理数据流，这些数据流负责程序中发生的每一个变化。**</u>

<u>****4。翻译器:**像编译器和解释器这样的语言翻译器用来将高级语言转换成机器语言。C++ 是一种编译语言，因此与解释的 Python 相比，它变得更快。**</u>

<u>**Dart 也可以编译。但是，dart 编译器不会生成机器语言，而是生成 JavaScript 代码，而 JavaScript 代码又是一种解释语言。Dart 也可以编译成本机代码，与 Node.js 一起使用。此外，还有一个 Dart 虚拟机充当解释器。因此，Dart 是一种解释的编译器语言。**</u>