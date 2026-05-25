# Kotlin中的`const`和`val`有什么区别？

> 原文：[https://www.geeksforgeeks.org/whats-the-difference-between-const-and-val-in-kotlin/](https://www.geeksforgeeks.org/whats-the-difference-between-const-and-val-in-kotlin/)

在Kotlin中，和其他编程语言一样，属性可以是可变的（mutable）或不可变的（immutable）。为了声明一个不可变的属性，我们使用了`const`和`val`这两个术语。开发人员经常对何时使用这些关键字感到困惑。在本文中，我们将研究Kotlin中常量（`const`）和值（`val`）之间的区别。

## `const`在Kotlin中的使用

`const`关键字用于声明编译时常量，即其值在编译时就已确定且不可改变。这些值在运行时是已知的，因此，在运行时没有值可以分配给常量变量。要成为常量属性，属性必须满足以下要求：

1.  必须位于顶层，或者是`object`或`companion object`的成员。
2.  必须是`String`类型或基本数据类型（primitive data type）。
3.  没有自定义`getter`，因此你不能将常量变量赋值给一个函数或类的返回值，因为该变量将在运行时而非编译时初始化。

## `val`在Kotlin中的使用

`const`和`val`之间的主要区别在于`val`属性的值可以在运行时初始化。因此，你可以将`val`变量赋值给一个方法或类的返回值。

示例：

```kt
const val gfgName = "Geeksforgeeks" // 正确
val coursename = "Android" // 正确

const val gfgName = getgfgName() // 错误
val coursename = getcoursename() // 正确
```

上面例子中的不可变变量是`gfgName`。使用`const`时，直接赋值就可以了；但是，试图从某个函数`getgfgName()`赋值将导致错误，因为该值将在运行时而不是编译时赋值。然而，在`val`的情况下，这两种情况都是可以接受的。

## 既然`val`就够了，为什么还要用`const`？

在最后一个例子中，我们看到`val`变量的值可以在运行时初始化，而`const`必须在编译时初始化。那么，为什么在`val`足够的时候使用`const`呢？让我们看看另一个真实世界的Android例子，看看`const`和`val`是如何使用的：

```kt
GeeksforGeeksClass {
    companion object {
        const val IMAGE_EXTENSION = ".jpg"
        val LOGONAME: String
            get() = "Geeks" + System.currentTimeMillis() + IMAGE_EXTENSION
    }
}
```

> **提示：** 在上面的例子中，我们在伴随对象（`companion object`）中声明了`const`值`IMAGE_EXTENSION`，并使用自定义`getter`将`LOGONAME`变量初始化为`val`。

因为文件扩展名总是相同的，所以它被定义为常量变量。但是，文件名将根据我们应用的逻辑进行修改。在这个例子中，我们用当前时间命名文件。你不能一开始就给它一个值，因为这个值是在运行时获得的。所以我们要用`val`。

```kt
public final String getIMAGENAME() {
   return "Geeks" + System.currentTimeMillis() + ".jpg";
}
```

在这里，变量`IMAGE_EXTENSION`已经被它的值`".jpg"`所取代，表示该值已经内联，因此在运行时访问该变量没有开销。这就是用`const`代替`val`的好处。