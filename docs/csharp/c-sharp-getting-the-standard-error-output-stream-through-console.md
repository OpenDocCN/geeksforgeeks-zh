# C# |通过控制台获取标准错误输出流

> 原文:[https://www . geesforgeks . org/c-sharp-get-the-standard-error-output-stream-through-console/](https://www.geeksforgeeks.org/c-sharp-getting-the-standard-error-output-stream-through-console/)

给定一个普通的控制台，任务是在 C# 中通过这个控制台获取标准错误输出流。

**方法:**这可以使用 C# 中系统包的**控制台**类中的**错误**属性来完成。

**程序:**获取标准误差输出流

```cs
// C# program to illustrate the
// Console.Error Property
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GFG {

class Program {

    static void Main(string[] args)
    {

        // Get the Standard Error output Stream
        Console.WriteLine("Standard Error Output Stream: {0}",
                                               Console.Error);
    }
}
}
```

**输出:**

![](img/1062752e1e87a0c97b4efec620cc1b8e.png)

**注:****文字书写**代表可以书写一系列连续字符的书写者。