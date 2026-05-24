# Java 中的访问和非访问修饰符

> 原文：[https://www.geeksforgeeks.org/access-and-non-access-modifiers-in-java/](https://www.geeksforgeeks.org/access-and-non-access-modifiers-in-java/)

Java 提供了一组丰富的修饰符。它们用于控制访问机制，也向 JVM 提供关于类功能的信息。它们分为两类：

## 访问修饰符

Java 的访问修饰符有 `public`、`private`、`protected`。Java 还定义了一个默认的访问级别（称为包私有）。

### 它们是如何工作的？

*   **`public`**：当一个类的成员被 `public` 修改时，那么该成员可以被任何其他代码访问。
*   **`private`**：当一个类的成员被指定为 `private` 时，那么该成员只能被其所在类的其他成员访问。
    现在你可以理解为什么 `main()` 总是前面带有 `public` 修饰符。它被程序外部的代码调用——即由 Java 运行时系统调用。当未使用访问修饰符时，默认情况下，类的成员在其自己的包内是 `public` 的，但不能在其包外被访问。`protected` 仅在涉及[继承](https://www.geeksforgeeks.org/inheritance-in-java/)时适用。

**详细文章：** [Java 中的访问修饰符](https://www.geeksforgeeks.org/access-modifiers-java/)

## 非访问修饰符

在 Java 中，我们有 7 个非访问修饰符。它们与类、方法、变量、构造函数等一起使用，向 JVM 提供关于它们行为的信息。它们是：

*   [`static`](https://www.geeksforgeeks.org/static-keyword-java/)
*   [`final`](https://www.geeksforgeeks.org/final-keyword-java/)
*   `abstract`
*   [`synchronized`](https://www.geeksforgeeks.org/synchronized-in-java/)
*   [`transient`](https://www.geeksforgeeks.org/transient-keyword-java/)
*   [`volatile`](https://www.geeksforgeeks.org/volatile-keyword-in-java/)
*   [`native`](https://www.geeksforgeeks.org/native-keyword-java/)

本文由 **Gaurav Miglani** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。