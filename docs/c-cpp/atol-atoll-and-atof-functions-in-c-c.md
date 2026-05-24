# 环礁()，环礁()和 atof()函数在 C/C++ 中

> 原文:[https://www . geesforgeks . org/环礁-环礁-和-atof-functions-in-c-c/](https://www.geeksforgeeks.org/atol-atoll-and-atof-functions-in-c-c/)

1.  **atol():** This function converts a C-type string, passed as an argument to function call, to a long integer. It parses the C-string str interpreting its content as an integral number, which is returned as a value of type long int. The function discards the whitespace characters present at the beginning of the string until a non-whitespace character is found. If the sequence of non-whitespace characters in C-string str is not a valid integral number, or if no such sequence exists because either str is empty or it contains only whitespace characters, no conversion is performed and zero is returned.

    **语法:**

    ```cpp
    long int atol ( const char * str )

    ```

    **参数:**该函数接受一个强制参数 **str** ，它是一个整数的表示。

    **返回值:**函数将转换后的整数作为长整型数返回。如果无法执行有效转换，它将返回零。

    ```cpp
    // CPP program to illustrate
    // working of atol() function.
    #include <bits/stdc++.h>
    using namespace std;

    int main()
    {
        // char array of numbers
        char str1[] = "5672345";

        // Function calling to convert to a long int
        long int num1 = atol(str1);

        cout << "Number is " << num1 << "\n";

        // char array of numbers of spaces
        char str2[] = "10000002  0";

        // Function calling to convert to a long int
        long int num2 = atol(str2);

        cout << "Number is " << num2 << "\n";
        return 0;
    }
    ```

    **Output:**

    ```cpp
    Number is 5672345
    Number is 10000002

    ```