# Java - 重命名文件

> 原文：[https://www.geeksforgeeks.org/java-renaming-file/](https://www.geeksforgeeks.org/java-renaming-file/)

在 Java 中，我们可以使用属于`File`类的`renameTo()`方法来重命名文件。

## 声明

以下是`File.renameTo(File dest)`方法的声明：

```java
public boolean renameTo(File dest)
```

## 参数

`dest` – 现有抽象路径名的新抽象路径名。

## 异常

- `SecurityException`：如果安全管理器存在，并且其方法拒绝对旧路径名或新路径名的写访问。
- `NullPointerException`：如果参数`dest`为空。

```java
// Java program to rename a file.
import java.io.File;

public class GeeksforGeeks {
    public static void main(String[] args)
    {
        File oldName =
         new File("C:\Users\Siddharth\Desktop\java.txt");
        File newName = 
         new File("C:\Users\Siddharth\Desktop\GeeksforGeeks.txt");

        if (oldName.renameTo(newName)) 
            System.out.println("Renamed successfully");        
        else 
            System.out.println("Error");        
    }
}
```

```
Renamed successfully
```