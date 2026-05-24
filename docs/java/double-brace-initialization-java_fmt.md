# Java 中的双括号初始化

> 原文：[https://www.geeksforgeeks.org/double-brace-initialization-java/](https://www.geeksforgeeks.org/double-brace-initialization-java/)

Java 中两个独立进程的组合称为 Java 中的双括号初始化。顾名思义，其中包含两个大括号`{{`。

对于程序员来说，单个括号`{`并不是什么新鲜事。双括号初始化中的第一个大括号用于创建匿名内部类。我们已经用这种方式制作了许多匿名的内部类。

第二个大括号是它区别于 Java 中普通大括号的地方。第二个大括号是初始化块，它与声明的匿名内部类一起使用。当这个初始化块与匿名内部类一起使用时，它被称为 Java 双括号初始化。

### 双括号初始化在 Java 中的应用

Java 双括号初始化用于将创建和初始化合并在一条语句中。使用双括号初始化，我们可以初始化集合。

#### 标准方法：

当我们在代码中使用[集合](https://www.geeksforgeeks.org/collections-in-java-2/)时，我们通常会执行以下操作。

1.  为临时集合声明一个变量。
2.  创建一个新的空集合并将引用存储到变量中。
3.  将元素放入集合。
4.  将集合传递给方法。

**例如：**

```java
// Java program to demonstrate working of Collections
// without double brace initialization.

import java.util.HashSet;
import java.util.Set;

public class DoubleBrace
{
    public static void main(String[] args)
    {
        Set<String> sets = new HashSet<String>();

        sets.add("one");
        sets.add("two");
        sets.add("three");

        // ...

        // Now pass above collection as parameter to method
        useInSomeMethod(sets);
    }

    private static void useInSomeMethod(Set<String> sets)
    {
        System.out.println(sets);
    }
}
```

**输出**

```
[one, two, three]
```

以上是我们在编码实践中遵循的正常步骤。你不觉得 Java 应该有一个更方便的集合语法（列表、映射、集合等）吗？

让我们看看另一种简单的方法。这就是所谓的`双括号初始化`。

#### 使用双括号初始化

当我们在代码中使用双括号初始化时，我们通常会执行以下操作。

1.  创建一个扩展集合的匿名内部类。
2.  提供一个实例初始化块，调用 `add` 方法并向集合添加元素。
3.  传递给方法。

**举例：**

```java
// Java program to demonstrate working of Double
// Brace Initialization

import java.util.HashSet;
import java.util.Set;

public class DoubleBrace
{
    public static void main(String[] args)
    {
        Set<String> sets = new HashSet<String>()
        {
            {
                add("one");
                add("two");
                add("three");
            }
        };

        // ...

        // Now pass above collection as parameter to method
        useInSomeMethod(sets);
    }

    private static void useInSomeMethod(Set<String> sets)
    {
        System.out.println(sets);
    }
}
```

**输出**

```
[one, two, three]
```

#### **上面的代码是如何工作的？**

第一个大括号创建了一个新的[匿名内部类](https://www.geeksforgeeks.org/anonymous-inner-class-java/)。这些内部类能够访问其父类的行为。因此，在我们的例子中，我们创建了一个 `HashSet` 类的子类，这样这个内部类就可以使用 `add()` 方法。

第二个大括号是[实例初始值设定项](https://www.geeksforgeeks.org/g-fact-26-the-initializer-block-in-java/)。每当创建实例时，都会执行实例初始值设定项中的代码。

### Java 中双括号初始化的优势

Java 中双括号初始化的优点是：

*   与原生的创建和初始化方法相比，代码行数更少。
*   代码更具可读性。
*   创建和初始化在同一个表达式中完成。

### Java 中双括号初始化的缺点

Java 中双括号初始化的缺点是：

*   它晦涩难懂，并非众所周知的初始化方法。
*   每次使用时，它都会创建一个额外的类。
*   它不支持“菱形操作符”的使用——这是 Java 7 引入的一个特性。
*   如果我们试图扩展的类被标记为 `final`，它将无法工作。
*   它保存了对封闭实例的隐藏引用，这可能导致内存泄漏。

> **注**：正是由于这些缺点，双括号初始化才被认为是反模式。

本文由 [**索米亚米什拉**](https://www.facebook.com/profile.php?id=100009911175839) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。