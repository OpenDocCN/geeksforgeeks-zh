# Java 中 `getPath()` 和 `getAbsolutePath()` 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-getpath-and-getabsolutepath-in-java/](https://www.geeksforgeeks.org/difference-between-getpath-and-getabsolutepath-in-java/)

`getPath()`：`getPath()` 方法是 `File` 类的一部分。这个函数返回给定文件对象的路径。该函数返回一个包含给定文件对象路径的字符串对象。

**返回类型：**

```java
The string form of an abstract pathname
```

`getAbsolutePath()`：`getAbsolutePath()` 返回一个路径对象，表示给定路径的绝对路径。如果给定的路径名已经是绝对的，那么路径名字符串就像是由 `getPath()` 方法返回的一样。如果当前抽象路径名是空的抽象路径名，则返回当前用户目录的路径名字符串（由系统属性命名）。否则，该路径名将以依赖于系统的方式解析。

**在 Unix 系统上：**

> 通过根据当前用户目录解析相对路径名，相对路径名成为绝对路径名。

**在微软系统上：**

> 相对路径名通过根据路径名命名的驱动器的当前目录进行解析而成为绝对路径名，并根据当前用户目录进行解析。

**返回：**

> 绝对路径名字符串，表示与此抽象路径名相同的文件或目录

### `getPath()` 和 `getAbsolutePath()` 之间的区别

| | `getPath()` | `getAbsolutePath()` |
| :--- | :--- | :--- |
| **1** | 此方法返回一个字符串，该字符串表示由文件对象表示的文件的（绝对或相对）路径名。 | 此方法返回抽象文件路径名的绝对路径名字符串。 |
| **2** | 如果文件对象是使用绝对路径创建的，那么返回的路径就是绝对路径。 | 如果抽象路径名已经是绝对路径名，则返回相同的路径名字符串。 |
| **3** | 如果文件对象是使用相对路径创建的，那么返回的路径就是相对路径。 | 如果抽象路径名是相对的，那么它是以系统相关的方式解析的。 |
| **4** | **示例（在 Windows 系统上）：**<br>如果提供了绝对路径：<br>`File filePath1 = new File("C:\\Users\\ASPIRE\\Desktop\\Java Folder\\demo.txt");`<br>**输出：** `C:\Users\ASPIRE\Desktop\Java Folder\demo.txt`<br>如果提供了相对路径：<br>`File filePath2 = new File("..\\demo.txt");`<br>**输出：** `..\demo.txt` | **示例（在 Windows 系统上）：**<br>如果提供了绝对路径：<br>`File filePath1 = new File("C:\\Users\\ASPIRE\\Desktop\\Java Folder\\demo.txt");`<br>**输出：** `C:\Users\ASPIRE\Desktop\Java Folder\demo.txt`<br>如果提供了相对路径：<br>`File filePath2 = new File("..\\demo.txt");`<br>**输出：** `C:\Users\ASPIRE\Desktop\Java Folder\..\demo.txt` |
| **5** | **示例（在 Unix 系统上）：**<br>如果提供了绝对路径：<br>`File filePath1 = new File("home/Pooja/Desktop/Java Folder/demo.txt");`<br>**输出：** `home/Pooja/Desktop/Java Folder/demo.txt`<br>如果提供了相对路径：<br>`File filePath2 = new File("../demo.txt");`<br>**输出：** `../demo.txt` | **示例（在 Unix 系统上）：**<br>如果提供了绝对路径：<br>`File filePath1 = new File("home/Pooja/Desktop/Java Folder/demo.txt");`<br>**输出：** `home/Pooja/Desktop/Java Folder/demo.txt`<br>如果提供了相对路径：<br>a) `File filePath2 = new File("../demo.txt");`<br>**输出：** `../demo.txt`<br>b) `File filePath2 = new File("../Document/ABC.txt");`<br>**输出：** `/home/pooja/Document/abc.txt` |