# 了解 ShellExecute 函数及其应用，使用 C++ 代码打开文件中存在的 URL 列表

> 原文:[https://www . geesforgeks . org/understanding-shellexecute-function-application-open-list-URLs-present-file-use-c-code/](https://www.geeksforgeeks.org/understanding-shellexecute-function-application-open-list-urls-present-file-using-c-code/)

给定一个字符串形式的网址，使用微软视窗操作系统中的 C++ 代码打开它。
例:

```cpp
Input : https://www.geeksforgeeks.org/
Output : The site opened in your browser.

```

```cpp
// C++ program to open a URL in browser.
// This program is written on for Microsoft
// Windows OS
#include <bits/stdc++.h>
#include <windows.h>
using namespace std;

int main()
{
    char url[100] = "http:// www.geeksforgeeks.org/";
    ShellExecute(NULL, "open", url, NULL, NULL, SW_SHOWNORMAL);
    return 0;
}
```

输出:

```cpp
GeeksforGeeks site opened in Google Chrome in a new tab.

```

**ShellExecute** 相当于用户双击文件图标的代码。它使 Windows 计算出文档文件与哪个应用程序相关联，启动程序并让它加载文档文件。

通过使用 **ShellExecute** ，您不需要知道注册到特定文件类型的程序的名称或位置。Windows 会帮你搞定的。例如，您可以 shell execute . PDF 文件，只要安装了 Reader、Acrobat 或其他一些 PDF 阅读应用程序，Windows 就会启动它并为您加载 PDF。

**shell execute 的参数及其含义:**

HINSTANCE ShellExecute(
_ In _ opt _ HWND HWND，
_In_opt_ LPCTSTR lpOperation，
_In_ LPCTSTR lpFile，
_In_opt_ LPCTSTR lpParameters，
_In_opt_ LPCTSTR lpDirectory，
_ In _ INT nShowCmd
)；

**参数:**

类型为“T0”和“T1”

用于显示用户界面或错误消息的父窗口的句柄。如果操作与窗口无关，则该值可以为空。

类型:lpctstr

指向空终止字符串的指针，在本例中称为动词，它指定要执行的操作。可用动词集取决于特定的文件或文件夹。通常，对象快捷菜单中可用的操作是可用的动词。**在我们的例子中，使用“打开”来打开由 lpFile 参数指定的项目。项目可以是文件或文件夹。**

类型: **LPCTSTR**
一个指向空终止字符串的指针，该字符串指定在其上执行指定动词的文件或对象。若要指定外壳命名空间对象，请传递完全限定的解析名称。请注意，并非所有对象都支持所有动词。例如，并非所有文档类型都支持“打印”动词。如果相对路径用于 lpDirectory 参数，不要为 lpFile 使用相对路径。在我们的例子中，它是一个字符' url '数组，在这个数组上执行操作。

类型: **LPCTSTR**
如果 lpFile 指定了一个可执行文件，这个参数是一个指向空终止字符串的指针，该字符串指定了要传递给应用程序的参数。该字符串的格式由要调用的动词决定。如果 lpFile 指定了文档文件，lpParameters 应该为空。

类型: **LPCTSTR**
一个指向空终止字符串的指针，该字符串指定操作的默认(工作)目录。如果该值为空，则使用当前工作目录。如果在 lpFile 中提供了相对路径，请不要为 lpDirectory 使用相对路径。

类型: **INT**
指定应用程序打开时如何显示的标志。如果 lpFile 指定了一个文档文件，这个标志就被简单地传递给相关的应用程序。应该由应用程序决定如何处理它。这些值是在 Winuser.h 中定义的。在我们的例子中，使用了 SW_SHOWNORMAL 来激活和显示一个窗口。如果窗口最小化或最大化，窗口会将其恢复到原始大小和位置。应用程序应该在第一次显示窗口时指定此标志。

**返回值**
类型: **HINSTANCE**
如果函数成功，则返回值大于 32。如果函数失败，它将返回一个错误值，指出失败的原因。返回值被转换为 HINSTANCE，以便与 16 位 Windows 应用程序向后兼容。然而，这并不是一个真实的立场。

示例:

```cpp
Input : A list of URLs stored in a text file.
Output : All the URLs opened in different tabs.

```

```cpp
// C++ program to list URLs in a text file and
// open them.
// This program is written only for Microsoft
// Windows OS
#include <bits/stdc++.h>
#include <windows.h>
using namespace std;

int main()
{
    long long int s, i, x, c = 0;
    char temp[1000];

    // Name of the text file which contains all the
    // URLs separated by end line.
    ifstream all_lines("urls.txt");
    string line; // To get each line of the file as a string.

    while (getline(all_lines, line, 'n'))
    {
        x = 0; // For getting each character of a string.
        s = line.size(); // Measuring size of each string.

        // Here we limit number of tabs to 10, we can
        // change the value of c according to your
        // requirement.
        for (i = 0; i <= s && c < 10; i++) {
            if (line[i] != 't' && line[i] != '\0')
            {
                temp[x] = line[i];
                x++ ;
            }
            else
            {
                temp[x] = '\0'; ShellExecute(NULL, "open", temp, NULL,
                                                  NULL, SW_SHOWNORMAL);

                // Keeping a count of number of tabs
                // getting opened.
                c++ ;
            }
        }
    }
    system("pause");
    return 0;
}
```

输出:

```cpp
List of all urls present in the urls.txt file opened in different tabs.

```

**注意:**在像 Codeblocks 这样的一些 C++ 编辑器中运行上面的代码，文本文件和代码应该出现在同一个文件夹中。

**参考:**[https://msdn . Microsoft . com/en-us/library/windows/desktop/bb 762153(v = vs . 85)。aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/bb762153(v=vs.85).aspx)

本文由 **[阿迪蒂亚·古普塔](https://www.linkedin.com/in/aditya-gupta-437504a7?trk=hp-identity-name)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。