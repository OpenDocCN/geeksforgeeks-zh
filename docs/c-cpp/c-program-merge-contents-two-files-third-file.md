# 将两个文件的内容合并成第三个文件的 C 程序

> 原文:[https://www . geesforgeks . org/c-program-merge-contents-two-files-third-file/](https://www.geeksforgeeks.org/c-program-merge-contents-two-files-third-file/)

假设给定的两个文件是 file1.txt 和 file2.txt。
1)以读取模式打开 file1.txt 和 file2.txt。
2)以写入模式打开 file3.txt。
3)对文件 1.txt 到文件 3.txt 的一个个复制字符运行循环
4)对文件 2.txt 到文件 3.txt 的一个个复制字符运行循环
5)关闭所有文件。

要成功运行以下程序，file1.txt 和 fil2.txt 必须存在于同一个文件夹中。

```cpp
#include <stdio.h>
#include <stdlib.h>

int main()
{
   // Open two files to be merged
   FILE *fp1 = fopen("file1.txt", "r");
   FILE *fp2 = fopen("file2.txt", "r");

   // Open file to store the result
   FILE *fp3 = fopen("file3.txt", "w");
   char c;

   if (fp1 == NULL || fp2 == NULL || fp3 == NULL)
   {
         puts("Could not open files");
         exit(0);
   }

   // Copy contents of first file to file3.txt
   while ((c = fgetc(fp1)) != EOF)
      fputc(c, fp3);

   // Copy contents of second file to file3.txt
   while ((c = fgetc(fp2)) != EOF)
      fputc(c, fp3);

   printf("Merged file1.txt and file2.txt into file3.txt");

   fclose(fp1);
   fclose(fp2);
   fclose(fp3);
   return 0;
}
```

输出:

```cpp
Merged file1.txt and file2.txt into file3.txt
```

**相关文章:**

*   [Java 程序将两个文件交替合并成第三个文件](https://www.geeksforgeeks.org/java-program-merge-two-files-alternatively-third-file/)
*   [Java 程序将两个文件合并成第三个文件](https://www.geeksforgeeks.org/java-program-merge-two-files-third-file/)

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论