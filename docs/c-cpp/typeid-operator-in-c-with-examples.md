# c++ 中的 typeid 运算符，示例

> 原文:[https://www . geesforgeks . org/typeid-operator-in-c-with-examples/](https://www.geeksforgeeks.org/typeid-operator-in-c-with-examples/)

**typeid** 是 C++ 中的[运算符](https://www.geeksforgeeks.org/operators-c-c/)。

*   在需要对象的[动态类型或运行时类型](https://www.geeksforgeeks.org/g-fact-33/)信息的地方使用。
*   它包含在 **< typeinfo >** 库中。因此，为了使用 typeid，这个库应该包含在程序中。
*   typeid 表达式是一个[左值表达式](https://www.geeksforgeeks.org/lvalue-and-rvalue-in-c-language/)。

**语法:**

```cpp
typeid(type);
OR
typeid(expression);
```

**参数:** typeid 运算符根据程序中使用的语法接受参数:

*   **类型**:需要变量或对象的运行时类型信息时，传递该参数。在这种情况下，不需要在类型内部进行评估，只需知道类型信息。
*   **表达式:**需要表达式的运行时类型信息时传递此参数。在这种情况下，首先计算表达式。然后提供最终结果的类型信息。

**返回值:**该运算符提供指定参数的运行时类型信息，因此返回 [**类型信息**](https://www.geeksforgeeks.org/g-fact-33/) ，作为对**类类型信息**的对象的引用。
**用法:** typeid()运算符根据操作数类型的不同使用方式不同。

1.  当操作数是变量或对象时。

    ## 卡片打印处理机(卡片打印处理器的缩写)

    ```cpp
    // C++ program to show the use of typeid operator

    #include <iostream>
    #include <typeinfo>
    using namespace std;

    int main()
    {
        int i, j;
        char c;

        // Get the type info using typeid operator
        const type_info& ti1 = typeid(i);
        const type_info& ti2 = typeid(j);
        const type_info& ti3 = typeid(c);

        // Check if both types are same
        if (ti1 == ti2)
            cout << "i and j are of"
                 << " similar type" << endl;
        else
            cout << "i and j are of"
                 << " different type" << endl;

        // Check if both types are same
        if (ti2 == ti3)
            cout << "j and c are of"
                 << " similar type" << endl;
        else
            cout << "j and c are of"
                 << " different type" << endl;

        return 0;
    }
    ```

    **输出**

    ```cpp
    i and j are of similar type
    j and c are of different type
    ```

2.  当操作数是表达式时。

    ## 卡片打印处理机(卡片打印处理器的缩写)

    ```cpp
    // C++ program to show the use of typeid operator

    #include <iostream>
    #include <typeinfo>
    using namespace std;

    int main()
    {
        int i = 5;
        float j = 1.0;
        char c = 'a';

        // Get the type info using typeid operator
        const type_info& ti1 = typeid(i * j);
        const type_info& ti2 = typeid(i * c);
        const type_info& ti3 = typeid(c);

        // Print the types
        cout << "ti1 is of type "
             << ti1.name() << endl;

        cout << "ti2 is of type "
             << ti2.name() << endl;

        cout << "ti3 is of type "
             << ti3.name() << endl;

        return 0;
    }
    ```

    **输出:**

    ```cpp
    ti1 is of type f
    ti2 is of type i
    ti3 is of type c
    ```