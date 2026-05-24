# Java 中的 JavaBean 类

> 原文：[https://www.geeksforgeeks.org/javabean-class-java/](https://www.geeksforgeeks.org/javabean-class-java/)

JavaBeans 是[将多个对象封装成一个对象（bean）的类](https://www.geeksforgeeks.org/encapsulation-in-java/)。它是一个 Java 类，应该遵循以下约定：

1.  必须实现 `java.io.Serializable`。
2.  必须有一个公共的无参构造函数。
3.  所有属性必须是私有的，并提供公共的 getter 和 setter 方法。

```java
// Java program to illustrate the
// structure of JavaBean class
public class TestBean {
    private String name;
    public void setName(String name)
    {
        this.name = name;
    }
    public String getName()
    {
        return name;
    }
}
```

## setter 方法的语法

1.  应该是公共的。
2.  返回类型应为空（`void`）。
3.  setter 方法应以 `set` 为前缀。
4.  应该有参数，即它不应是无参方法。

## getter 方法的语法

1.  应该是公共的。
2.  返回类型不应无效，即根据我们的要求，必须给出返回类型。
3.  getter 方法应以 `get` 为前缀。
4.  不应有参数。

对于布尔属性，getter 方法名可以以 `get` 或 `is` 作为前缀。但建议用 `is`。

```java
// Java program to illustrate the
// getName() method on boolean type attribute
public class Test {
    private boolean empty;
    public boolean getName()
    {
        return empty;
    }
    public boolean isempty()
    {
        return empty;
    }
}
```

## 实施

```java
// Java Program of JavaBean class
package geeks;
public class Student implements java.io.Serializable
{
    private int id;
    private String name;
    public Student()
    {
    }
    public void setId(int id)
    {
        this.id = id;
    }
    public int getId()
    {
        return id;
    }
    public void setName(String name)
    {
        this.name = name;
    }
    public String getName()
    {
        return name;
    }
}
```

```java
// Java program to access JavaBean class
package geeks;
public class Test {
    public static void main(String args[])
    {
        Student s = new Student(); // object is created
        s.setName("GFG"); // setting value to the object
        System.out.println(s.getName());
    }
}
```

输出：

```
GFG
```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [`contribute.geeksforgeeks.org`](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。