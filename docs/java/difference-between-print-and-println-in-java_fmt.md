# Java 中 `print()` 和 `println()` 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-print-and-println-in-java/](https://www.geeksforgeeks.org/difference-between-print-and-println-in-java/)

## `print()`

Java 中的 `print()` 方法是用来在控制台上显示一个文本。该文本以字符串的形式作为参数传递给该方法。此方法在控制台上打印文本，光标保留在控制台上文本的末尾。下一次印刷就发生在这里。

### 各种 `print()` 方法

- `void print(boolean b)` – 打印一个布尔值。
- `void print(char c)` – 打印一个字符。
- `void print(char[] s)` – 打印字符数组。
- `void print(double d)` – 打印双精度浮点数。
- `void print(float f)` – 打印一个浮点数。
- `void print(int i)` – 打印一个整数。
- `void print(long l)` – 打印长整数。
- `void print(Object obj)` – 打印一个对象。
- `void print(String str)` – 打印字符串。

### 示例

```java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // The cursor will remain
        // just after the 1
        System.out.print("GfG1");

        // This will be printed
        // just after the GfG2
        System.out.print("GfG2");
    }
}
```

### 输出

```java
GfG1GfG2
```

## `println()`

Java 中的 `println()` 方法也是用来在控制台上显示一个文本的。该文本以字符串的形式作为参数传递给该方法。此方法在控制台上打印文本，光标保留在控制台下一行的开始处。下一次打印从下一行开始。

### 各种 `println()` 方法

- `void println()` – 通过写入行分隔符字符串终止当前行。
- `void println(boolean x)` – 打印一个布尔值，然后终止该行。
- `void println(char x)` – 打印一个字符，然后终止该行。
- `void println(char[] x)` – 打印一个字符数组，然后终止该行。
- `void println(double x)` – 打印一个 double，然后终止该行。
- `void println(float x)` – 打印一个 float，然后终止该行。
- `void println(int x)` – 打印一个整数，然后终止该行。
- `void println(long x)` – 打印一个长的，然后终止该行。
- `void println(Object x)` – 打印一个对象，然后终止该行。
- `void println(String x)` – 打印一个字符串，然后终止该行。

### 示例

```java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // The cursor will after GFG1
        // will at the start
        // of the next line
        System.out.println("GfG1");

        // This will be printed at the
        // start of the next line
        System.out.println("GfG2");
    }
}
```

### 输出

```java
GfG1
GfG2
```

## `print()` 和 `println()` 的区别

| `println()` | `print()` |
| --- | --- |
| 它会在消息显示后添加新行。 | 它不添加任何新行。 |
| 它可以在没有参数的情况下工作。 | 此方法仅适用于参数，否则就是语法错误。 |