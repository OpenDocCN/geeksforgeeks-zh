# 从流中读取数据并将数据转换为字符的 C# 程序

> 原文：[https://www.geeksforgeeks.org/c-sharp-program-for-reading-data-from-stream-and-cast-data-to-chars/](https://www.geeksforgeeks.org/c-sharp-program-for-reading-data-from-stream-and-cast-data-to-chars/)

给定数据，现在我们的任务是从流中读取数据，并将数据转换为 C# 中的字符。为此，我们使用以下类和方法：

### `FileStream`
是一个用来读写文件的类。因此，要使用 `FileStream` 操作文件，需要创建一个 `FileStream` 类的对象。

**语法**：
```cs
Stream object = new FileStream(path, FileMode.Open)
```
其中 `path` 是你文件的位置 – `@"c:\A\data.txt"`，`FileMode` 是文件的读写等模式。

### `ReadByte()`
该方法用于从文件中逐字节读取数据。当当前流不支持读取时，此方法将引发 `NotSupportException`。如果当前流已关闭，则此方法将引发 `ObjectDisposedException`。

**语法**：
```cs
FileStream_object.ReadByte()
```

### 示例
让我们考虑一个名为 `file.txt` 的文件存在于 C 盘的 A 文件夹中，如下图所示：

![](img/8bb4dba089960a7d66ca89537cfeefb2.png)

现在我们从流中读取数据，并将数据转换为字符。为此，请遵循以下方法。

### 方法
- 使用 `FileStream` 读取指定路径下名为 `file.txt` 的文件。
- 使用 `ReadByte()` 方法逐字节读取文件中的数据，直到到达文件末尾。
```cs
while ((obj = s.ReadByte()) != -1)
{
    // Convert the data into chars and display
    Console.Write("{0} ", (char)obj);
}
```
- 使用强制转换为 `char` 的方式将文件数据显示为字符。
```cs
(char)obj
```

## C# 示例代码
```cs
// C# program to read the data from stream
// and cast data to chars
using System;
using System.IO;

public sealed class GFG{
    public static void Main()
    {
        // Read the file from the specified path
        using (Stream s = new FileStream(@"c:\A\file.txt", FileMode.Open))
        {
            int obj;
            // Read the data in file byte by byte
            // Using ReadByte() method
            while ((obj = s.ReadByte()) != -1)
            {
                // Convert the data into chars and display
                Console.Write("{0} ", (char)obj);
            }
            Console.ReadLine();
        }
    }
}
```

**输出**：
```cs
T H I S  I S  F I L E  D E M O
```