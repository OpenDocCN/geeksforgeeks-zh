# C# 环境类 SetEnvironmentVariable()方法示例

> 原文:[https://www . geesforgeks . org/c-sharp-environment-class-setenvironmentvariable-method-with-examples/](https://www.geeksforgeeks.org/c-sharp-environment-class-setenvironmentvariable-method-with-examples/)

环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统引导以来的时间(以毫秒为单位)信息。这个类提供不同类型的方法和属性，SetEnvironmentVariable()方法就是其中之一。此方法用于创建、删除或修改环境变量。该方法以两种不同的方式重载:

**1。SetEnvironmentVariable(String，String):** 通过使用 SetEnvironmentVariable()方法，我们可以创建、删除或修改当前进程中存储的环境变量。

**语法**:

```cs
public static void SetEnvironmentVariable (string varstr, string? val);
```

其中该方法采用两个名为 varstr 和 val 的参数。这里，varstr 表示环境变量的名称，val 表示要分配给 varstr 的值。

**异常:**这个方法会抛出以下异常:

*   **SecurityException:** 只有当调用方没有执行此操作的给定权限时，才会发生此异常。
*   **ArgumentNullException:** 当 varstr 为空时会出现此异常。
*   **ArgumentException:** 当 varstr 包含零长度字符串或等号时，会出现此异常。或者 varstr 和 val 的长度大于或等于 32，767 个字符。或者在执行该操作时出现错误。

**2。SetEnvironmentVariable(String，String，EnvironmentVariableTarget):** 此方法用于修改、创建或删除存储在当前进程或为当前用户或本地机器保留的 Windows OS 注册表项中的环境变量。

**语法:**

```cs
public static void SetEnvironmentVariable (string varstr, string? val, EnvironmentVariableTarget t);
```

这里，varstr 表示环境变量的名称，val 表示要分配给 varstr 的值。t 代表环境变量的位置。

**异常:**这个方法会抛出以下异常:

*   **SecurityException:** 只有当调用方没有执行此操作的给定权限时，才会发生此异常。
*   **ArgumentNullException:** 当 varstr 为空时会出现此异常。
*   **ArgumentException:** 当 varstr 包含零长度字符串或等号时，会出现此异常。或者 varstr 和 val 的长度大于或等于 32，767 个字符。或者在执行该操作时出现错误。或者 t 不是 EnvironmentVariableTarget 的成员。

**示例:**

## C#

```cs
// C# program to illustrate the use of 
// SetEnvironmentVariable() method 
using System;
using System.IO;

class GFG{

static public void Main()
{

    // Declare variable 
    string variable = "Geeks";

    // Declare value
    string value = "True";

    // Check whether the value stored in environment variable
    if (Environment.GetEnvironmentVariable(variable) == null)
    {
        Environment.SetEnvironmentVariable(variable, value);
        Console.WriteLine("In environment variable, the value is stored");
    }
    else
    {
        Console.WriteLine("In environment variable, the value is already stored");
    }
}
}
```

**输出:**

```cs
In environment variable, the value is stored
```