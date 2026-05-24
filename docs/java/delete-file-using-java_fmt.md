# 使用 Java 删除文件

> 原文：[https://www.geeksforgeeks.org/delete-file-using-java/](https://www.geeksforgeeks.org/delete-file-using-java/)

Java 提供了使用 Java 程序删除文件的方法。与任何操作系统中的正常删除操作相反，使用 Java 程序删除的文件将被永久删除，而不会被移动到废纸篓/回收站。以下是用 Java 删除文件的方法：

## 方法一：使用 `java.io.File.delete()`

`java.io.File.delete()` 函数用于删除此抽象路径名表示的文件或目录。

**语法：**

```java
public boolean delete()
```

返回值：如果文件或目录被成功删除则返回 `true`；否则返回 `false`。

**示例代码：**

```java
// Java program to delete a file
import java.io.*;

public class Test {
    public static void main(String[] args) {
        File file = new File("C:\\Users\\Mayank\\Desktop\\1.txt");

        if(file.delete()) {
            System.out.println("File deleted successfully");
        } else {
            System.out.println("Failed to delete the file");
        }
    }
}
```

**输出：**

```
File deleted successfully
```

## 方法二：使用 `java.nio.file.Files.deleteIfExists(Path)`

使用在 `java.nio.file` 包中定义的 `Files.deleteIfExists(Path p)` 方法。该方法删除存在的文件。只有当目录不为空时，它才会删除路径中提到的目录。

**语法：**

```java
public static boolean deleteIfExists(Path path) throws IOException
```

参数：`path` - 要删除文件的路径。
返回值：如果文件被此方法删除则返回 `true`；如果文件因不存在而无法删除则返回 `false`。
抛出：
- `DirectoryNotEmptyException` - 如果文件是一个目录，并且因为目录不为空而无法以其他方式删除（可选特定异常）。
- `IOException` - 如果发生 I/O 错误。

**示例代码：**

```java
// Java program to demonstrate delete using Files class
import java.io.IOException;
import java.nio.file.*;

public class Test {
    public static void main(String[] args) {
        try {
            Files.deleteIfExists(Paths.get("C:\\Users\\Mayank\\Desktop\\445.txt"));
        } catch(NoSuchFileException e) {
            System.out.println("No such file/directory exists");
        } catch(DirectoryNotEmptyException e) {
            System.out.println("Directory is not empty.");
        } catch(IOException e) {
            System.out.println("Invalid permissions.");
        }

        System.out.println("Deletion successful.");
    }
}
```

**输出：**

```
Deletion successful.
```

**参考：**

*   Oracle

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。