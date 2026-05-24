# 使用环境类获取当前目录完整路径的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-to-get-the-full-path-of-the-current-directory-using-environment-class/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-full-path-of-the-current-directory-using-environment-class/)

在 C# 中，`Environment`类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它：它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间（以毫秒为单位）信息。在本文中，我们将讨论如何获取当前目录的完整路径。所以为了解决这个问题，我们使用`Environment`类的`CurrentDirectory`属性。此属性返回计算机当前工作目录的完整路径。此属性还引发以下异常：

*   `ParameterException`：当`CurrentDirectory`属性尝试被设置为空字符串时，将引发此异常。
*   `ArgumentNullException`：当`CurrentDirectory`属性尝试被设置为`null`时，将引发此异常。
*   `IOException`：当发生输入输出错误时，引发此异常。
*   `DirectoryNotFoundException`：当`CurrentDirectory`属性尝试设置为找不到的本地路径/地址时，将引发此异常。
*   `SecurityException`：当调用者没有适当权限时，引发此异常。

## 语法

`Environment.CurrentDirectory`

## 返回类型

该属性的返回类型为`string`。返回的字符串表示当前目录路径。

## 例

### C\#

```cs
// C# program to find the current directory path
// Using Environment Class
using System;

class GFG{

    static public void Main()
    {

        // Declaring a string
        string resultPath = "";

        // Get the complete path of the current
        // working directory. Using 
        // CurrentDirectory property of 
        // Environment class
        resultPath = Environment.CurrentDirectory;

        Console.WriteLine("System Directory:\n" + resultPath);
    }
}
```

### 输出

```cs
System Directory:
/Users/Projects/newprogram/
```