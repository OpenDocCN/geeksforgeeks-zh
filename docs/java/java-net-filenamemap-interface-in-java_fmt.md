# java.net.FileNameMap 接口

> 原文：[https://www.geeksforgeeks.org/java-net-filenamemap-interface-in-java/](https://www.geeksforgeeks.org/java-net-filenamemap-interface-in-java/)

`java.net.FileNameMap` 是一个 Java [接口](https://www.geeksforgeeks.org/interfaces-in-java/)。`FileNameMap` 接口是 `java.net` 包的一部分。`FileNameMap` 提供了一种在文件名和 MIME 类型字符串之间进行映射的机制。我们可以使用 `FileNameMap.getContentTypeFor` 方法来获取指定文件的 [MIME 类型](https://www.geeksforgeeks.org/mime-media-types/)。

**语法：**

```java
public interface FileNameMap
```

## 方法

`java.net.FileNameMap` 接口只包含一个名为以下的方法：

**`getContentTypeFor(String fileName)` 方法** — 它是 `java.net.FileNameMap` 接口的一部分。顾名思义，`getContentTypeFor` 用于获取特定文件的字符串格式的 MIME 类型。

**语法：**

```java
String getContentTypeFor(String fileName)
```

**方法参数：** 该方法只有一个 `String` 类型的参数。

**方法返回类型：** 它有一个 `String` 返回类型，将返回文件的 MIME 类型。

## 如何调用 getContentTypeFor 方法？

**步骤 1：** 使用 `URLConnection.getFileNameMap()` 静态方法从数据文件中加载 `FileNameMap`。

```java
FileNameMap fileNameMap = URLConnection.getFileNameMap();
```

**步骤 2：** 它调用 `fileNameMap.getContentTypeFor(String fileName)` 方法，并传递文件名以获得它的 MIME 类型。

```java
String mimeType = fileNameMap.getContentTypeFor(nameOfTheFile);
```

**示例：** 下面是 Java 程序，用于更好地理解 `FileNameMap` 接口，然后使用 `FileNameMap.getContentTypeFor()` 方法获取文件的 MIME 类型。

```java
// Java program to demonstrate the
// working of the FileNameMap interface

import java.io.*;
import java.net.*;

class GFG {
    public static void main(String[] args)
    {
        try {
            FileNameMap fileNameMap
                = URLConnection.getFileNameMap();

            // specify all the fileName whose
            // MIME type we need to know
            String firstFileName = "tmp.txt";
            String secondFileName = "profile.png";
            String thirdFileName = "gfg.mp4";

            // call getContentTypeFor() method for each
            // fileName to get it's MIME type, method will
            // return null if fileName is invalid
            String firstFileMimeType = fileNameMap.getContentTypeFor(firstFileName);
            String secondFileMimeType = fileNameMap.getContentTypeFor(secondFileName);
            String thirdFileMimeType = fileNameMap.getContentTypeFor(thirdFileName);

            // print all the MIME types
            System.out.println("Mime type of "
                               + firstFileName + " is "
                               + firstFileMimeType);
            System.out.println("Mime type of "
                               + secondFileName + " is "
                               + secondFileMimeType);
            System.out.println("Mime type of "
                               + thirdFileName + " is "
                               + thirdFileMimeType);
        }
        catch (Exception e) {
            System.out.println("Some Exception "
                               + e.getMessage());
        }
    }
}
```

**输出：**

```java
Mime type of tmp.txt is text/plain
Mime type of profile.png is image/png
Mime type of gfg.mp4 is video/mp4
```