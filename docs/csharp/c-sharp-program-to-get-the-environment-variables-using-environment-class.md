# 使用环境类获取环境变量的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-程序获取环境变量-使用环境类/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-environment-variables-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用一些预定义的方法，我们可以使用环境类获得操作系统的信息，而 **GetEnvironmentVariable()** 方法就是其中之一。此方法用于查找环境变量。它以两种不同的方式过载:

**1。GetEnvironmentVariable(String):**该方法用于查找当前进程的环境变量。它会找到所有环境变量及其值。请始终记住，环境变量的名称在 macOS 和 Linux 中区分大小写，但在 Windows 中，它们不区分大小写。

**语法:**

```cs
public static string? GetEnvironmentVariable (string varstring);
```

其中 varstring 参数是字符串类型，它将表示环境变量的名称。

**返回:**这个方法将返回环境变量的名称。或者在找不到环境变量时返回 null。

**异常:**此方法将引发以下异常:

*   **Security exception:** This exception only occurs when the caller does not have the given permission to perform this operation.
*   [T0】 ArgumentNullException: 【T1] This exception will occur when the variable is empty.

**2。GetEnvironmentVariable(String，EnvironmentVariableTarget):** 此方法用于查找当前进程的环境变量，或者从本地机器或当前用户的 Windows OS 注册表项中查找。请始终记住，环境变量的名称在 macOS 和 Linux 中区分大小写，但在 Windows 中，它们不区分大小写。

**语法:**

```cs
public static string? GetEnvironmentVariable (string varstr, EnvironmentVariableTarget t);
```

这个方法将两个参数命名为 varstr 和 t .这里， *varstr* 代表环境变量的名称， *t* 代表环境变量的目标值。

**返回:**这个方法将返回环境变量的名称。或者在找不到环境变量时返回 null。

**异常:**此方法将引发以下异常:

*   **Security exception:** This exception only occurs when the caller does not have the given permission to perform this operation.
*   [T0】 ArgumentNullException: 【T1] This exception will occur when the variable is empty.
*   **Parameter exception:** This exception will occur when the target is not a valid target value of the environment variable.

**例:**

## c#

```cs
// C# program to illustrate how to find the 
// environment variables Using Environment Class
using System;
using System.Collections;

class GFG{

static public void Main()
{

    // Create a IDictionary to get the environment variables
    IDictionary data = Environment.GetEnvironmentVariables();

    // Display the details with key and value
    foreach (DictionaryEntry i in data)
    {
        Console.WriteLine("{0}:{1}", i.Key, i.Value);
    }
}
}
```

**输出:**

```cs
USER:priya
GOPATH:/Users/priya/Documents/go
rvm_stored_umask:022
rvm_version:1.29.12 (latest)
HOME:/Users/priya
rvm_bin_path:/Users/priya/.rvm/bin

Press any key to continue...
```