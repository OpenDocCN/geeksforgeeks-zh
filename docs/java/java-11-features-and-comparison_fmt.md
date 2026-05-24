# Java 11–特性和比较

> 原文: [https://www.geeksforgeeks.org/java-11-features-and-comparison/](https://www.geeksforgeeks.org/java-11-features-and-comparison/)

每 6 个月，甲骨文就会发布新的 Java 版本。9 月份的 Java 11 版本甚至在发布之前就已经在计算机科学领域引起了很大的轰动，它宣称从现在开始 Java 将为商业用途付费。

以下文章将展示 JDK 11 的重要特性、增强功能和不推荐使用的特性。

## 重要变更和信息

*   运行小程序和 web 应用程序所需的部署堆栈已从 JDK 移除，这在 JDK 9 中已被否决。
*   由于部署堆栈不可用，支持的浏览器的整个部分已从支持的配置列表中删除。
*   自动更新已从 Windows 和 MacOS 的 JRE 安装中删除。
*   JavaFX 和 Java 任务控制现在可以单独下载。
*   不再提供法语、德语、意大利语、韩语、葡萄牙语(巴西)、西班牙语和瑞典语的 Java 语言翻译。
*   在这个版本中，不再提供 JRE 或服务器 JRE。只有 JDK 被录用了。
*   Windows 的更新打包格式已从 `tar.gz` 更改为 `.exe`。
*   macOS 的更新包格式已从 `.app` 更改为 `.dmg`。

## 新特性和增强功能

### 1. 新字符串方法

*   `isBlank()`: 这是一个布尔方法。当字符串为空时返回 `true`，反之亦然。

```java
class GFG {
    public static void main(String args[])
    {
        String str1 = "";
        System.out.println(str1.isBlank());

        String str2 = "GeeksForGeeks";
        System.out.println(str2.isBlank());
    }
}
```

**输出:**

```text
True
False
```

*   `lines()`: 此方法用于返回一个由行终止符分隔的字符串集合。

```java
class GFG {
    public static void main(String args[])
    {
        String str = "Geeks\nFor\nGeeks";
        System.out.println(str
                           .lines()
                           .collect(
                               Collectors.toList()));
    }
}
```

**输出:**

```text
Geeks
For
Geeks
```

*   `repeat(n)`: 结果是原始字符串重复参数中指定次数后的连接字符串。

```java
class GFG {
    public static void main(String args[])
    {
        String str = "GeeksForGeeks";
        System.out.println(str.repeat(4));
    }
}
```

**输出:**

```text
GeeksForGeeksGeeksForGeeksGeeksForGeeksGeeksForGeeks
```

*   `stripLeading()`: 用于移除字符串前面的空白。

```java
class GFG {
    public static void main(String args[])
    {
        String str = " GeeksForGeeks";
        System.out.println(str.stripLeading());
    }
}
```

**输出:**

```text
GeeksForGeeks
```

*   `stripTrailing()`: 用于移除字符串后面的空白。

```java
class GFG {
    public static void main(String args[])
    {
        String str = "GeeksForGeeks ";
        System.out.println(str.stripTrailing());
    }
}
```

**输出:**

```text
GeeksForGeeks
```

*   `strip()`: 用于移除字符串前面和后面的空白。

```java
class GFG {
    public static void main(String args[])
    {
        String str = " GeeksForGeeks ";
        System.out.println(str.strip());
    }
}
```

**输出:**

```text
GeeksForGeeks
```

### 2. 新文件方法

*   `writeString()`: 这是在文件中写入一些内容。

```java
jshell> Files.writeString(Path.of("example.txt"), "GeeksForGeeks!");
```

*   `readString()`: 用于读取文件的内容。

```java
jshell> Files.readString(Path.of("example.txt"));
```

**输出:**

```text
"GeeksForGeeks!"
```

*   `isSameFile()`: 这个方法用来知道两个路径是否定位同一个文件。

```java
jshell> Files.isSameFile(Path.of("example1.txt"), Path.of("example1.txt"));
```

**输出:**

```text
true
```

```java
jshell> Files.isSameFile(Path.of("example2.txt"), Path.of("example1.txt"));
```

**输出:**

```text
false
```

### 3. 模式识别方法

*   `asMatchPredicate()`: 该方法类似于 Java 8 方法 `asPredicate()`。在 JDK 11 中引入，如果模式与输入字符串匹配，这个方法将创建一个谓词。

```java
jshell> var str = Pattern.compile("aba").asMatchPredicate();

jshell> str.test("aabb");
```

**输出:**

```text
false
```

```java
jshell> str.test("aba");
```

**输出:**

```text
true
```

### 4. Epsilon 垃圾收集器

这处理内存分配，但没有实际的内存回收机制。一旦可用的 Java 堆耗尽，JVM 将关闭。
其目标是:
*   性能试验
*   记忆压力测试
*   上次丢弃延迟改进

### 5. 删除了 Java EE 和 CORBA 模块

这些模块在 Java 9 中已被弃用，并声明在进一步的 JDK 版本中删除这些模块。

### 6. 移除线程功能

`stop(Throwable obj)` 和 `destroy()` 对象已从 JDK 11 中移除，因为它们分别仅抛出 `UnsupportedOperationException` 和 `NoSuchMethodError`。除此之外，它们毫无用处。

### 7. 时间单位转换

该方法用于将给定时间转换为像日、月、年这样的单位，也用于时间。

```java
jshell> TimeUnit c = TimeUnit.DAYS;
```

**输出:**

```text
DAYS
```

```java
jshell> c.convert(Duration.ofHours(24));
```

**输出:**

```text
1
```

```java
jshell> c.convert(Duration.ofHours(50));
```

**输出:**

```text
2
```

### 8. `Optional.isEmpty()`

如果任何对象的值为空，则该方法返回真，否则返回假。

```java
jshell> Optional<String> str = Optional.empty();
jshell> str.isEmpty();
```

**输出:**

```text
true
```

```java
jshell> Optional<String> str = Optional.of("TonyStark");
jshell> str.isEmpty();
```

**输出:**

```text
false
```

### 9. Lambda 参数的局部变量语法

JDK 11 允许在 lambda 表达式中使用 `var`。引入此功能是为了与 Java 10 的局部 `var` 语法保持一致。

```java
//Variable used in lambda expression
public class VarInLambdaExample {
  public static void main(String[] args) {
      IntStream.of(1, 2, 3, 5, 6, 7)
               .filter((var i) -> i % 2 == 0)
               .forEach(System.out::println);
  }
}
```

**输出:**

```text
2
6
```

```java
//Variable without using lambda expression
public class WithoutVarInLambdaExample {
  public static void main(String[] args) {
      IntStream.of(1, 2, 3, 5, 6, 7)
               .filter(i -> i % 2 == 0)
               .forEach(System.out::println);
  }
}
```

**输出:**

```text
2
6
```

## 删除的功能和选项

1.  删除 `com.sun.awt.AWTUtilities` 类
2.  从 Oracle JDK 中删除 Lucida 字体
3.  移除 `appletviewer` 启动器
4.  Oracle JDK 中的 `javax.imageio` JPEG 插件不再支持带有 alpha 的图像
5.  删除 `sun.misc.Unsafe.defineClass` 类
6.  移除 `Thread.destroy()` 和 `Thread.stop(Throwable)` 方法
7.  删除 `sun.nio.ch.disableSystemWideFileLockCheck` 属性
8.  删除 `sun.locale.formatasdefault` 属性
9.  移除 `JVM-MANAGEMENT-MIB.mib`
10. 删除简单网络管理协议代理
11. 删除 Java 部署技术
12. 将 JMC 从 Oracle JDK 中移除
13. 从 Oracle JDK 中删除 JavaFX
14. JEP 320 删除 Java EE 和 CORBA 模块

## 不推荐使用的功能和选项

1.  `ThreadPoolExecutor` 不应指定终结依赖项
2.  JEP 335 反对 Nashorn 的 JavaScript 引擎
3.  废弃 `-XX:+AggressiveOpts` 选项
4.  对商业功能的过时支持
5.  不赞成基于流的通用文本方法
6.  JEP 336 反对 Pack200 工具和 API