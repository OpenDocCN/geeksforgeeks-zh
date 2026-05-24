# 通过覆盖相同文件名将一个文件的内容复制到另一个文件的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-通过覆盖相同文件名将一个文件的内容复制到另一个文件中/](https://www.geeksforgeeks.org/c-sharp-program-to-copy-content-of-one-file-to-another-file-by-overwriting-same-file-name/)

给定一个文件，现在我们的任务是通过使用 C# 覆盖相同的文件名，将数据从一个文件复制到另一个文件。因此，我们使用以下方法来执行此任务:

**1。** [**Copy(String、String、Boolean)**](https://www.geeksforgeeks.org/file-copystring-string-boolean-method-in-c-sharp-with-examples/?ref=rp)**:**It**用于将一个文件的内容复制到有覆盖的新文件中。**

****语法**:**

> **文件。副本(Myfile1，Myfile2，owrite)；**

**其中，Myfile1 是第一个文件，Myfile2 是第二个文件，owrite 是一个布尔变量，如果目标文件可以被覆盖，则它被设置为 true，否则为 false。**

****2。ReadAllText(String):** 它打开一个文本文件，然后读取其中存在的数据，然后关闭该文件。即使出现异常，该方法也肯定会关闭文件句柄。**

> **文件。ReadAllText(我的路径)**

**其中 Mypath 是我们要读取的文件的位置。它是字符串类型。**

**让我们考虑一下源文件夹和目标文件夹中名为 sai.txt 的两个文件**

**来源(第一):**

```cs
Hello Geeks welcome to c#.
```

**目的地(最后一个):**

```cs
Hello Geeks welcome to java/php.
```

**现在，我们的任务是用源内容覆盖最后一个文件，因此我们使用以下方法。**

****进场:****

> ***   Declare variables*   Use the ReadAllText () method to read the source file and the target file.**
> 
> ```cs
> file = File.ReadAllText("first/sai.TXT");
> file = File.ReadAllText("last/sai.TXT");
> ```
> 
> *   Copy the file by overwriting the source file (first one) with the copy () method.
> 
> ```cs
>  File.Copy("first/sai.TXT", "last/sai.TXT",true);
> ```
> 
> *   Use the ReadAllText () method to read the source and target files and display them.
> 
> ```cs
> file = File.ReadAllText("first/sai.TXT");
> file = File.ReadAllText("last/sai.TXT");
> ```**

****示例:****

## **C#**

```cs
// C# program to copy the data of one file to 
// another file by overwriting the same file name
using System;
using System.IO;

class GfG{

static void Main()
{

    // Declate file name
    string file;

    // Content in files before copying
    Console.WriteLine("Before copy:\n");
    file = File.ReadAllText("first/sai.TXT");
    Console.WriteLine("data in first:\n" + file);

    file = File.ReadAllText("last/sai.TXT");
    Console.WriteLine("data in last :\n" + file + "\n\n\n");

    // Copy file with overwriting
    File.Copy("first/sai.TXT", "last/sai.TXT", true);

    // Content in files after copying
    Console.WriteLine("After copy:\n");
    file = File.ReadAllText("first/sai.TXT");
    Console.WriteLine("data in first:\n" + file);

    file = File.ReadAllText("last/sai.TXT");
    Console.WriteLine("data in last :\n" + file + "\n\n\n");
}
}
```

****输出:****

```cs
Before copy:

data in first:
Hello Geeks welcome to c#.
data in last:
Hello Geeks welcome to java/php.

After copy:

data in first:
Hello Geeks welcome to c#.
data in last:
Hello Geeks welcome to c#.
```