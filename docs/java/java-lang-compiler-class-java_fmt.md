# Java 中的 `Compiler` 类

> 原文：[https://www.geeksforgeeks.org/java-lang-compiler-class-java/](https://www.geeksforgeeks.org/java-lang-compiler-class-java/)

`Compiler` 类提供从 Java 代码到原生代码的支持和相关服务。
原生代码是一种可以说在虚拟机中运行的代码形式（例如，JVM Java Virtual Machine）。

## 申报

```java
public final class Compiler
   extends Object
```

## 方法

### `command()`

`java.lang.Compiler.command()` 测试参数类型并执行一些有文档记录的操作。

**语法：**

```java
public static boolean command(Object argument)
Parameters : 
argument : needs to be compiler specific.
Return  :
compiler specific value
Exception : 
-> NullPointerException
```

### `compileClass()`

`java.lang.Compiler.compileClass()` 编译指定的类。

**语法：**

```java
public static boolean compileClass(Class c)
Parameters : 
c : class to be compiled.
Return  :
 true if the compilation succeeded else, false
Exception : 
-> NullPointerException
```

### `enable()`

`java.lang.Compiler.enable()` 使编译器开始运行。

**语法：**

```java
public static void enable()
Parameters : 
------
Return  :
void
```

### `disable()`

`java.lang.Compiler.disable()` 停止编译器执行操作。

**语法：**

```java
public static void disable()
Parameters : 
-------
Return  :
void
```

### `compileClasses()`

`java.lang.Compiler.compileClasses()` 编译名称为字符串 `str` 的类。

**语法：**

```java
public static boolean compileClasses(String string)
Parameters : 
str : name of the class to be compiled
Return  :
true if the classes are compiled successfully 
Exception : 
-> NullPointerException
```

## 示例代码

```java
// Java Program illustrating the use of Compiler class Methods.

import java.lang.*;

public class NewClass
{
    public static void main(String[] args)
    {
        CompilerClass geek = new CompilerClass();

        // Use of enable() :
        Compiler.enable();

        // class CompilerDemo
        Class c = geek.getClass();
        System.out.println(c);

        // Use of command() :
        Object g = Compiler.command("javac CompilerClass");
        System.out.println("Value : " + g);

        // Use of compileClass :
        // Since it is not a subclass so there is no compiler for it
        boolean check = Compiler.compileClass(c);
        System.out.println("\nIs compilation successful ? : " + check);

        String str = "CompilerClass";
        boolean check1 = Compiler.compileClasses(str);

        System.out.println("\nIs compilation successful using str ? : " + check1);

        // Use of disable() :
        Compiler.disable();
    }

    private static class CompilerClass
    {
        public CompilerClass()
        {
        }
    }
}
```

## 输出

```java
class NewClass$CompilerClass
Value : null

Is compilation successful ? : false

Is compilation successful using str ? : false
```

**注：**
`Compiler` 类继承了 Java 中 [`Object`](https://www.geeksforgeeks.org/object-class-in-java/) 类的其他方法。

本文由 [**莫希特·古普塔 _OMG 供稿😀**](https://www.facebook.com/profile.php?id=100016327034955) 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。