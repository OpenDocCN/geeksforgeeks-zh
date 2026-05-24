# Java 中的格式说明符

> 原文：[https://www.geeksforgeeks.org/format-specifiers-in-java/](https://www.geeksforgeeks.org/format-specifiers-in-java/)

格式说明符以百分比字符（`%`）开头，以“类型字符”结尾，表示数据类型（`int`、`float` 等）将被转换为表示数据的基本方式（十进制、十六进制等）。
格式说明符的一般语法是

```java
% [flags] [width] [.precision] [argsize] typechar
```

`Formatter` 类的 `format()` 方法接受多种格式说明符。当使用大写说明符时，字母以大写显示。否则，大写和小写说明符执行相同的转换。

| 格式规范 | 应用的转换 |
| --- | --- |
| `%%` | 插入 `%` 符号 |
| `%x %X` | 整数十六进制 |
| `%t %T` | 时间和日期 |
| `%s %S` | 线 |
| `%n` | 插入换行符 |
| `%o` | 八进制整数 |
| `%f` | 十进制浮点 |
| `%e %E` | 科学符号 |
| `%g` | 使格式化程序使用 `%f` 或 `%e`，以较短者为准 |
| `%h %H` | 参数的哈希代码 |
| `%d` | 十进整数 |
| `%c` | 性格；角色；字母 |
| `%b %B` | 布尔代数学体系的 |
| `%a %A` | 浮点十六进制 |

## 空格格式说明符
当创建数字列时，有时在正数前打印一个空格以便正负数对齐非常有用。为此，可以使用空格格式说明符。

**语法：**

```java
Formatter().format("% d", -111);
Formatter().format("% d", 111);
```

**示例：**

```java
// Java program to demonstrate
// the space format specifier

import java.util.*;

class GFG {
    public static void main(String args[])
    {
        // create Formatter class object
        Formatter formatter = new Formatter();

        // Use Space format specifier
        formatter.format("%d", -111);
        System.out.println(formatter);

        formatter = new Formatter();
        formatter.format("% d", 111);
        System.out.println(formatter);

        formatter = new Formatter();
        formatter.format("% d", -222);
        System.out.println(formatter);

        formatter = new Formatter();
        formatter.format("% d", 222);
        System.out.println(formatter);
    }
}
```

**输出：**

```java
-111
 111
-222
 222
```

## 加号格式说明符
此说明符在正数值前添加 `+` 号，对负数值无效。

**语法：**

```java
Formatter().format("%+d", 111);
```

**输出：**

```java
+111
```

**示例：**

```java
// Java program to demonstrate
// the + sign Specifier format specifiers.

import java.util.*;

class GFG {
    public static void main(String args[])
    {
        // create Formatter class object
        Formatter formatter = new Formatter();

        // + sign specifier
        formatter = new Formatter();
        formatter.format("%+d", 111);
        System.out.println(formatter);

        // + sign specifier
        // on - sign, it will have no effect
        formatter = new Formatter();
        formatter.format("%+d", -111);
        System.out.println(formatter);
    }
}
```

**输出：**

```java
+111
-111
```

## 括号格式说明符
此说明符将负数值放在括号内，对正数值无效。

**语法：**

```java
Formatter().format("%(d", -111);
Formatter().format("%(d", 111);
```

**输出：**

```java
(111)
111
```

**示例：**

```java
// Java program to demonstrate
// the ( Specifiers format specifiers.

import java.util.*;

class GFG {
    public static void main(String args[])
    {
        // create Formatter class object
        Formatter formatter = new Formatter();

        // ( Specifier
        formatter = new Formatter();
        formatter.format("%(d", -111);
        System.out.println(formatter);

        formatter = new Formatter();
        formatter.format("%(d", 111);
        System.out.println(formatter);
    }
}
```

**输出：**

```java
(111)
111
```