# C# |数组 IndexOutofRange 异常

> 哎哎哎:# t0]https://www . geeksforgeeks . org/c-sharp 数组 indexoutofrange-exception/

C# 支持数组的创建和操作，作为一种数据结构。数组的索引是一个整数值，其值在区间[0，n-1]内，其中 n 是数组的大小。如果请求一个负数或大于或等于数组大小的索引，那么 C# 抛出一个*系统。IndexOutOfRange* 异常。这与 C/C++不同，在 C/c++中，没有进行绑定检查的索引。 *IndexOutOfRangeException 是一个运行时异常*，只在运行时抛出。C# 编译器在编译程序时不会检查此错误。

**示例:**

```cs
// C# program to demonstrate the 
// IndexOutofRange Exception in array
using System;

public class GFG {

    // Main Method
    public static void Main(String[] args)
    {
        int[] ar = {1, 2, 3, 4, 5};

        // causing exception
        for (int i = 0; i <= ar.Length; i++)
            Console.WriteLine(ar[i]);
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。IndexOutOfRangeException:索引超出了数组的界限。
> 在 GFG。主(系统。字符串[]参数)<filename unknown="">中的<0x 40 bdbd 50+0x 00067>:0
> 【错误】致命未处理异常:系统。IndexOutOfRangeException:索引超出了数组的界限。
> 在 GFG。主(系统。字符串[]args)<0x 40 bdbd 50+0x 00067<filename unknown="">中的>:0</filename>0x 40 bdbd 50>T7】0x 40 bdbd 50></filename>

**输出:**

```cs
1
2
3
4
5

```

这里如果你仔细看，数组的大小是 5。因此，当使用 for 循环访问它的元素时，索引的最大值可以是 4，但是在我们的程序中，它一直到 5，因此是异常。

让我们看看另一个使用数组列表的例子:

```cs
// C# program to demonstrate the 
// IndexOutofRange Exception in array
using System;
using System.Collections;

public class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // using ArrayList
        ArrayList lis = new ArrayList();
        lis.Add("Geeks");
        lis.Add("GFG");
        Console.WriteLine(lis[2]);
    }
}
```

**运行时错误:**这里的错误比前一个错误信息更丰富，如下所示:

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:系统中的索引
> 。GFG<filename unknown="">0
> 中的 collections . ArrayList . get _ Item(int 32 index)<0x7f2d 36 B2 ff 40+0x 00082>。主(系统。字符串[]参数)< 0x41b9fd50 + 0x0008b >在<filename unknown="">中:0
> 【错误】致命未处理异常:系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:系统处的索引
> 。集合. ArrayList.get_Item (Int32 索引)< 0x7f2d36b2ff40 + 0x00082 >在<filename unknown="">中:0
> 在 GFG。主(系统。字符串[]args)<0x 41 B9 FD 50+0x 0008 b>在<filename unknown="">中:0</filename>0x 41 B9 FD 50>T13】0x7f 2d 36 B2 ff 40>T14】0x 41 B9 FD 50>T15】0x7f 2d 36 B2 ff 40></filename></filename></filename>

**让我们详细了解一下:**

*   这里的索引定义了我们试图访问的索引。
*   大小给了我们列表大小的信息。
*   由于大小是 2，我们可以访问的最后一个索引是(2-1)=1，因此是例外

**正确的数组访问方式是:**

```cs
for (int i = 0; i < ar.Length; i++) 
{
}

```

**异常处理:**

*   【for-each 循环:这将在访问数组元素时自动处理索引。
    *   **语法:**

        ```cs
        for(int variable_name in array_variable)
        {
             // loop body
        }

        ```

*   **使用 Try-Catch:** 考虑将代码封装在 Try-Catch 语句中，并相应地操作异常。如上所述，C# 不会让您访问无效的索引，并且肯定会抛出 IndexOutOfRangeException。但是，我们应该在 catch 语句的块内小心，因为如果我们不适当地处理异常，我们可能会隐藏它，从而在您的应用程序中创建一个 bug。