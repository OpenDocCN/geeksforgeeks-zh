# c++ 中的操纵器，示例

> 原文:[https://www . geeksforgeeks . org/operators-in-c-with-examples/](https://www.geeksforgeeks.org/manipulators-in-c-with-examples/)

**操纵器**是帮助功能，可以修改[输入/输出](https://www.geeksforgeeks.org/basic-input-output-c/)流。这并不意味着我们改变变量的值，它只使用插入(< <)和提取(> >)操作符来修改输入/输出流。

例如，如果我们想要打印十六进制值 100，那么我们可以将其打印为:

```cpp
cout<<setbase(16)<<100
```

**机械手类型**

操纵器有多种类型:

1.  **无参数操纵器**:下面提供了**iOS stream 库**定义的最重要的操纵器。
    *   **endl** :在牡蛎中定义。它用于输入一个新行，在输入一个新行后，它会刷新输出流(即，它会强制将所有输出写入屏幕或文件中)。
    *   **ws** :在 istream 中定义，用于忽略字符串序列中的空格。
    *   **结束**:也是在 ostream 中定义的，它在输出流中插入一个空字符。它通常与 STD::ost stream 一起使用，当相关的输出缓冲区需要以空终止以作为 C 字符串处理时。
    *   **flush**: It is also defined in ostream and it flushes the output stream, i.e. it forces all the output written on the screen or in the file. Without flush, the output would be the same, but may not appear in real-time.

        **示例:**

        ```cpp
        #include <iostream>
        #include <istream>
        #include <sstream>
        #include <string>

        using namespace std;

        int main()
        {
            istringstream str("           Programmer");
            string line;
            // Ignore all the whitespace in string
            // str before the first word.
            getline(str >> std::ws, line);

            // you can also write str>>ws
            // After printing the output it will automatically
            // write a new line in the output stream.
            cout << line << endl;

            // without flush, the output will be the same.
            cout << "only a test" << flush;

            // Use of ends Manipulator
            cout << "\na";

            // NULL character will be added in the Output
            cout << "b" << ends;
            cout << "c" << endl;

            return 0;
        }
        ```

        **Output:**

        ```cpp
        Programmer
        only a test
        abc

        ```

2.  **Manipulators with Arguments:** Some of the manipulators are used with the argument like setw (20), setfill (‘*’), and many more. These all are defined in the header file. If we want to use these manipulators then we must include this header file in our program.

    例如，您可以使用以下操纵器来设置最小宽度，并用您想要的任何字符填充空白:STD::cout < < STD::setw(6)< < STD::setfill(' *)；

    *   **T4 的一些重要操纵者是:**
        1.  **setw (val):** 用于设置输出操作中的字段宽度。
        2.  **setfill (c):** 用于填充输出流中的字符‘c’。
        3.  **设置精度(val):** 它将 val 设置为浮点值精度的新值。
        4.  **设置基(val):** 用于设置数值的数值基值。
        5.  **setiosflags(标志):**用于设置参数掩码指定的格式标志。
        6.  **resetiosflags(m):** 用于重置参数掩码指定的格式标志。
    *   **T2 IOs>中一些重要的操控者有:**
        1.  **显示:**它强制在正数上显示一个正号。
        2.  **noshowpos:** 它强制不要在正数上写正号。
        3.  **显示基数:**表示数值的数值基数。
        4.  **大写:**它强制数字值使用大写字母。
        5.  **noppercase:**它强制数值使用小写字母。
        6.  **固定:**对浮点值使用十进制表示法。
        7.  **scientific:** 它使用科学浮点记数法。
        8.  **十六进制:**读写整数的十六进制值，其工作方式与 setbase(16)相同。
        9.  **dec:** 读写整数的十进制值，即 setbase(10)。
        10.  **oct:** 读写整数的八进制值，即 setbase(10)。
        11.  **向左:**向左调整输出。
        12.  **右:**向右调整输出。

    **示例:**

    ```cpp
    #include <iomanip>
    #include <iostream>
    using namespace std;

    int main()
    {
        double A = 100;
        double B = 2001.5251;
        double C = 201455.2646;

        // We can use setbase(16) here instead of hex

        // formatting
        cout << hex << left << showbase << nouppercase;

        // actual printed part
        cout << (long long)A << endl;

        // We can use dec here instead of setbase(10)

        // formatting
        cout << setbase(10) << right << setw(15)
             << setfill('_') << showpos
             << fixed << setprecision(2);

        // actual printed part
        cout << B << endl;

        // formatting
        cout << scientific << uppercase
             << noshowpos << setprecision(9);

        // actual printed part
        cout << C << endl;
    }
    ```

    **Output:**

    ```cpp
    0x64
    _______+2001.53
    2.014552646E+05

    ```

**参考文献:**

*   [http://www.cplusplus.com/reference/iomanip/](http://www.cplusplus.com/reference/iomanip/)
*   [http://www.cplusplus.com/reference/ios/basic_ios/](http://www.cplusplus.com/reference/ios/basic_ios/)
*   [http://www.cplusplus.com/reference/ios/](http://www.cplusplus.com/reference/ios/)