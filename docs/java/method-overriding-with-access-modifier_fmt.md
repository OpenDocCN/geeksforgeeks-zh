# 使用访问修改器覆盖方法

> 原文:[https://www.geeksforgeeks.org/method-overriding-with-access-modifier/](https://www.geeksforgeeks.org/method-overriding-with-access-modifier/)

**先决条件:**[Java 中的方法覆盖](https://www.geeksforgeeks.org/overriding-in-java/)和[Java 中的访问修饰符](https://www.geeksforgeeks.org/access-modifiers-java/)

## 方法覆盖
在任何面向对象的编程语言中，覆盖都是允许子类或子类提供其超类或父类已经提供的方法的特定实现的特性。当子类中的方法与其超类中的方法具有相同的名称、相同的参数或签名以及相同的返回类型(或子类型)时，那么子类中的方法被称为覆盖超类中的方法。
方法覆盖是 java 实现[运行时多态性](https://www.geeksforgeeks.org/dynamic-method-dispatch-runtime-polymorphism-java/)的方法之一。执行的方法版本将由用于调用它的对象决定。如果父类的对象被用来调用方法，那么父类中的版本将被执行，但是如果子类的对象被用来调用方法，那么子类中的版本将被执行。换句话说，是被引用对象的类型(而不是引用变量的类型)决定了被重写方法的哪个版本将被执行。

## 访问修饰符
顾名思义，Java 中的访问修饰符有助于限制类、构造函数、变量、方法或数据成员的范围。java 中有四种类型的访问修饰符:

*   默认-不需要关键字
*   私人的
*   保护
*   公众

## 使用访问修饰符进行方法重写
在使用访问修饰符进行方法重写时，它们只有一个规则，即

> 如果要重写任何方法，被重写的方法(即在子类中声明的方法)不能更严格。

## 按降序排列的访问修饰符限制:

*   私人的
*   系统默认值
*   保护
*   公众的

即私有比默认更受限制，默认比受保护更受限制等等。

### 例 1:

```java
class A {
    protected void method()
    {
        System.out.println("Hello");
    }
}

public class B extends A {

// Compile Time Error
    void method()
    {
        System.out.println("Hello");
    }

public static void main(String args[])
    {
        B b = new B();
        b.method();
    }
}
```

**Output:**

```java
Compile Time Error
```

**注意:**在上面的示例超类中，`A`类定义了一个方法，其访问修饰符是`protected`。在子类`B`中进行方法覆盖时，我们没有定义任何访问修饰符，因此将使用默认的访问修饰符。根据规则，默认的是更受限制的而不是`protected`，所以这个程序会给出编译时错误。我们本可以使用`public`而不是默认，`public`是较少限制的而非`protected`。

### 例 2:

```java
class A {
    protected void method()
    {
        System.out.println("Hello");
    }
}

public class B extends A {
    public void method()
    {
        System.out.println("Hello");
    }

public static void main(String args[])
    {
        B b = new B();
        b.method();
    }
}
```

**Output:**

```java
Hello
```

**注意:**在上面的示例超类中，`A`类定义了一个方法，其访问修饰符是`protected`。在子类`B`中进行方法重写时，我们将访问修饰符定义为`public`。因为`public`访问修饰符的限制比`protected`少，所以这个程序编译成功。