# 在目录中搜索文件的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-search-for-a-file-in-a-directory/](https://www.geeksforgeeks.org/java-program-to-search-for-a-file-in-a-directory/)

在 Java 中搜索文件可以使用 `File` 类和 `FilenameFilter` 接口来执行。`FilenameFilter` 接口用于从文件列表中过滤文件。这个接口有一个方法 `boolean accept(File dir, String name)`，实现这个方法是为了从 `java.io.File.list()` 方法返回的列表中找到想要的文件。当我们想要在一个文件夹中找到具有特定扩展名的文件时，这种方法非常有用。

## 第一种方法

1.  创建一个实现 `FilenameFilter` 接口的类 `MyFilenameFilter`，并重写 `FilenameFilter` 接口的 `accept()` 方法。
2.  `accept()` 方法有两个参数，第一个是目录名，第二个是文件名。
3.  如果文件名以指定的首字母开头，则 `accept()` 方法返回 `true`，否则返回 `false`。
4.  类 `FindFile` 包含主方法，用于接受用户输入，例如要搜索的目录和要搜索文件的首字母。
5.  `File` 类的目录对象通过目录名初始化，`MyFilenameFilter` 类的过滤器对象通过用户提供的首字母初始化。
6.  在 `dir` 对象上调用 `list()` 方法，以返回符合条件的文件数组。
7.  遍历数组，并将所需文件的名称打印到输出屏幕。

## 代码实现

### Java

```java
// Java Program to Search for a File in a Directory
import java.io.*;

// MyFilenameFilter class implements FilenameFilter
// interface
class MyFilenameFilter implements FilenameFilter {

    String initials;

    // constructor to initialize object
    public MyFilenameFilter(String initials)
    {
        this.initials = initials;
    }

    // overriding the accept method of FilenameFilter
    // interface
    public boolean accept(File dir, String name)
    {
        return name.startsWith(initials);
    }
}

public class Main {

    public static void main(String[] args)
    {
        // Create an object of the File class
        // Replace the file path with path of the directory
        File directory = new File("/home/user/");

        // Create an object of Class MyFilenameFilter
        // Constructor with name of file which is being
        // searched
        MyFilenameFilter filter
            = new MyFilenameFilter("file.cpp");

        // store all names with same name
        // with/without extension
        String[] flist = directory.list(filter);

        // Empty array
        if (flist == null) {
            System.out.println(
                "Empty directory or directory does not exists.");
        }
        else {

            // Print all files with same name in directory
            // as provided in object of MyFilenameFilter
            // class
            for (int i = 0; i < flist.length; i++) {
                System.out.println(flist[i]+" found");
            }
        }
    }
}
```