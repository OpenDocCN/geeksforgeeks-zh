# 字符串的编译时与运行时解析

> 原文：[https://www.geeksforgeeks.org/compiletime-vs-runtime-resolution-of-strings/](https://www.geeksforgeeks.org/compiletime-vs-runtime-resolution-of-strings/)

## 字符串的编译时解析

当字符串在[字符串文字](https://www.geeksforgeeks.org/literals-in-java/)和 `+` 运算符的帮助下被创建时，它们在编译时被连接在一起。这被称为字符串的编译时解析。编译器消除了串联运算符并优化了字符串。

**示例：**

考虑下面的代码：

```java
String str = "Geeks "
             + "for"
             + "Geeks";
```

上面的代码由编译器通过字符串的编译时解析进行优化，如下所示：

```java
String str = "GeeksforGeeks";
```

## 字符串的运行时解析

当字符串在[字符串文字](https://www.geeksforgeeks.org/literals-in-java/)以及变量和 `+` 运算符的帮助下创建时，它们仅在运行时连接在一起，因为变量的值无法预先预测。这被称为字符串的运行时解析。

**示例：**

考虑下面的代码：

```java
String str = "Geeks " + var + "Geeks";
```

由于变量 `var` 的值未知，编译器无法在编译时优化上述代码。因此，字符串的运行时解析发生在这里。

**不同场景，识别分辨率类型：**

1.  假设字符串使用 `StringBuffer` 定义：

```java
    String str = (new StringBuffer())
                    .append("Geeks")
                    .append("for")
                    .append("Geeks")
                    .toString();
```

**字符串解析类型：** 字符串的运行时解析

这里编译器不能在编译时解析，因为对象创建是一个运行时活动。因此，上面的字符串将在运行时解析。

2.  假设字符串使用 `StringBuffer` 定义：

```java
    String str = "Geeks"
                 + " "
                 + "for"
                 + " "
                 + "Geeks";
```

**字符串解析类型：** 字符串的编译时解析

这里编译器可以在编译时解析，因为给定的字符串是字符串文字。因此，上述字符串将在编译时解析。

3.  假设字符串在返回语句中定义：

```java
    public static String func(String var)
    {
        return "Geeks" + var + "Geeks";
    }
```

**字符串解析类型：** 字符串的运行时解析

这里，编译器无法在编译时解析，因为变量 `var` 的值是运行时活动。因此，上面的字符串将在运行时解析。