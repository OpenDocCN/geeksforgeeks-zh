# Java 中继承和组合的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-inheritance-and-composition-in-java/](https://www.geeksforgeeks.org/difference-between-inheritance-and-composition-in-java/)

[**继承**](https://www.geeksforgeeks.org/inheritance-in-c/)：
当我们想要创建一个新的类，并且已经有一个类包含了我们想要的一些代码时，我们可以从现有的类中派生出我们的新类。这样，我们可以重用现有类的字段和方法，而不必自己编写它们。

子类从它的超类继承所有成员（字段、方法和嵌套类）。构造函数不是成员，所以它们不会被子类继承，但是超类的构造函数可以从子类中调用。

继承的类型有：

1.  单一继承
2.  多级继承
3.  多重继承
4.  混合遗传
5.  分级继承

**继承示例：**

```java
class A {
    int a, b;
    public void add(int x, int y)
    {
        a = x;
        b = y;
        System.out.println(
            "addition of a + b is:"
            + (a + b));
    }
}

class B extends A {
    public void sum(int x, int y)
    {
        add(x, y);
    }

    // Driver Code
    public static void main(String[] args)
    {
        B b1 = new B();
        b1.sum(5, 6);
    }
}
```

**输出：**

```
addition of a+b is:11
```

这里，类 `B` 是继承基类 `A` 的属性（`add` 方法）的派生类。

[**组合**](https://www.geeksforgeeks.org/association-composition-aggregation-java/)：
组合也提供了代码的可重用性，但这里的区别是我们没有为此扩展类。

**组合示例：**
我们以**图书馆**为例。

```java
// Java program to illustrate
// the concept of Composition

import java.io.*;
import java.util.*;

// class book
class Book {
    public String title;
    public String author;

    Book(String title, String author) {
        this.title = title;
        this.author = author;
    }
}

// Library class contains
// list of books.
class Library {
    // reference to refer to the list of books.
    private final List<Book> books;

    Library(List<Book> books) {
        this.books = books;
    }

    public List<Book> getTotalBooksInLibrary() {
        return books;
    }
}

// main method
class GFG {
    public static void main(String[] args) {
        // Creating the Objects of Book class.
        Book b1 = new Book("Effective Java", "Joshua Bloch");
        Book b2 = new Book("Thinking in Java", "Bruce Eckel");
        Book b3 = new Book("Java: The Complete Reference", "Herbert Schildt");

        // Creating the list which contains the no. of books.
        List<Book> books = new ArrayList<Book>();
        books.add(b1);
        books.add(b2);
        books.add(b3);

        Library library = new Library(books);

        List<Book> bks = library.getTotalBooksInLibrary();
        for (Book bk : bks) {
            System.out.println("Title : " + bk.title + " and " + " Author : " + bk.author);
        }
    }
}
```

**输出：**

```
Title : Effective Java and  Author : Joshua Bloch
Title : Thinking in Java and  Author : Bruce Eckel
Title : Java: The Complete Reference and  Author : Herbert Schildt
```

**继承与组合的区别：**

| S.NO | 继承 | 组合 |
| :--- | :--- | :--- |
| 1. | 在继承中，我们定义了我们要继承的类（超类），最重要的是它不能在运行时更改。 | 而在组合中，我们只定义一个我们想要使用的类型，它可以保存不同的实现，并且它可以在运行时改变。因此，组合比继承灵活得多。 |
| 2. | 这里我们只能扩展一个类，换句话说，多个类不能被扩展，因为 Java 不支持多重继承。 | 而组合允许使用不同类的功能。 |
| 3. | 在继承中，我们需要父类来测试子类。 | 组合允许独立于父类或子类测试我们正在使用的类的实现。 |
| 4. | 继承不能扩展 `final` 类。 | 而组合允许代码重用，甚至从 `final` 类开始。 |
| 5. | 这是一种 `is-a` 关系。 | 而它是一个 `has-a` 的关系。 |