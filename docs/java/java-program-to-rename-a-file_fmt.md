# 重命名文件的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-rename-a-file/](https://www.geeksforgeeks.org/java-program-to-rename-a-file/)

更改文件的名称称为重命名文件。重命名操作可以使用属于 Java 中 `File` 类的 `renameTo()` 方法。

## A. `renameTo()` 方法

`renameTo()` 方法用于将文件的抽象路径名重命名为给定的路径名。方法返回一个布尔值，即如果文件被重命名，则返回 `true`，否则返回 `false`。

### 接近

1.  创建 `File` 类的对象，并用目录路径替换文件路径。
2.  创建 `File` 类的另一个对象，并用目录的重命名路径替换文件路径。
3.  使用 `renameTo()` 方法。
4.  如果重命名操作成功，则函数返回 `true`。
5.  否则返回 `false`。

下面是上述方法的实现。

```java
// Java Program to rename a file
import java.io.File;
public class GFG {
    public static void main(String[] args)
    {
        // Create an object of the File class
        // Replace the file path with path of the directory
        File file = new File("/home/mayur/Folder/GFG.java");

        // Create an object of the File class
        // Replace the file path with path of the directory
        File rename = new File("/home/mayur/Folder/HelloWorld.java");

        // store the return value of renameTo() method in flag
        boolean flag = file.renameTo(rename);

        // if renameTo() return true then if block is executed
        if (flag == true) {
            System.out.println("File Successfully Rename");
        }
        // if renameTo() return false then else block is executed
        else {
            System.out.println("Operation Failed");
        }
    }
}
```

**输出：**

```java
File Successfully Rename
```

**程序执行前**

![](img/a01861b5c0e9c5108693af7e06727009.png)

**程序执行后**

![](img/479f7e78b33591540f41f4784fd1a111.png)

## B. `move()` 方法

重命名文件可以通过将第一个文件的内容移动到一个新文件并删除以前的文件来完成。Java 正在使用 [`resolveSibling`](https://www.geeksforgeeks.org/path-resolvesibling-method-in-java-with-examples/) 方法处理这个操作。它是用来根据该路径的父路径解析给定路径。

```java
// Java Program to rename a file
import java.nio.file.*;
import java.io.IOException;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {
        Path oldFile
            = Paths.get("/home/mayur/Folder/GFG.java");

        try {
            Files.move(oldFile, oldFile.resolveSibling(
                                    "HelloWorld.java"));
            System.out.println("File Successfully Rename");
        }
        catch (IOException e) {
            System.out.println("operation failed");
        }
    }
}
```

**输出：**

```java
File Successfully Rename
```

**程序执行前**

![](img/a01861b5c0e9c5108693af7e06727009.png)

**程序执行后**

![](img/479f7e78b33591540f41f4784fd1a111.png)