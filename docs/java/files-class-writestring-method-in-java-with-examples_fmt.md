# Java 中的文件类 writeString()方法，带示例

> 原文：[https://www.geeksforgeeks.org/files-class-writestring-method-in-java-with-examples/](https://www.geeksforgeeks.org/files-class-writestring-method-in-java-with-examples/)

Java 中[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的 `writeString()` 方法用于将内容写入指定文件。

## 语法

```java
Files.writeString(path, string, options)
```

## 参数

*   `path` – 数据类型为 `Path` 的文件路径。
*   `string` – 将在文件中以返回类型 `String` 输入的指定字符串。
*   `options` – 在文件中输入字符串的不同选项。比如将字符串附加到文件中，用当前字符串覆盖文件中的所有内容，等等。

## 返回值

此方法不返回值。

下面是 `writeString()` 方法的两种重载形式。

> public static Path writeString(Path path, CharSequence csq, OpenOption… options) throws IOException
>
> public static Path writeString(Path path, CharSequence csq, Charset cs, OpenOption… options) throws IOException

*   在第一种方法中，UTF-8 字符集用于将内容写入文件。
*   第二种方法使用指定的字符集进行相同的操作。
*   文件的打开方式在 `options` 中指定。

## 示例

下面是问题陈述的实现：

```java
// Implementation of writeString() method in Java
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardOpenOption;

public class GFG {
    public static void main(String[] args)
    {
        // Initializing file Path with some conditions
        Path filePath
            = Paths.get("/home/mayur/", "temp", "gfg.txt");

        try {
            // Write content to file
            Files.writeString(filePath, "Hello from GFG !!",
                              StandardOpenOption.APPEND);

            // Verify file content
            String content = Files.readString(filePath);

            System.out.println(content);
        }
        catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 输出

```java
Hello from GFG !!
```

![](img/36103e54293441218ea613ddba682f1c.png)

输出文件