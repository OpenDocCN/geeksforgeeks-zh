# C

内部联动和外部联动

> 原文:[https://www . geesforgeks . org/内部-链接-外部-链接-c/](https://www.geeksforgeeks.org/internal-linkage-external-linkage-c/)

通常很难区分范围和联系，以及它们所扮演的角色。本文主要讨论范围和链接，以及它们如何在 C 语言中使用。
**注:**所有 C 程序均在 64 位 GCC 4.9.2 上编译完成。此外，术语“标识符”和“名称”在本文中可以互换使用。

 **定义**

*   **作用域:**标识符的作用域是程序中标识符可以直接访问的部分。在 C 语言中，所有标识符都是词汇(或静态)范围的。
*   **联动:**联动描述了名称在整个程序或单个翻译单元中如何能或不能指代同一个实体。
    以上听起来和 Scope 差不多，其实不然。为了理解上面的意思，让我们更深入地了解编译过程。
*   **翻译单元:**翻译单元是包含源代码、头文件和其他依赖项的文件。所有这些源都组合在一个文件中，因为它们用于生成一个可执行的对象。以一种有意义的方式将这些来源联系在一起是很重要的。比如编译器要知道`printf`的定义在于`stdio`头文件。

在 C 和 C++ 中，由多个源代码文件组成的程序一次编译一个*。在编译过程之前，变量可以用它的作用域来描述。只有当链接过程开始时，链接属性才开始发挥作用。因此，**作用域是由编译器处理的属性，而链接是由链接器处理的属性。***

*链接器在编译过程的*链接*阶段将资源链接在一起。链接器是一个程序，它接受多个机器代码文件作为输入，并产生一个可执行的目标代码。它解析符号(即获取符号的定义，如“+”等..)并在地址空间中排列对象。*

*链接是一个描述链接器应该如何链接变量的属性。一个变量应该可供另一个文件使用吗？变量应该只在声明的文件中使用吗？两者都是联动决定的。
因此，链接允许您在每个文件的基础上将名称连接在一起，范围决定了这些名称的可见性。
**有 2 种联动:***

1.  ***Internal Linkage**: An identifier implementing internal linkage is not accessible outside the translation unit it is declared in. Any identifier within the unit can access an identifier having internal linkage. It is implemented by the keyword `[static](https://www.geeksforgeeks.org/static-variables-in-c/)`. An internally linked identifier is stored in initialized or uninitialized segment of RAM. (**note:** `static` also has a meaning in reference to scope, but that is not discussed here).
    Some Examples:

    **动物. cpp**

    ```cpp
    // C code to illustrate Internal Linkage
    #include <stdio.h>

    static int animals = 8;
    const int i = 5;

    int call_me(void)
    {
        printf("%d %d", i, animals);
    }
    ```

    以上代码对标识符`animals`实现静态链接。考虑`Feed.cpp`位于同一个翻译单元。

    **饲料 cpp**

    ```cpp
    // C code to illustrate Internal Linkage
    #include <stdio.h>

    int main()
    {
        call_me();
        animals = 2;
        printf("%d", animals);
        return 0;
    }
    ```

    首先编译动物，然后编译饲料，我们得到

    ```cpp
    Output : 5 8 2

    ```

    现在，考虑一下 Feed.cpp 位于不同的翻译单元。只有我们使用`#include "Animals.cpp"`，它才会如上编译运行。
    考虑位于第三翻译单元的 Wash.cpp。

    **Wash.cpp**

    ```cpp
    // C code to illustrate Internal Linkage
    #include <stdio.h>
    #include "animal.cpp" // note that animal is included.

    int main()
    {
        call_me();
        printf("\n having fun washing!");
        animals = 10;
        printf("%d\n", animals);
        return 0;
    }
    ```

    在编译时，我们得到:

    ```cpp
    Output : 5 8
    having fun washing!
    10

    ```

    有 3 个翻译单元(动物、饲料、洗涤)使用`animals`代码。
    这让我们得出结论，每个翻译单元都访问自己的`animals`副本。这就是为什么我们有`animals` = 8 代表`Animals.cpp`，`animals` = 2 代表`Feed.cpp`，`animals` = 10 代表`Wash.cpp`。一份文件。这种行为会消耗内存并降低性能。

    内部链接的另一个性质是**只有在变量有全局作用域**时才实现，所有常量默认内部链接。

    **用法:**我们知道，内部链接变量是通过复制传递的。因此，如果一个头文件有一个函数`fun1()`，并且包含它的源代码也有`fun1()`，但是定义不同，那么这两个函数不会相互冲突。因此，我们通常使用内部链接来隐藏全局范围内的翻译单元本地助手函数。例如，我们可能会在一个描述另一种读取用户输入方法的文件中包含一个包含读取用户输入方法的头文件。这两个函数在链接时是相互独立的。* 
2.  ***External Linkage:** An identifier implementing external linkage is visible to **every translation unit**. Externally linked identifiers are *shared* between translation units and are considered to be located at the outermost level of the program. In practice, this means that you must define an identifier in a place which is visible to all, such that it has only one visible definition. It is the default linkage for globally scoped variables and functions. Thus, all instances of a particular identifier with external linkage refer to the same identifier in the program. The keyword `[extern](https://www.geeksforgeeks.org/understanding-extern-keyword-in-c/)` implements external linkage.

    当我们使用关键字`extern`时，我们告诉链接器在其他地方寻找定义。因此，外部链接标识符的声明不占用任何空间。`Extern`标识符通常存储在内存的初始化/未初始化或文本段中。

    **请务必在进入以下示例之前，先通过 [了解 C](https://www.geeksforgeeks.org/understanding-extern-keyword-in-c/) 中的 extern 关键字。**
    可以在局部范围内使用`extern`变量。这将进一步概述联系和范围之间的区别。考虑以下代码:

    ```cpp
    // C code to illustrate External Linkage
    #include <stdio.h>

    void foo()
    {
        int a;
        extern int b; // line 1
    }

    void bar()
    {
        int c;
        c = b; // error
    }

    int main()
    {
        foo();
        bar();
    }
    ```

    ```cpp
    Error: 'b' was not declared in this scope

    ```

     **解释:**变量`b`在函数`foo`中有局部范围，尽管它是一个`extern`变量。请注意，编译发生在链接之前；即范围是一个只能在编译阶段使用的概念。程序编译后，不存在“变量范围”这样的概念。

    编制时考虑`b`的范围。在`foo()`有局部范围。当编译器看到`extern`声明时，它相信某处有`b`的定义，并让链接器处理剩下的。

    但是，同一个编译器会通过`bar()`函数，试图找到变量`b`。由于`b`已经被声明为`extern`，所以编译器还没有给它内存；它还不存在。编译器会让链接器在翻译单元中找到`b`的定义，然后链接器会给`b`分配定义中指定的值。只有到那时`b`才会存在并被分配内存。但是由于在编译时没有在`bar()`的范围内，甚至在全局范围内给出声明，所以编译器会抱怨上面的错误。

    考虑到编译器的工作是确保所有变量都在它们的作用域内使用，当它在`bar()`中看到`b`时，当`b`已经在`foo()`的作用域中声明时，它会发出抱怨。编译器将停止编译，并且程序不会被传递给链接器。

    我们可以通过将`b`声明为全局变量，将第 1 行移到`foo`的定义之前来修复程序。

    让我们看另一个例子

    ```cpp
    // C code to illustrate External Linkage
    #include <stdio.h>

    int x = 10;
    int z = 5;

    int main()
    {

        extern int y; // line 2
        extern int z;
        printf("%d %d %d", x, y, z);
    }

    int y = 2;
    ```

    ```cpp
    Output: 10 2 5

    ```

    我们可以通过观察外部联系的行为来解释输出。我们在*全局*范围内定义了 2 个变量`x`和`z`。默认情况下，两者都有外部链接。现在，当我们将`y`声明为`extern`时，我们告诉编译器在同一个翻译单元内存在一个带有某种定义的`y`。请注意，这是在编译时阶段，编译器信任`extern`关键字并编译程序的其余部分。下一行`extern int z`对`z`没有影响，因为`z`在我们声明为程序外的全局变量时，默认是外部链接的。当我们遇到`printf`行时，编译器会看到 3 个变量，这 3 个变量之前都被声明过，并且这 3 个变量都在它们的作用域内使用(在`printf`函数中)。这样，即使编译器不知道`y`的定义，程序也能成功编译

    下一阶段是链接。链接器遍历编译后的代码，首先找到`x`和`z`。由于它们是全局变量，默认情况下它们是外部链接的。然后，链接器在整个翻译单元中将`x`和`z`的值更新为 10 和 5。如果翻译单元中的任何其他文件中有对`x`和`z`的引用，则它们被设置为 10 和 5。

    现在，链接器来到`extern int y`并试图在翻译单元中找到`y`的任何定义。它在翻译单元的每个文件中寻找`y`的定义。如果找不到任何定义，将引发链接器错误。在我们的程序中，我们给出了`main()`之外的定义，这个定义已经为我们编译好了。因此，链接器找到该定义并更新`y`。

    本文由 [**西姆兰·达米亚**](https://auth.geeksforgeeks.org/profile.php?user=simran) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。*