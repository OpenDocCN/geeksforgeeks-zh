# c++ 中的属性

> 原文:[https://www.geeksforgeeks.org/attributes-in-c/](https://www.geeksforgeeks.org/attributes-in-c/)

**属性**是现代 C++ 的关键特性之一，它允许程序员**向编译器指定附加信息，以实施约束(条件)，优化某些代码段或进行某些特定的代码生成**。简而言之，属性充当编译器的注释或注释，为优化目的和对其实施某些条件提供关于代码的附加信息。在 C++ 11 中引入，它们一直是 C++ 的最佳特性之一，并且随着 C++ 的每个新版本而不断发展。

**语法:**

> //c++ 11
> [[属性-列表]]
> 
> //c++ 17
> [[使用属性-命名空间:属性-列表]]
> 
> //即将到来的 c++ 20
> [[合约-属性-令牌合约-级别标识符:表达式]]
> 
> 除了一些特定的属性之外，大多数属性
> 可以应用于变量、函数、类、
> 结构等。

### C++ 中属性的用途

*   **To enforce constraints on the code:**

    这里的约束指的是一个条件，特定函数的参数必须满足这个条件才能执行(前提条件)。在 C++ 的早期版本中，用于指定约束的代码是以这种方式编写的

    ```cpp
    int f(int i)
    {
        if (i > 0)
            return i;
        else
            return -1;

        // Code
    }
    ```

    它增加了代码的可读性，并避免了在参数检查函数内部编写的混乱。

    ```cpp
    int f(int i)[[expects:i > 0]]
    {
        // Code
    }
    ```

*   **To give additional information to the compiler for optimisation purposes:**

    编译器非常擅长优化，但与人类相比，它们在某些地方仍然落后，并提出了效率不高的通用代码。这主要是由于缺乏关于人类“问题”的额外信息。为了在一定程度上减少这个问题，C++ 标准引入了一些新的属性，允许向编译器而不是代码语句本身指定更多的内容。一旦这样的例子是可能的。

    ```cpp
    int f(int i)
    {
        switch (i) {
        case 1:
            [[fallthrough]];
            [[likely]] case 2 : return 1;
        }
        return -1;
    }
    ```

    当语句前面有可能是编译器对该语句进行了特殊优化，从而提高了代码的整体性能。这类属性的一些例子有**【carriers _ dependency】、【可能】、【不太可能】**

*   **Suppressing certain warnings and errors that programmer intended to have in his code:**

    这种情况很少发生，但有时程序员故意试图写一个错误的代码，被编译器检测到，并被报告为错误或警告。一个这样的例子是一个未使用的变量，它由于特定的原因留在那个状态，或者是一个 switch 语句，其中 break 语句在某些情况下不被放在后面，从而导致失败的情况。为了规避此类情况下的错误和警告，C++ 提供了诸如**【也许 _ 未使用】**和**【穿越】**等属性，防止编译器生成警告或错误。

    ```cpp
    #include <iostream>
    #include <string>

    int main()
    {

        // Set debug mode in compiler or 'R'
        [[maybe_unused]] char mg_brk = 'D';

        // Compiler does not emit any warnings
        // or error on this unused variable
    }
    ```

### C++ 中的标准属性列表

**C++ 11**

4.  **noreturn:** indicates that the function does not return a value

    用法:

    ```cpp
    [[noreturn]] void f();

    ```

    看着上面的代码，问题来了，当返回类型实际上是**空**的时候，让**不转**有什么意义呢？如果一个函数有一个 void 类型，那么它实际上返回给调用者而没有一个值，但是如果情况是这样的，函数永远不会返回给调用者(例如一个无限循环)，那么添加一个 **noreturn** 属性会提示编译器优化代码或者生成更好的警告。

    **示例:**

    ```cpp
    #include <iostream>
    #include <string>

    [[noreturn]] void f()
    {
        // Some code that does not return
        // back the control to the caller
        // In this case the function returns
        // back to the caller without a value
        // This is the reason why the
        // warning "noreturn' function does return' arises
    }

    void g()
    {
        std::cout << "Code is intented to reach here";
    }

    int main()
    {
        f();
        g();
    }
    ```

    **警告:**

    ```cpp
    main.cpp: In function 'void f()':
    main.cpp:8:1: warning: 'noreturn' function does return
     }
     ^

    ```

    **C++ 14**

5.  **deprecated:** Indicates that the name or entity declared with this attribute has become obsolete and must not be used for some specific reason. This attribute can be applied to namespaces, functions, classes structures or variables.

    用法:

    ```cpp
    [[deprecated("Reason for deprecation")]]

    // For Class/Struct/Union
    struct [[deprecated]] S;

    // For Functions
    [[deprecated]] void f();

    // For namespaces
    namespace [[deprecated]] ns{}

    // For variables (including static data members)
    [[deprecated]] int x;

    ```

    **示例:**

    ```cpp
    #include <iostream>
    #include <string>

    [[deprecated("Susceptible to buffer overflow")]] void gets(char* str)
    {

        // Code for gets dummy
        // (Although original function has
        // char* as return type)
    }

    void gets_n(std::string& str)
    {
        // Dummy code
        char st[100];
        std::cout << "Successfully Executed";
        std::cin.getline(st, 100);
        str = std::string(st);
        // Code for new gets
    }

    int main()
    {
        char a[100];
        gets(a);

        // std::string str;
        // gets_n(str);
    }
    ```

    **警告:**

    ```cpp
    main.cpp: In function 'int main()':
    main.cpp:26:9: warning: 'void gets(char*)' is deprecated:
     Susceptible to buffer overflow [-Wdeprecated-declarations]
       gets(a);
             ^

    ```

    **C++ 17**

6.  **nodiscard:** The entities declared with nodiscard should not have their return values ignored by the caller. Simply saying if a function returns a value and is marked nodiscard then the return value must be utilized by the caller and not discarded.

    用法:

    ```cpp
    // Functions
    [[nodiscard]] void f();

    // Class/Struct declaration 
    struct [[nodiscard]] my_struct{};

    ```

    带函数的 nodiscard 和带结构/类声明的 nodiscard 之间的主要区别在于，在函数的情况下，nodiscard 仅适用于声明不丢弃的特定函数，而在类/结构声明的情况下，no discard 适用于返回由值标记的 nodiscard 对象的每个函数。

    **示例:**

    ```cpp
    #include <iostream>
    #include <string>

    // Return value must be utilized by the caller
    [[nodiscard]] int f()
    {
        return 0;
    }

    class[[nodiscard]] my_class{};

    // Automatically becomes nodiscard marked
    my_class fun()
    {
        return my_class();
    }

    int main()
    {
        int x{ 1 };

        // No error as value is utilised
        // x= f();

        // Error : Value is not utilised
        f();

        // Value not utilised error
        // fun() ;
        return x;
    }
    ```

    **警告:**

    ```cpp
    prog.cpp:5:21: warning: 'nodiscard' attribute directive ignored [-Wattributes]
     [[nodiscard]] int f()
                         ^
    prog.cpp:10:20: warning: 'nodiscard' attribute directive ignored [-Wattributes]
     class[[nodiscard]] my_class{};
                        ^

    ```

7.  **maybe_unused**: Used to suppress warnings on any unused entities (For eg: An unused variable or an unused argument to a function).

    用法:

    ```cpp
    //Variables
    [[maybe_used]] bool log_var = true;

    //Functions
    [[maybe_unused]] void log_without_warning();

    //Function arguments 
    void f([[maybe_unused]] int a, int b);

    ```

    **示例:**

    ```cpp
    #include <iostream>
    #include <string>

    int main()
    {

        // Set debug mode in compiler or 'R'
        [[maybe_unused]] char mg_brk = 'D';

        // Compiler does not emit any warnings
        // or error on this unused variable
    }
    ```

8.  **漏检:**
    【【漏检】】表示 switch 语句中的漏检是故意的。switch 语句中缺少 break 或 return 通常被认为是程序员的错误，但在某些情况下，它会导致一些非常简洁的代码，因此被使用。

**注意:**与其他属性不同的是，失败在声明后需要分号。

**示例:**

```cpp
void process_alert(Alert alert)
{
    switch (alert) {
    case Alert::Red:
        evacuate();
    // Compiler emits a warning here
    // thinking it is done by mistake

    case Alert::Orange:
        trigger_alarm();

        // this attribute needs semicolon
        [[fallthrough]];
    // Warning suppressed by [[fallthrough]]

    case Alert::Yellow:
        record_alert();
        return;

    case Alert::Green:
        return;
    }
}
```

**即将到来的 C++ 20 属性**

15.  **likely:** For optimisation of certain statements that have more probability to execute than others. Likely is now available in latest version of GCC compiler for experimentation purposes.

    **例**

    ```cpp
    int f(int i)
    {
        switch (i) {
        case 1:
            [[fallthrough]];
            [[likely]] case 2 : return 1;
        }
        return 2;
    }
    ```

16.  **no_unique_address**: Indicates that this data member need not have an address distinct from all other non-static data members of its class. This means that if the class consist of an empty type then the compiler can perform empty base optimisation on it.

    **示例:**

    ```cpp
    // empty class ( No state!)
    struct Empty {
    };

    struct X {
        int i;
        Empty e;
    };

    struct Y {
        int i;
        [[no_unique_address]] Empty e;
    };

    int main()
    {
        // the size of any object of
        // empty class type is at least 1
        static_assert(sizeof(Empty) >= 1);

        // at least one more byte is needed
        // to give e a unique address
        static_assert(sizeof(X) >= sizeof(int) + 1);

        // empty base optimization applied
        static_assert(sizeof(Y) == sizeof(int));
    }
    ```

17.  **expects:** It specifies the conditions (in form of contract) that the arguments must meet for a particular function to be executed.

    用法:

    ```cpp
    return_type func ( args...) [[expects : precondition]]

    ```

    **示例:**

    ```cpp
    void list(node* n)[[expects:n != nullptr]]
    ```

    违反合同会导致调用违反处理程序，或者如果未指定，则 std::terminate()

### 标准属性和非标准属性的区别

| 标准属性 | 非标准属性 |
| 由标准和
指定，存在于所有编译器中 | 由编译器供应商提供
并且并不存在于所有编译器中 |
| 代码完全可移植
没有任何警告或问题 | 尽管对于“标准语法”
中的非标准属性，代码变得可移植(从 C++ 17 开始)
了，但是一些警告/错误仍然在编译器中蔓延。 |
| 属性写在
标准语法
**【【ATR】】**中 | 一些属性是在非
标准语法中编写的，而其他属性是在编译器
特定的关键字中编写的，如 **declspec()** 或**_ _ 属性 __** |
| 标准属性不存在于任何封闭命名空间中
 | 非标准属性以标准语法
编写，其封闭的名称空间
**【【名称空间::attr】】** |

### 自 C++ 11 以来的变化

*   **Ignoring unknown attributes:**

    自 C++ 17 以来，C++ 中属性特性引入的主要变化之一是关于编译器对未知属性的澄清。在 C++ 11 或 14 中，如果一个属性没有被编译器识别，那么它会产生一个错误并阻止代码被编译。作为一种变通方法，程序员必须从代码中移除该属性才能使其工作。这带来了一个主要的可移植性问题。除了标准属性之外，不能使用任何特定于供应商的属性，因为代码会被破坏。这妨碍了该功能的实际使用。

    作为一种解决方案，该标准强制所有编译器忽略它们没有定义的属性。这允许程序员在他们的代码中自由使用供应商特定的属性，并确保代码仍然是可移植的。大多数支持 C++ 17 的编译器现在会忽略未定义的属性，并在遇到时发出警告。这使得程序员可以像现在一样使代码更加灵活，他们可以在不同供应商的名称空间下为同一个操作指定多个属性。(支持:MSVC(尚未)、海湾合作委员会、克罗地亚(是))

    **示例:**

    ```cpp
    // Here the attributes will work on their respective
    [[msvc::deprecated]][[gnu::deprecated]] char* gets(char* str) compilers
    ```

*   **Use of attribute namespaces without repetition**:

    在 C++ 17 中，一些关于使用“非标准”属性的规则被放宽了。一种这样的情况是用后续的非标准属性作为名称空间的前缀。在 C++ 11 或 14 中，当多个属性被写在一起时，它们中的每一个都必须以其封闭的名称空间作为前缀，这产生了如下所示的代码模式。

    ```cpp
    [[ gnu::always_inline, gnu::const, gnu::hot, nodiscard ]] int f();
    ```

    看上面的代码，可以看出它看起来臃肿杂乱。因此，委员会决定一起“在使用多个属性时简化案例”。到目前为止，对于程序员来说，一次又一次地在名称空间前面加上后续属性并不是强制性的。这就产生了下面显示的代码模式，它看起来简洁易懂。

    ```cpp
    [[using gnu:const, always_inline]] int f() { return 0; }
    ```

*   **Multiple attributes over a particular piece of code**:

    几个属性现在可以应用于 C++ 中的某段代码。在这种情况下，编译器按照每个属性的编写顺序对其进行评估。这允许程序员编写包含多个约束的代码片段。

    **示例:**

    ```cpp
    #include <iostream>

    // Not implemented by compilers as of now
    // but will be implemented in the future
    [[nodiscard]] int f(int i)[[expects:i > 0]]
    {
        std::cout << " Always greater than 0!"
                  << " and return val must "
                  << "always be utilized";
    }
    ```

### C++ 和 C#中属性的区别

C#和 C++ 中的属性有明显的区别。在 C#的情况下，程序员可以通过从**系统派生来定义新的属性。属性**；而在 C++ 中，元信息是由编译器固定的，不能用来定义新的用户定义属性。这种限制是为了防止语言演变成一种新的形式，这种形式可能会使语言更加复杂。