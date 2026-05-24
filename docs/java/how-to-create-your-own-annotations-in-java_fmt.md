# 如何用 Java 创建自己的注释？

> 原文：`https://www.geeksforgeeks.org/how-to-create-your-own-annotations-in-java/`

注释是元数据的一种形式，它提供关于程序的信息，但不是程序本身的一部分。注释不会影响它们注释的代码的操作。

现在让我们来看看不同类型的 java 注释，如下所示：

1.  **预定义注释**：`@Deprecated`、`@Override`、`@SuppressWarnings`、`@SafeVarargs`、`@FunctionalInterface`。
2.  **元注释**：`@Reserved`、`@Documented`、`@Target`、`@Inherited`、`@Repeatable`。
3.  **用户定义注释**：这些是由用户定义的。（我们将在本模块中学习如何创建自定义注释）。

极客，现在你一定想知道我们如何创建自己的 java 注释，为此，请依次参考以下简单步骤：

1.  要创建你自己的 Java 注释，你必须使用 `@interface Annotation_name`，这将为你创建一个新的 Java 注释。
2.  `@interface` 将描述新的注释类型声明。
3.  为你的注释命名后，你需要创建一个声明块，你可以在其中声明一些变量。

现在继续，有三种形式的注释可以用 java 定义如下：

1.  **标记注释**：这些是内部没有声明或定义变量的注释。
2.  **单值注释**：这些注释中只声明或定义了一个变量。
3.  **多值注释**：这些是可以声明和定义多种类型的多个变量的注释。

**实现：**

让我们以一个名为 `books_data` 的自定义注释为例，来了解不同形式的注释是如何声明的。

```java
@interface books_data // 使用语法：@interface Annotation_name，我们在这里声明了一个新注释。
{ // 注释声明和定义的开始

/*
在注释中定义变量是可选的。
注释内声明的变量数量将描述其形式。
*/

} // 注释声明和定义的结束
```

**例 1：**

## Java

```java
// Java 程序，用于说明自定义标记注释的声明

// 导入 I/O 类
import java.io.*;

// 标记注释示例：
// 自定义注释声明
@interface books_data
{
    // 此处未声明变量
}

// 主类
class books {

    // 主驱动方法
    public static void main(String[] args)
    {
        // 打印语句
        System.out.println(
            "example of Marker Annotations.");
    }
}
```

**输出**

```
example of Marker Annotations.
```

> 由于在这个注释里面没有声明变量，这将被称为**标记注释**。

**例 2：**

## Java

```java
// Java 程序，用于说明自定义单值注释的声明

// 导入输入输出类
import java.io.*;

// 单值注释示例：
// 自定义注释声明
@interface books_data
{
    // 单变量声明
    String book_name();
}

// 主类
class books {

    // 主驱动方法
    public static void main(String[] args)
    {
        // 打印语句
        System.out.println(
            "example of single value Annotation.");
    }
}
```