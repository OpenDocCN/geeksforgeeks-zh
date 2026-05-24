# 控制台。C# 中的 OpenStandardOutput()方法，带示例

> 原文:[https://www . geesforgeks . org/console-open standard output-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/console-openstandardoutput-method-in-c-sharp-with-examples/)

**控制台。OpenStandardOutput 方法**用于获取标准输出流。C# 中有两种 OpenStandardOutput 方法重载，如下所示:

*   **OpenStandardOutput()方法**
*   **OpenStandardOutput(int32)方法**

### OpenStandardOutput()方法

它用于获取标准输出流。

> **语法:**公共静态系统。IO . Stream openstandard output()；
> **参数:**此方法不接受任何参数。
> **返回值:**此方法返回标准输出流。

**示例:**

```cs
// C# program to illustrate the
// Console.OpenStandardOutput()
// method
using System;
class GFG
{
    static void Main(string[] args)
    {
        // use of Console.OpenStandardOutput() method
        // to print the Geeksforgeeks
        // BeginWrite returns an IAsyncResult that represents
        //  the asynchronous write
        // int32 value like 071, 101 represents the 
        // ascii value of Geeksforgeeks
        if (System.Console.OpenStandardOutput().BeginWrite(new byte[] { 071, 101,101, 
            107,115, 102, 111, 114, 103, 101,101, 
            107,115, 0 },0, 
            13, null, null).AsyncWaitHandle.WaitOne()) 
        { 
        }
    }
}
```

**输出:**

```cs
Geeksforgeeks
```

### OpenStandardOutput(Int32)方法

它用于获取标准输出流，该输出流被设置为指定的缓冲区大小。

> **语法:**公共静态系统。流开放标准输出；
> **参数:**该方法接受以下参数。
> 
> *   **缓冲区大小:**该参数是内部流缓冲区大小。
> 
> **返回值:**此方法返回标准输出流。
> **异常:**如果缓冲区大小小于或等于零，此方法将给出 ArgumentOutOfRangeException。

**示例:**它用制表符替换字符串中的 2 个连续空格字符。

```cs
// C# program to illustrate the 
// Console.OpenStandardOutput(int32) method
using System;
using System.IO;

public class GFG
{
    // size of tab
    private const int Val1 = 2;

    // working string
    private const string Val_Text = "Geeks for Geeks";

    // main function
    public static int Main(string[] args)
    {
        // check for the argument
        if (args.Length < 2)
        {
            Console.WriteLine(Val_Text);
            return 1;
        }

        try
        {
            // replacing space characters in a string with
            // a tab character
            using (var wrt1 = new StreamWriter(args[1]))
            {
                using (var rdr1 = new StreamReader(args[0]))
                {
                    Console.SetOut(wrt1);
                    Console.SetIn(rdr1);
                    string line;
                    while ((line = Console.ReadLine()) != null)
                    {
                        string newLine = line.Replace(("").PadRight(Val1, ' '), "\t");
                        Console.WriteLine(newLine);
                    }
                }
            }
        }
        catch(IOException e)
        {
            TextWriter errwrt = Console.Error;
            errwrt.WriteLine(e.Message);
            return 1;
        }

        // use of OpenStandardOutput() method
        var standardOutput = new StreamWriter(Console.OpenStandardOutput());
        standardOutput.AutoFlush = true;

        // set the output
        Console.SetOut(standardOutput);
        Console.WriteLine("OpenStandardOutput Example");
        return 0;
    }
}
```

**输出:**

```cs
Geeks for Geeks
```