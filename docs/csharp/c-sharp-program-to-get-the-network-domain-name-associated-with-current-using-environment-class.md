# C# 程序获取与当前使用环境类关联的网络域名

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-get-network-domain-name-associated-current-use-environment-class/](https://www.geeksforgeeks.org/c-sharp-program-to-get-the-network-domain-name-associated-with-current-using-environment-class/)

在 C# 中，环境类提供关于当前平台的信息，并操纵当前平台。它对于获取和设置各种操作系统相关信息非常有用。我们可以这样使用它:它检索命令行参数信息、退出代码信息、环境变量设置信息、调用堆栈信息的内容以及自上次系统启动以来的时间(以毫秒为单位)信息。通过使用一些预定义的方法，我们可以使用环境类获得操作系统的信息。在本文中，我们将获取与当前用户相关联的网络域名。所以我们使用环境类的 **UserDomainName** 属性。此属性用于获取与当前用户关联的网络域名。如果操作系统不允许检索网络域名，它将引发 PlatformNotSupportedException 如果此属性不检索网络域名，它还将引发 InvalidOperationException。

**语法** :

> 环境。
> 
> 用户域名

**返回类型:**该属性的返回类型为字符串。返回的字符串表示网络域名。

**例**

## c#

```cs
// C# program to find the network domain name 
// associated with current user. Using the 
// Environment Class
using System;

class GFG{

static public void Main()
{

    // Declare a variable
    string resultName;

    // Find the network domain name 
    // Using the UserDomainName property 
    // of Environment class
    resultName = Environment.UserDomainName;

    // Display the result
    Console.WriteLine("Network domain name: " + resultName);
}
}
```

**输出:**

```cs
Network domain name: Check
```