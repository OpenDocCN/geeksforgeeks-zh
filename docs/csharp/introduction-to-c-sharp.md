# c# 入门

> 原文:[https://www.geeksforgeeks.org/introduction-to-c-sharp/](https://www.geeksforgeeks.org/introduction-to-c-sharp/)

[C# ](https://www.geeksforgeeks.org/csharp-programming-language/) 是一种通用、现代和面向对象的编程语言，发音为**“C 夏普”**。它是由微软开发的，由安德斯·海尔斯伯格和他的团队领导。Net 倡议，并获得了欧洲计算机制造商协会(ECMA)和国际标准组织(ISO)的批准。C# 是[通用语言基础设施](https://en.wikipedia.org/wiki/Common_Language_Infrastructure)的语言之一，目前的 C# 版本是 7.2 版本。C# 在语法上与 Java 非常相似，对于具有 C、C++或 Java 知识的用户来说很容易。

**有点差不多。网络框架**
。Net 应用程序是多平台应用程序，框架可以从 C++、C#、Visual Basic、COBOL 等语言中使用。它是以其他语言可以使用的方式设计的。
了解更多[。网络框架](https://en.wikipedia.org/wiki/.NET_Framework)

**为什么是 C#？**

C# 受欢迎和受欢迎还有许多其他原因。下面提到的原因很少:

1.  **容易上手:** C# 是一种高级语言，因此它更接近于其他流行的编程语言，如 C、C++、Java，因此变得对任何人都很容易学习。
2.  **广泛用于开发桌面和 web 应用:** C# 广泛用于开发 Web 应用和桌面应用。它是在专业桌面中使用的最流行的语言之一。如果有人想创建微软应用程序，C# 是他们的首选。
3.  **社区:**社区越大越好，因为新的工具和软件将不断开发，使其变得更好。C# 有一个很大的社区，所以开发是为了让它存在于系统中而不是灭绝。
4.  **游戏开发:** C# 广泛应用于游戏开发，并将继续占据主导地位。C# 与微软集成，因此拥有大量的目标受众。诸如自动垃圾收集、接口、面向对象等 C# 特性。让 C# 成为流行的游戏开发语言。

**从 C# 编程开始:**
**找编译器:**
网上有各种各样的 ide，比如[geeks forgeeks ide](https://ide.geeksforgeeks.org/)[CodeChef ide](https://www.codechef.com/ide)等。它可以用来运行 C# 程序而无需安装。

**Windows:** 因为 C# 是在内部开发的。Net 框架倡议，它提供各种 ide 来运行 C# 程序:[微软 Visual Studio](https://www.visualstudio.com/) 、 [Visual Studio Express](https://www.visualstudio.com/vs/express/) 、 [Visual Web Developer](https://msdn.microsoft.com/en-us/library/ee410104(v=vs.100).aspx)

**Linux:** [Mono](http://www.mono-project.com/) 可以用来在 Linux 上运行 C# 程序。

**用 C# 编程:**
由于 C# 在语法上与其他广泛使用的语言有很多相似之处，所以用 C# 编程和学习更容易。
程序可以在任何广泛使用的文本编辑器中用 C# 编写，如 Notepad++、gedit 等。或者在任何编译器上。写完程序后，保存扩展名为. cs 的文件。

**示例:**一个简单的程序打印**你好极客**

```cs
// C# program to print Hello Geeks
using System;

namespace HelloGeeksApp
{   
    class HelloGeeks
    {   
        // Main function
        static void Main(string[] args)
        {

            // Printing Hello Geeks
            Console.WriteLine("Hello Geeks");

            Console.ReadKey();
        }
    }
}
```

**输出:**

```cs
Hello Geeks
```

**说明:**
**1。注释:**注释用于解释代码，其使用方式类似于 Java 或 C 或 C++。编译器忽略注释条目，并且不执行它们。注释可以是单行或多行。
**单行注释:**
**语法:**

```cs
// Single line comment
```

**多行注释:**
**语法:**

```cs
/* Multi line comments*/
```

**2。使用系统:** **使用**关键字用于在程序中包含系统命名空间。
**名称空间声明:**名称空间是类的集合。HelloGeeksApp 命名空间包含类 HelloGeeks。
**3。类:**类包含程序中要使用的数据和方法。方法定义类的行为。类**hello geks**只有一个类似于 JAVA 的 Main 方法。

**4。static void Main():****static**关键字告诉我们，这个方法不需要实例化类就可以访问。 **5。void** 关键字告诉我们这个方法不会返回任何东西。 **Main()** 方法是我们应用的切入点。在我们的程序中，Main()方法用 Console 语句指定其行为。WriteLine(“你好，极客”)；。

**6。控制台。WriteLine():** WriteLine()是在 System 命名空间中定义的 Console 类的方法。
**7。控制台。ReadKey():** 这是给 VS.NET 用户的。这使得程序等待按键，并阻止屏幕快速运行和关闭。
**注意:** C# 区分大小写，所有语句和表达式必须以分号(；).

**c# 的优势:**

*   C# 在管理系统方面非常高效。所有的垃圾都是用 C# 自动收集的。
*   C# 没有内存泄漏的问题，因为它的内存备份很高。
*   与其他语言相比，维护成本更低，运行更安全。
*   C# 代码被编译成中间语言(Common(。Net)中间语言)，它是一种标准语言，与目标操作系统和体系结构无关。

**c# 的缺点:**

*   C# 不太灵活，因为它非常依赖。Net 框架。
*   C# 运行缓慢，每次进行更改时都需要编译程序。

**应用:**

*   C# 广泛用于开发桌面应用程序、web 应用程序和 web 服务。
*   它用于大规模创建微软的应用程序。
*   C# 也用于 [Unity](https://en.wikipedia.org/wiki/Unity_(game_engine)) 中的游戏开发。