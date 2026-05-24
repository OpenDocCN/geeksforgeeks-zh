# # C/c++ 中的 pragma 指令

> 原文:[https://www.geeksforgeeks.org/pragma-directive-in-c-c/](https://www.geeksforgeeks.org/pragma-directive-in-c-c/)

该指令是一个特殊目的指令，用于打开或关闭某些功能。这种类型的指令是编译器特定的，即它们因编译器而异。下面讨论一些#pragma 指令:

1.  **#pragma startup and #pragma exit**: These directives helps us to specify the functions that are needed to run before program startup( before the control passes to main()) and just before program exit (just before the control returns from main()).

    **注意**:下面的程序不会和 GCC 编译器一起工作。
    看下面的程序:

    ```cpp
    #include<stdio.h> 

    void func1(); 
    void func2(); 

    #pragma startup func1 
    #pragma exit func2 

    void func1() 
    { 
        printf("Inside func1()\n"); 
    } 

    void func2() 
    { 
        printf("Inside func2()\n");    
    } 

    int main() 
    { 
        printf("Inside main()\n"); 

        return 0; 
    } 
    ```

    **Output:**

    ```cpp
    Inside func1()
    Inside main()
    Inside func2()

    ```

    当在 GCC 编译器上运行时，上述代码将产生如下所示的输出:

    ```cpp
    Inside main()

    ```

    出现这种情况是因为 GCC 不支持 **#pragma 启动或退出**。但是，您可以使用下面的代码在 GCC 编译器上获得类似的输出。

    ```cpp
    #include<stdio.h> 

    void func1(); 
    void func2(); 

    void __attribute__((constructor)) func1(); 
    void __attribute__((destructor)) func2(); 

    void func1() 
    { 
        printf("Inside func1()\n"); 
    } 

    void func2() 
    { 
        printf("Inside func2()\n");  
    } 

    int main() 
    { 
        printf("Inside main()\n"); 

        return 0; 
    } 
    ```

    **Output:**

    ```cpp
    Inside func1()
    Inside main()
    Inside func2()

    ```

2.  **#pragma warn Directive**: This directive is used to hide the warning messages which are displayed during compilation. This may be useful for us when we have a large program and we want to solve all the errors before looking on warnings then by using it we can focus on errors by hiding all warnings. we can again let the warnings be visible by making slight changes in syntax.

    **语法**:

    ```cpp
    #pragma warn +xxx (To show the warning)
    #pragma warn -xxx (To hide the warning)
    #pragma warn .xxx (To toggle between hide and show)

    ```

    我们可以隐藏警告，如下所示:

    *   **#pragma warn -rvl** :该指令隐藏了当一个应该返回值的函数没有返回值时发出的警告。
    *   **#pragma warn -par** :该指令隐藏了当函数不使用传递给它的参数时发出的警告。
    *   **#pragma warn -rch** :该指令隐藏了当代码不可访问时发出的警告。例如:函数中任何写在 return 语句之后的代码都是不可达的。

    **例**:

    ```cpp
    // Example to explain the working of 
    // #pragma warn directive
    // This program is compatible with C/C++ compiler 

    #include<stdio.h>

    #pragma warn -rvl /* return value */
    #pragma warn -par /* parameter never used */
    #pragma warn -rch /*unreachable code */

    int show(int x)
    {   
        // parameter x is never used in
        // the function

        printf("GEEKSFORGEEKS");

        // function does not have a
        // return statement
    }

    int main()
    {
        show(10);

        return 0;
    }
    ```

    **Output:**

    ```cpp
    GEEKSFORGEEKS

    ```

    上述程序编译成功，没有任何警告，给出输出“GEEKSFORGEEKS”。

3.  **#pragma GCC poison**: This directive is supported by the GCC compiler and is used to remove an identifier completely from the program. If we want to block an identifier then we can use the **#pragma GCC poison** directive.

    **例**:

    ```cpp
    // Program to illustrate the 
    // #pragma GCC poison directive

    #include<stdio.h>

    #pragma GCC poison printf

    int main()
    {
        int a=10;

        if(a==10)
        {
            printf("GEEKSFORGEEKS");
        }
        else
            printf("bye");

        return 0;
    }
    ```

    上面的程序会给出下面的错误:

    ```cpp
    prog.c: In function 'main':
    prog.c:14:9: error: attempt to use poisoned "printf"
             printf("GEEKSFORGEEKS");
             ^
    prog.c:17:9: error: attempt to use poisoned "printf"
             printf("bye");
             ^

    ```

4.  **#pragma GCC dependency**: The #pragma GCC dependency allows you to check the relative dates of the current file and another file. If the other file is more recent than the current file, a warning is issued. This is useful if the current file is derived from the other file, and should be regenerated.

    **语法**:

    ```cpp
    #pragma GCC dependency "parse.y"
    #pragma GCC dependency "/usr/include/time.h" rerun fixincludes

    ```

5.  **#pragma GCC system_header** :此 pragma 不接受任何参数。它导致当前文件中的其余代码被视为来自系统头。
6.  **#pragma once**: The #pragma once directive has a very simple concept. The header file containing this directive is included only once even if the programmer includes it multiple times during a compilation. This is not included in any ISO C++ standard. This directive works similar to the #include guard idiom. Use of #pragma once saves the program from multiple inclusion optimisation.

    **语法:**

    ```cpp
    #pragma once
    ```