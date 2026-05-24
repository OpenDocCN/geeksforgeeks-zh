# 在 C/C++ 中重命名函数

> 原文:[https://www.geeksforgeeks.org/rename-function-in-ccpp/](https://www.geeksforgeeks.org/rename-function-in-ccpp/)

rename()函数用于更改文件或目录的名称，即从 **old_name** 更改为 **new_name** ，而不更改文件中存在的内容。这个函数以文件名作为参数。
如果 **new_name** 是同一文件夹中现有文件的名称，则该功能可能会失败或覆盖现有文件，具体取决于具体的系统和库实现。
**语法:**

```cpp
int rename (const char *old_name, const char *new_name);

Parameters:
old_name : Name of an existing file to be renamed.
new_name : String containing new name of the file.

```

**Return:**
函数的 Return 类型为整数。如果文件重命名成功，则返回零。失败时，返回非零值。

假设我们有一个名为 **geeks.txt** 的文本文件，有一些内容。因此，我们将使用下面的 C 程序重命名这个文件，该程序位于这个文件所在的文件夹中。

![](img/f943dc3cbdf245f238943cadf111943b.png)

```cpp
// C program to demonstrate use of rename()
#include<stdio.h>

int main()
{
    // Old file name
    char old_name[] = "geeks.txt";

    // Any string
    char new_name[] = "geeksforgeeks.txt";
    int value;

    // File name is changed here
    value = rename(old_name, new_name);

    // Print the result
    if(!value)
    {
        printf("%s", "File name changed successfully");
    }
    else
    {
        perror("Error");
    }
    return 0;
}
```

输出:

```cpp
If file name changed
File name changed successfully
            OR
If file name not changed
Error: No such file or directory

```

![](img/f4145da0c5b9902c397829a959538319.png)