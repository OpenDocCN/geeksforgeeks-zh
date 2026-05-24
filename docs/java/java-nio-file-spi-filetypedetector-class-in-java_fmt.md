# java.nio.file.spi.FileTypeDetector类

> 原文：[https://www.geeksforgeeks.org/java-nio-file-spi-filetypedetector-class-in-java/](https://www.geeksforgeeks.org/java-nio-file-spi-filetypedetector-class-in-java/)

`java.nio.file.spi.FileTypeDetector`类扩展了`java.lang.Object`类。文件类型检测器类包含了解给定文件内容类型的方法。

## 类声明

```java
public abstract class FileTypeDetector
extends Object
```

## 构造器

| 构造器 | 描述 |
| --- | --- |
| `protected FileTypeDetector()` | 它用于创建文件类型检测器类的新对象。 |

## 方法

| 方法 | 描述 |
| --- | --- |
| `probeContentType(Path)` | 它用于猜测给定文件的内容类型。 |

### `probeContentType(Path path)`方法
用于猜测给定文件的内容类型。要知道文件的内容类型，这个方法可以检查文件名，使用文件属性，甚至检查文件中的字节。审查文件的方式完全取决于实现。

**参数:**

*   `Path` – 要猜测内容类型的文件的路径

**返回:**
给定文件的内容类型。如果无法识别文件类型，它将返回`null`。

**异常:**

*   `IOException` – 如果出现输入/输出错误
*   `SecurityException` – 如果安全管理器拒绝访问给定文件。

## Java代码示例

```java
// Java program to illustrate use of probeContentType()
// method of FileTypeDetector class
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {

    public static void main(String[] args)
    {
        try {
            // create object of Path
            Path path = (Path)Paths.get("/usr", "local",
                                        "bin", "file.txt");
            // Print content type of the file present at
            // this path
            System.out.println(
                Files.probeContentType(path));
        }
        catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 输出

```java
text/plain
```