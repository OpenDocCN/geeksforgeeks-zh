# Java 中的 `createTempDirectory()` 方法示例

> 原文：[https://www.geeksforgeeks.org/files-createtempdirectory-method-in-java-with-examples/](https://www.geeksforgeeks.org/files-createtempdirectory-method-in-java-with-examples/)

[`java.nio.file.Files`](https://www.geeksforgeeks.org/tag/java-nio-file-package/) 类的 `createTempDirectory()` 方法用于使用给定的前缀和属性创建一个新目录。给定的前缀充当形成的目录的名称，可以为空。目录是用给定的属性设置的。

根据传递的参数类型，`Files` 类提供了两种类型的 `createTempDirectory()` 方法。

## 方法

### 1. `public static Path createTempDirectory(Path dir, String prefix, FileAttribute<?>... attrs)`

此方法用于在已经存在的目录中创建新目录，使用给定的前缀生成其名称。新形成的目录的路径与默认文件系统相关联。它与指定目录的路径相同。候选名称是使用前缀生成的。`File.deleteOnExit()` 方法用于自动删除目录。`attrs` 参数用于设置目录的属性。每个属性都由其名称标识。如果指定了多个具有相同名称的属性，则忽略除最后一个属性之外的所有属性。

**参数：**

*   `dir` – 要在其中创建新目录的现有目录的路径。
*   `prefix` – 目录的名称，可以为空。
*   `attrs` – 设置目录的属性（可选）

**返回：** 新形成目录的路径

**异常：**

*   `IllegalArgumentException` – 如果前缀不是合适的候选目录名称。
*   `UnsupportedOperationException` – 如果指定了任何无法设置到目录的属性。
*   `IOException` – 如果发生 I/O 错误。
*   `SecurityException` – 如果安全管理器调用了 `checkWrite` 方法。

```java
// Java Program to show the usage of
// public static Path createTempDirectory
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

// Driver class
public class GFG {

    // main method
    public static void main(String[] args) {
        // prefix used to create candidate names
        String prefix = "TempDirectory";

        // path of the directory in which temporary
        // directory has to created
        Path dir = (Path) Paths.get("/usr", "local", "bin", "directory");
        try {
            // creating temporary directory and storing its
            // path in tempDir variable
            Path tempDir = Files.createTempDirectory(dir, prefix);

            // printing the path of the created temporary
            // directory
            System.out.println("Temporary Directory created at:\n" + tempDir.toString());

            // deleting the temporary directory after the
            // virtual machine terminates
            tempDir.toFile().deleteOnExit();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**输出：**

```
Temporary Directory created at:
/usr/local/bin/directory/TempDirectory1472243991754401317
```

### 2. `public static Path createTempDirectory(String prefix, FileAttribute<?>... attrs)`

此方法用于使用给定的前缀和属性创建新目录。给定的前缀充当形成的目录的名称，可以为空。候选名称是使用前缀生成的。目录是用给定的属性设置的。新形成的目录的路径与默认文件系统相关联。`attrs` 参数用于设置目录的属性。每个属性都由其名称标识。如果指定了多个具有相同名称的属性，则忽略除最后一个属性之外的所有匹配项。

**参数：**

*   `prefix` – 目录的名称，可以为空。
*   `attrs` – 设置目录的属性（可选）

**返回：** 新形成目录的路径

**异常：**

*   `IllegalArgumentException` – 如果前缀不是合适的候选目录名称。
*   `UnsupportedOperationException` – 如果指定了任何无法设置到目录的属性。
*   `IOException` – 如果发生 I/O 错误。
*   `SecurityException` – 如果安全管理器调用了 `checkWrite` 方法。

**输出：**

```
Temporary Directory created at:
/var/folders/13/jsq29lh11bn7kgwnzpggqytr0000gn/T/TempDirectory4403940384431706243
```