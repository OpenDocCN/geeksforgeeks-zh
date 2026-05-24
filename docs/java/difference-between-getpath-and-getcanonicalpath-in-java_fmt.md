# Java 中 `getPath()` 和 `getCanonicalPath()` 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-getpath-and-getcanonicalpath-in-java/](https://www.geeksforgeeks.org/difference-between-getpath-and-getcanonicalpath-in-java/)

`getPath()` 方法是 `File` 类的一部分。这个函数返回给定文件对象的路径。该函数返回一个包含给定文件对象路径的字符串对象，而 `getCanonicalPath()` 方法是 `Path` 类的一部分。该函数返回给定文件对象的规范路径名。如果文件对象的路径名是规范的，那么它只返回当前文件对象的路径。规范路径总是绝对且唯一的，函数移除了“.”和“..”如果存在的话。现在，两种方法 `getPath()` 和 `getCanonicalPath()` 都是 `File` 类的一部分，都是获取文件系统路径的 `File` 方法。首先，我们从下面的文件结构中了解两种路径之间的区别。

**图示:** 考虑 windows 目录中的随机路径

```java
|--D:
   \--Article      
   \--Test
   \--Program
       \--Python
       \--JAVA
           \Program1.java
```

如果路径 `Python/../JAVA/Program1.java` 被传递，那么 Path 和规范路径的值如下。

*   **路径:** `Python\..\JAVA\Program1.java`
*   **规范路径:** `d:\Program\JAVA\Program1.java`

现在让我们理解这两种方法的区别。

## (一) 理论差异

| `getPath()` 方法 | `getCanonicalPath()` 方法 |
| --- | --- |
| 该函数以字符串形式返回抽象路径名。 | 该函数返回给定文件对象的规范路径名。 |
| 返回的路径名可能是绝对路径。 | 规范路径始终是绝对且唯一的路径。 |
| 如果字符串路径名用于创建文件对象，它只返回路径名。 | 如果需要，该方法首先将该路径名转换为绝对形式。为此，它将调用 `getAbsolutePath()` 方法，然后将其映射到其唯一的形式。 |
| 如果在文件对象的参数中使用了 URL，那么它将删除协议并返回文件名。 | 这个方法会移除多余的名称，例如 `.` 和 `..` 从路径名。它将解析符号链接，并将驱动器号转换为标准大小写。 |
| 这个方法不会抛出任何异常。 | 此方法引发以下异常。<br>*安全异常:* 如果无法访问需要的属性值。<br>*输入输出异常:* 如果出现输入输出异常。 |
| *示例:* `File f = new File("c:\\users\\..\\program\\.\\file1.txt")`<br>路径: `c:\users\..\program\.\file1.txt` | *示例:* `File f = new File("c:\\users\\..\\program\\.\\file1.txt")`<br>规范路径: `c:\program\file1.txt` |

## (二) 实际差异

### 示例

```java
// Java program to demonstrate the difference
// between getPath() and getCanonicalPath() function

// Importing input output classes
import java.io.*;

// Class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Try block to check exceptions
        try {

            // Creating a file object
            File f = new File(
                "g:\\gfg\\A(7)PATH\\Test\\..\\file1.txt");

            // Getting the Path of file object
            String path = f.getPath();

            // Getting the Canonical path of the file object
            String canonical = f.getCanonicalPath();

            // Display the file path of the file object
            // and also the Canonical path of file
            System.out.println("Path : " + path);
            System.out.println("Canonical path : "
                               + canonical);
        }

        // Catch block to handle if exception/s occurs
        catch (Exception e) {

            // Exception message is printed where occurred
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```java
Path (getPath()): g:\gfg\A(7)PATH\Test\..\file1.txt
path (getCanonicalPath()) : G:\gfg\A(7)PATH\file1.txt
```