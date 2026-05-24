# Java 中抽象类和具体类的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-abstract-class-and-concrete-class-in-java/](https://www.geeksforgeeks.org/difference-between-abstract-class-and-concrete-class-in-java/)

## 抽象类

抽象类是 Java 中由 `abstract` 关键字声明的一种类。抽象类不能直接实例化，即不能使用 `new` 关键字直接创建该类的对象。抽象类可以通过一个具体的子类来实例化，也可以通过定义所有的抽象方法和新语句来实例化。它可能包含也可能不包含抽象方法。抽象方法由 `abstract` 关键字声明，这样的方法不能有主体。如果一个类包含一个抽象方法，那么它也需要是抽象的。

## 具体类

Java 中的具体类是子类的一种类型，它实现了它所扩展到的超抽象类的所有抽象方法。它也有它实现的接口的所有方法的实现。

## 抽象类 vs 具体类

### 1. 修饰符

使用 `abstract` 修饰符声明抽象类。具体的类不应该用 `abstract` 关键字来声明，这样做的话，它也会变成一个抽象类。

### 2. 实例化

抽象类不能直接实例化，即不能使用 `new` 关键字直接创建该类的对象。抽象类可以通过一个具体的子类来实例化，也可以通过定义所有的抽象方法和新语句来实例化。可以使用 `new` 关键字直接实例化具体的类。

**示例：** 抽象类的无效直接实例化。

```java
abstract class DemoAbstractClass {
    abstract void display();
}

public class JavaApplication {
    public static void main(String[] args)
    {
        DemoAbstractClass AC = new DemoAbstractClass();
        System.out.println("Hello");
    }
}
```

**编译错误：**

```java
prog.java:9: error: DemoAbstractClass is abstract; cannot be instantiated
        DemoAbstractClass AC = new DemoAbstractClass();
                               ^
```

**示例：** 通过定义一个抽象类的所有抽象方法进行有效的实例化。

```java
abstract class DemoAbstractClass {
    abstract void display();
}

public class JavaApplication {
    public static void main(String[] args)
    {
        DemoAbstractClass AC = new DemoAbstractClass() {
            void display()
            {
                System.out.println("Hi.");
            }
        };
        AC.display();
        System.out.println("How are you?");
    }
}
```

**Output：**

```java
Hi.
How are you?
```

**示例：** 使用 `new` 关键字直接实例化具体类。

```java
abstract class DemoAbstractClass {
    abstract void display();
}

class ConcreteClass extends DemoAbstractClass {
    void display()
    {
        System.out.println("Hi.");
    }
}

public class JavaApplication {
    public static void main(String[] args)
    {
        ConcreteClass C = new ConcreteClass();
        C.display();
        System.out.println("How are you?");
    }
}
```

**Output：**

```java
Hi.
How are you?
```

### 3. 抽象方法

一个抽象类可以有也可以没有抽象方法。一个具体类不能有抽象方法，因为包含抽象方法的类也必须是抽象的。

让我们通过一个例子来理解：
我们在 Servlet 中有一个名为 `HttpServlet` 的类。现在，这个类有其特殊之处。
**`HttpServlet` 是一个抽象类，但它不包含任何抽象方法。**

让我们深入理解上述语句的含义：
-> `HttpServlet` 是一个抽象类，因为它没有为其方法提供合适的实现。既然它没有为其方法提供合适的实现，那么为这样的类创建对象又有什么意义呢。因此，这个类被设为抽象的。

**现在出现的问题是：**
**问：** 如果方法没有得到适当的实现，那么为什么它们没有使它变得抽象？
- > 因为抽象方法是那些没有合适的主体定义的方法，所以我们在类中重写这些方法来给它一个合适的定义。所以基本上抽象的方法被用于压倒一切的目的。
现在这个 `HttpServlet` 类包含 10 个方法，假设如果这些方法被抽象，那么我们需要覆盖 `HttpServlet` 类的所有 10 个方法，这是一个愚蠢的方法，因为我们只需要 `doGet()` 和 `doPost()` 方法。

下面是一个用 Java 说明上述观点的示例程序：

```java
// Java program to show servlet example
// Importing required Java libraries
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;

// Extend HttpServlet class
public class AdvanceJavaConcepts extends HttpServlet {
    private String output;

    // Initializing servlet
    public void init() throws ServletException
    {
        output = "Advance Java Concepts";
    }

    // Requesting and printing the output
    public void doGet(HttpServletRequest req,
                      HttpServletResponse resp)
        throws ServletException, IOException
    {
        resp.setContentType("text/html");
        PrintWriter out = resp.getWriter();
        out.println(output);
    }

    public void destroy()
    {
        System.out.println("Over");
    }
}
```

**输出：**

```java
Advance Java Concepts
output
Over
```

**注意：** 如前所述，`HttpServlet` 类不包含任何抽象方法。因此，程序可以成功运行，而不会覆盖它的所有方法。
但是假设这个类包含所有抽象的方法，那么我们需要覆盖它的所有方法，尽管它们在我们的类中什么都不做。
`HttpServlet` 类的方法原型有：

1.  `public void service(ServletRequest req, ServletResponse res)`
2.  `protected void service(HttpServletRequest req, HttpServletResponse res)`
3.  `protected void doGet(HttpServletRequest req, HttpServletResponse res)`
4.  `protected void doPost(HttpServletRequest req, HttpServletResponse res)`
5.  `protected void doHead(HttpServletRequest req, HttpServletResponse res)`
6.  `protected void doOptions(HttpServletRequest req, HttpServletResponse res)`
7.  `protected void doPut(HttpServletRequest req, HttpServletResponse res)`
8.  `protected void doTrace(HttpServletRequest req, HttpServletResponse res)`
9.  `protected void doDelete(HttpServletRequest req, HttpServletResponse res)`
10. `protected long getLastModified(HttpServletRequest req)`

如果我们的类是抽象的，那么这种方法的不必要的重写就会存在。

**注：** 然而在 NetBeans 等最新 IDE 中，它会通过给抽象方法一个空白体来自动覆盖所有抽象方法，减少了程序员要覆盖的头疼。

### 4. Final

抽象类不能是 `final`，因为它的所有抽象方法都必须在子类中定义。一个具体的类可以被声明为 `final`。

### 5. Interface

一个抽象类不能单独实现一个接口，但它可以通过使用一个子类并提供接口中所有方法的实现来实现一个接口。第一个以该抽象类为祖先的具体类有责任实现接口中的所有方法。

| 抽象类 | 具体类 |
| --- | --- |
| 抽象类是使用 `abstract` 修饰符声明的。 | 具体类是用 `abstract` 修饰符声明的。 |
| 不能使用 `new` 关键字直接实例化抽象类。 | 可以使用 `new` 关键字直接实例化具体的类。 |
| 抽象类可以包含也可以不包含抽象方法。 | 具体类不能包含抽象方法。 |
| 抽象类不能声明为最终类。 | 一个具体的类可以被声明为最终类。 |
| 通过不提供接口的所有方法的实现，实现接口是可能的。为此，需要一个子类。 | 接口中所有方法的简单实现。 |

## 一些要点

-   具体类是抽象类的子类，它实现了它所有的抽象方法。
-   抽象方法不能有主体。
-   抽象类可以像其他类一样有静态字段和静态方法。
-   抽象类不能声明为最终类。
-   只有抽象类可以有抽象方法。
-   私有的、最终的、静态的方法不能是抽象的，因为它不能在子类中被覆盖。
-   抽象类不能有抽象构造函数。
-   抽象类不能有抽象静态方法。
-   如果一个类扩展了一个抽象类，那么它应该定义基础抽象类的所有抽象方法（覆盖）。如果没有，子类（扩展抽象类的类）也必须被定义为抽象类。