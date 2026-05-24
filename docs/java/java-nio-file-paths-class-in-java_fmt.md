# Java中的`java.nio.file.Path`类

> 原文：[https://www.geeksforgeeks.org/java-nio-file-paths-class-in-java/](https://www.geeksforgeeks.org/java-nio-file-paths-class-in-java/)

`Paths`类包含将路径字符串或`URI`转换为`Path`的静态方法。

## 类声明

```java
public final class Paths
extends Object
```

## 方法

| 方法 | 描述 |
| --- | --- |
| `get(String first, String... more)` | 此方法将路径字符串或字符串序列转换为`Path`，这些字符串在连接时形成路径字符串。 |
| `get(URI uri)` | 此方法将给定的`URI`转换为`Path`对象。 |

### `public static Path get(String first, String... more)`

通过将给定字符串转换为路径来返回`Path`。如果`more`没有指定任何字符串，那么`first`是唯一要转换的字符串。如果`more`指定了额外的字符串，那么`first`是序列的初始部分，额外的字符串将被附加到序列的`first`之后，用`"/"`分隔。

**参数:**
1. `first` – 路径的初始部分。
2. `more` – 要连接到路径的额外字符串。

**返回:** 结果路径

**抛出:**
- `InvalidPathException` – 如果给定的字符串无法转换为路径

### 示例代码

```java
// Java program to demonstrate
// java.nio.file.Path.get(String first,String... more)
// method

import java.io.IOException;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {
        // create object of Path
        Path path = (Path)Paths.get("/usr", "local", "bin");

        // print Path
        System.out.println(path);
    }
}
```

**输出**

```java
/usr/local/bin
```

### `public static Path get(URI uri)`

通过将给定的`URI`转换为路径来返回`Path`。

**参数:**
- `uri` – 要转换的

**返回:** 结果路径

**抛出:**
- `IllegalArgumentException` – 如果`URI`的参数不合适
- `FileSystemNotFoundException` – 如果由`URI`标识的文件系统不存在
- `SecurityException` – 如果安全管理器拒绝访问文件系统

### 示例代码

```java
// Java program to demonstrate
// java.nio.file.Path.get(URI uri) method

import java.io.IOException;
import java.net.URI;
import java.net.URISyntaxException;
import java.nio.file.Paths;

public class Path {
    public static void main(String[] args)
        throws IOException, URISyntaxException
    {
        String uribase = "https://www.geeksforgeeks.org/";
        // Constructor to create a new URI
        // by parsing the string
        URI uri = new URI(uribase);

        // create object of Path
        Path path = (Path)Paths.get(uri);

        // print ParentPath
        System.out.println(path);
    }
}
```

**输出:**

```java
https://www.geeksforgeeks.org/
```