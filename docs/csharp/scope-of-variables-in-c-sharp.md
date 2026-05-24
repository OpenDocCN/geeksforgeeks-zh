# c# 中变量的范围

> 原文:[https://www . geesforgeks . org/c-sharp 中变量的范围/](https://www.geeksforgeeks.org/scope-of-variables-in-c-sharp/)

程序中可访问特定变量的部分称为该变量的作用域。变量可以在类、方法、循环等中定义。在 C/C++中，所有标识符都有词汇(或静态)范围，即变量的范围可以在编译时确定，并且独立于函数调用堆栈。但是 C# 程序是以类的形式组织的。

所以 C# 变量的作用域规则可以分为如下三类:

*   **类级别范围***   **方法级别范围***   **Block Level Scope

    #### 类级别范围

    *   在类中但在任何方法之外声明变量可以在类的任何地方直接访问。
    *   这些变量也被称为字段或类成员。
    *   类级别范围的变量可以由声明它的类的非静态方法访问。
    *   类级变量的访问修饰符不会影响它们在类中的作用域。
    *   也可以使用访问修饰符在类外访问成员变量。

    **示例:**

    ```cs
    // C# program to illustrate the
    // Class Level Scope of variables
    using System;

    // declaring a Class
    class GFG { // from here class level scope starts

        // this is a class level variable
        // having class level scope
        int a = 10;

        // declaring a method
        public void display()
        {
            // accessing class level variable
            Console.WriteLine(a);

        } // here method ends

    } // here class level scope ends
    ```

    #### 方法级别范围

    *   在方法内部声明的变量具有方法级别的作用域。这些在方法之外是不可访问的。
    *   但是，这些变量可以由方法内部的嵌套代码块访问。
    *   这些变量被称为局部变量。
    *   如果这些变量在同一个作用域中用相同的名称声明两次，将会出现编译时错误。
    *   这些变量在方法执行结束后不存在。

    **示例:**

    ```cs
    // C# program to illustrate the
    // Method Level Scope of variables
    using System;

    // declaring a Class
    class GFG { // from here class level scope starts

        // declaring a method
        public void display()

        { // from here method level scope starts

            // this variable has
            // method level scope
            int m = 47;

            // accessing method level variable
            Console.WriteLine(m);

        } // here method level scope ends

        // declaring a method
        public void display1()

        { // from here method level scope starts

            // it will give compile time error as
            // you are trying to access the local
            // variable of method display()
            Console.WriteLine(m);

        } // here method level scope ends

    } // here class level scope ends
    ```

    #### 块级范围

    *   这些变量通常在 for、while 语句等中声明。
    *   这些变量也被称为循环变量或语句变量，因为它们将其范围限制在声明它的语句体中。
    *   通常，方法内部的循环有三层嵌套代码块(即类级、方法级、循环级)。
    *   在循环外部声明的变量也可以在嵌套循环中访问。这意味着方法和所有循环都可以访问类级变量。方法级变量可由该方法内部的循环和方法访问。
    *   在循环体内部声明的变量对于循环体外部是不可见的。

    **示例:**

    ```cs
    // C# code to illustrate the Block
    // Level scope of variables
    using System;

    // declaring a Class
    class GFG

    { // from here class level scope starts

        // declaring a method
        public void display()

        { // from here method level scope starts

            // this variable has
            // method level scope
            int i = 0;

            for (i = 0; i < 4; i++) {

                // accessing method level variable
                Console.WriteLine(i);
            }

            // here j is block level variable
            // it is only accessible inside
            // this for loop
            for (int j = 0; j < 5; j++) {
                // accessing block level variable
                Console.WriteLine(j);
            }

            // this will give error as block level
            // variable can't be accessed outside
            // the block
            Console.WriteLine(j);

        } // here method level scope ends

    } // here class level scope ends
    ```**