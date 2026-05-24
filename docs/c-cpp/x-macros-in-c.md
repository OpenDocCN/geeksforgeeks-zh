# X-C 中的宏

> 原文:[https://www.geeksforgeeks.org/x-macros-in-c/](https://www.geeksforgeeks.org/x-macros-in-c/)

**X-Macros** 基于嵌套宏的属性和在其他宏中定义宏的能力。从某种意义上说，x-macro 是非常强大的预处理器技术，它可以创建一段**自我维护和相互依赖的**代码。当一个程序的一个部分的变化导致另一个部分的变化时，那么代码就被称为是相互依赖的。

**语法:**
一个 X 宏应用程序由两部分组成:

*   **列表元素的定义:**

    ```cpp
    #define VARIABLES \
        X(value1, 1)  \
        .
        .
        .  \
        X(valueN, N)

    ```

*   **扩展列表以生成声明或语句的片段:**

    ```cpp
    #define X(name) int name;
        VARIABLES
    #undef X

    ```

该列表是由一个宏或头文件(名为，VARIABLES)定义的，它本身不生成任何代码，而只是由一系列调用宏(通常名为“X”)和元素数据组成。变量的每次扩展之前都有一个 X 的定义，带有列表元素的语法。变量的调用为列表中的每个元素扩展了 X。

**实现:**

*   **Example 1:** Following Code explains the working of X-Macros:

    ```cpp
    #include <stdio.h>

    // Defines four variables.
    #define VARIABLES \
        X(value1, 1)  \
        X(value2, 2)  \
        X(value3, 3)  \
        X(value4, 4)

    // driver program.
    int main(void)
    {
        // Declaration of every variable
        // is done through macro.
        #define X(value, a) char value[10];
            VARIABLES
        #undef X

        // String values are accepted
        // for all variables.
        #define X(value, a) scanf("\n%s", value);
            VARIABLES
        #undef X

        // Values are printed.
        #define X(value, a) printf("%d) %s\n", a, value);
            VARIABLES
        #undef X
        return 0;
    }
    ```

    **Output:**

    ```cpp
    1) geeks
    2) for
    3) geeks
    4) geeksforgeeks

    ```

    在上述代码中，在宏**“变量”**中添加一个或多个变量将导致其自动声明、扫描以及打印。这个简单的例子阐明了 X 宏的工作原理和功能。扩展后，上面的代码看起来像下面的代码:

    ```cpp
    #include <stdio.h>

    int main(void)
    {
        char value1[10];
        char value2[10];
        char value3[10];
        char value4[10];

        scanf("\n%s", value1);
        scanf("\n%s", value2);
        scanf("\n%s", value3);
        scanf("\n%s", value4);

        printf("%d) %s\n", 1, value1);
        printf("%d) %s\n", 2, value2);
        printf("%d) %s\n", 3, value3);
        printf("%d) %s\n", 4, value4);
        return 0;
    }
    ```

    **Output:**

    ```cpp
    1) geeks
    2) for
    3) geeks
    4) geeksforgeeks

    ```

    虽然上面的代码只是简单的解释了 X-Macros 的威力，但是这样的使用并不多见， ***不推荐*** 使用，因为这样会让代码可读性降低。一个更实际的例子是枚举或跳转表。

*   **Example 2:** Following code explains the working of X-Macros with enum:

    ```cpp
    #include <stdio.h>

    // Defining a macro 
    // with the values of colors.
    #define COLORS \
        X(RED)     \
        X(BLACK)   \
        X(WHITE)   \
        X(BLUE)

    // Creating an enum of colors
    // by macro expansion.
    enum colors {
        #define X(value) value,
            COLORS
        #undef X
    };

    // A utility that takes the enum value
    // and returns corresponding string value
    char* toString(enum colors value)
    {
        switch (value) {
            #define X(color) \
                case color:  \
                    return #color;
                    COLORS
            #undef X
        }
    }

    // driver program.
    int main(void)
    {
        enum colors color = WHITE;
        printf("%s", toString(color));
        return 0;
    }
    ```

    **Output:**

    ```cpp
    WHITE

    ```

    在上面的代码中，从 COLORS 宏中添加或删除任何常量都会自动反映在枚举以及 toString()函数的定义中。这就是为什么 X-macro 被用来产生自我维护的代码。宏展开后，上面的代码看起来像下面的代码:

    ```cpp
    #include <stdio.h>

    // Creating an enum of colors.
    enum colors {
        RED,
        BLACK,
        WHITE,
        BLUE
    };

    /*A utility that takes the enum value and returns 
    corresponding string value*/
    char* toString(enum colors value)
    {
        switch (value) {
        case RED:
            return "RED";
        case BLACK:
            return "BLACK";
        case WHITE:
            return "WHITE";
        case BLUE:
            return "BLUE";
        }
    }

    // driver program.
    int main(void)
    {
        enum colors color = WHITE;
        printf("%s", toString(color));
        return 0;
    }
    ```

    **Output:**

    ```cpp
    WHITE

    ```

**X 宏的优势**

*   通过创建单独的头文件来提高可维护性和可读性，x 宏在操作系统开发中被广泛使用
*   有助于轻松维护复杂的编程
*   它可以创建一段自我维护和相互依赖的代码

**X-宏的缺点**

*   代码变得不太可读
*   代码很难理解
*   通常仅用于内部编程，如操作系统编程。

**参考资料:**[https://en . Wikipedia . org/wiki/x _ macro](https://en.wikipedia.org/wiki/X_Macro)