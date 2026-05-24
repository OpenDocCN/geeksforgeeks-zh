# 关系运算符(==)与 C++ 中的 std::string::compare()的区别

> 原文:[https://www . geesforgeks . org/relational-operator-and-stdstringcompare-in-c/](https://www.geeksforgeeks.org/difference-between-relational-operator-and-stdstringcompare-in-c/)之间的差异

[使用关系运算符](https://www.geeksforgeeks.org/comparing-string-objects-using-relational-operators-c/)比较字符串，[使用比较()](https://www.geeksforgeeks.org/stdstringcompare-in-c/)

**关系运算符 vs std::string::compare()**

1.  **返回值:**关系运算符返回布尔值，而 compare()返回无符号整数。
2.  **参数:**关系运算符只需要两个字符串就可以进行比较，一个是正在比较的，另一个是作为参考的，而 compare()可以接受不同的参数来相应地执行某个任务。
3.  **比较方法:**关系运算符根据当前字符特征按字典顺序比较字符，而 compare()可以为每个字符串处理多个参数，以便您可以根据其索引和长度指定子字符串。
4.  **Operation :** We can perform comparison in a part of string directly, using compare() which is otherwise quite a long process with relational operators.
    **Example :** * Compare 3 characters from 3rd position of str1 with 3 characters from 4th position of str2.

    ```cpp
    * str1 = "GeeksforGeeks"
    * str2 = "HelloWorld!"
    ```

    **使用 compare() :**

    ```cpp
    // CPP code to perform comparison using compare()
    #include <iostream>
    using namespace std;

    void usingCompare(string str1, string str2)
    {
        // Direct Comparison
        if (str1.compare(2, 3, str2, 3, 3) == 0)
            cout << "Both are same";
        else
            cout << "Not equal";
    }

    // Main function
    int main()
    {
        string s1("GeeksforGeeks");
        string s2("HelloWorld !");
        usingCompare(s1, s2);

        return 0;
    }
    ```

    输出:

    ```cpp
    Not equal

    ```

    **使用关系运算符:**

    ```cpp
    // CPP code for comparison using relational operator
    #include <iostream>
    using namespace std;

    void relational_operation(string s1, string s2)
    {
        int i, j;

        // Lexicographic comparison
        for (i = 2, j = 3; i <= 5 && j <= 6; i++, j++) {
            if (s1[i] != s2[j])
                break;
        }
        if (i == 6 && j == 7)
            cout << "Equal";
        else
            cout << "Not equal";
    }

    // Main function
    int main()
    {
        string s1("GeeksforGeeks");
        string s2("HelloWorld !");
        relational_operation(s1, s2);

        return 0;
    }
    ```

    输出:

    ```cpp
    Not equal

    ```

    我们可以清楚地观察到在使用关系运算符时需要经历的额外处理。

本文由**萨基提瓦里**供稿。如果你喜欢极客(我们知道你喜欢！)并愿意投稿，也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者将文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。