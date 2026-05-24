# Java 中 getCanonicalPath() 和 getAbsolutePath() 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-getcanonicalpath-and-getabsolutepath-in-java/](https://www.geeksforgeeks.org/difference-between-getcanonicalpath-and-getabsolutepath-in-java/)

`getCanonicalPath()` 和 `getAbsolutePath()` 方法属于 `java` 中的 `java.io.File` 类。而这些方法基本上都是用来获取文件对象在系统目录结构中的路径。

## 绝对文件路径

**绝对文件路径**是文件对象的路径名。

*   如果我们使用抽象路径创建文件对象，绝对文件路径与抽象文件路径相同。
*   如果我们使用相对路径创建文件对象，那么绝对文件路径是根据当前目录分析相对路径后得到的路径。

## 规范文件路径

**规范文件路径**是文件对象的路径名。

*   如果我们使用抽象路径创建文件对象，规范文件路径与抽象文件路径相同。
*   如果我们使用相对路径创建文件对象，规范文件路径既是绝对路径中最短的，也是唯一的路径。

举个例子吧。比方说，我们使用路径 `C:/folder 1/folder 2/folder 3/file . txt` 创建一个文件对象。显然，上述路径是一个抽象路径，因此绝对文件路径以及规范文件路径将与上面相同。

但是如果文件对象创建时提到的文件路径像 `C:/folder 1/folder 2/folder 3/folder 4/../../folder3/file.txt`，那么绝对文件路径将与上述路径相同，但规范文件路径将是最短的绝对路径，即 `C:/folder 1/folder 2/folder 3/file . txt`。

## 方法定义

### 方法 1: `getAbsolutePath()`

```java
public String getAbsolutePath()
```

### 方法 2: `getCanonicalPath()`

```java
public String getCanonicalPath() throws IOException
```

## 示例

### 方法 1: `getAbsolutePath()`

```java
file.getAbsolutePath()
// It returns absolute path of file object in system's directory structure
```

### 方法 2: `getCanonicalPath()`

```java
file.getCanonicalPath()
// It returns canonical path of file object in system's directory structure
```

## 例 1

```java
// Java Program to illustrate Difference Between
// getCanonicalPath() and getAbsolutePath()

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
        throws IOException
    {

        // Path of Test.txt is E:\workspace\gfg\Test.txt
        // Test.txt is created inside project directory,
        // Here project name is gfg
        File file1 = new File("Test.txt");

        // Getting the absolute path of the file
        // using getAbsolutePath() method
        System.out.println("Absolute Path: "
                           + file1.getAbsolutePath());

        // Getting the canonical path of the file
        // using getCanonicalPath() method
        System.out.println("Canonical Path: "
                           + file1.getCanonicalPath());
    }
}
```