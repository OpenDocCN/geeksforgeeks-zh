# java 中的 java.lang.reflect.Constructor 类

> 原文: [https://www.geeksforgeeks.org/java-lang-reflect-constructor-class-in-java/](https://www.geeksforgeeks.org/java-lang-reflect-constructor-class-in-java/)

`Constructor` 类用于管理构造函数元数据，如构造函数的名称、构造函数的参数类型和构造函数的访问修饰符。我们可以检查类的构造函数，并在运行时实例化对象。对于类中声明的每个公共构造函数，`Constructor[]` 数组将有一个 `Constructor` 实例。

为了获得构造器对象，一个可以从类对象中获得构造器类对象。

**参数:** `T` - 声明构造函数的类

实现的接口如下:

*   注释删除
*   泛型声明
*   成员

## 插图

```java
Class aClass = Employee.class;
Constructor[] constructors = aClass.getConstructors();
```

## 先决条件

让我们讨论一些获取构造函数信息的方法

1.  `getConstructors()`: 此方法可以获取相应类中所有的公共构造函数。它返回一个构造函数数组。
2.  `getDeclaredConstructors()`: 一个类可以获取其自身所有的构造函数，无论是否为 `public`。
3.  `getName()`: 你可以获取每个构造函数的名称。
4.  `getModifiers()`: 此方法返回一个整数，表示此 `Constructor` 对象所表示的构造函数的 Java 语言修饰符。应使用 `Modifier` 类来解码修饰符。
5.  `getParameterTypes()`: 此方法返回特定构造函数的参数类型。

## 主要方法

此外，该类的主要方法如下表所示:

| 方法 | 描述 |
| --- | --- |
| `equals(Object obj)` | 将此构造函数与指定对象进行比较。 |
| `getAnnotatedReceiverType()` | 返回一个 `AnnotatedType` 对象，该对象表示使用类型来指定此可执行对象所表示的方法/构造函数的接收者类型。 |
| `getAnnotatedReturnType()` | 返回一个 `AnnotatedType` 对象，该对象表示使用类型来指定此可执行对象所表示的方法/构造函数的返回类型。 |
| `getAnnotation(Class<T> annotationClass)` | 返回此元素的指定类型的注解，如果不存在此类注解，则返回 `null`。 |
| `getDeclaredAnnotations()` | 返回直接出现在此元素上的注解。 |
| `getDeclaringClass()` | 返回一个 `Class` 对象，该对象表示声明此对象所表示的可执行文件的类或接口。 |
| `getExceptionTypes()` | 返回一个 `Class` 对象数组，这些对象表示此对象所表示的可执行文件声明要抛出的异常类型。 |
| `getGenericExceptionTypes()` | 返回一个 `Type` 对象数组，这些对象表示此可执行对象声明要抛出的异常。 |
| `getGenericParameterTypes()` | 返回一个 `Type` 对象数组，这些对象按声明顺序表示此对象所表示的可执行文件的形式参数类型。 |
| `hashCode()` | 返回此构造函数的哈希码。 |
| `isSynthetic()` | 如果此构造函数是一个合成构造函数，则返回 `true`。 |
| `isVarArgs()` | 如果此构造函数被声明为接受可变数量的参数，则返回 `true`。 |

## 示例

```java
// Java program to show uses of Constructor class
// present in java.lang.reflect package

// Importing package to that examine and
// introspect upon itself
import java.lang.reflect.*;

// Class 1
// Helper class
class Employee {

    // Member variables of this class
    int empno;
    String name;
    String address;

    // Constructor of this class

    // Constructor 1
    public Employee(int empno, String name, String address) {
        // 'this' keyword refers to the
        // current object itself
        this.empno = empno;
        this.name = name;
        this.address = address;
    }

    // Constructor 2
    public Employee(int empno, String name) {
        this.empno = empno;
        this.name = name;
    }

    // Constructor 3
    private Employee(String address) {
        this.address = address;
    }

    // Constructor 4
    protected Employee(int empno) {
        this.empno = empno;
    }
}

// Class 2
// Main class
public class GFG {

    // Main driver method
    public static void main(String args[]) {
        // Creating an object of above class
        // in the main() method
        Class c = Employee.class;

        // Display message
        System.out.println("All public constructor are :");

        Constructor[] cons = c.getConstructors();

        for (Constructor con : cons)
            // It will return all public constructor
            System.out.print(con.getName() + " ");

        // Display message for better readability
        System.out.println(
            "\n\nAll constructor irrespective of access modifiers");

        // Getting constructors of this class
        // using getDeclaredConstructors() method
        cons = c.getDeclaredConstructors();

        // Iterating to print all constructors
        for (Constructor con : cons)
            System.out.print(con.getName() + " ");

        // Display message
        System.out.println(
            "\n\naccess modifiers of each constructor");

        // Iterating to get all the access modifiers
        for (Constructor con : cons)
            // Print all the access modifiers for all
            // constructors
            System.out.print(
                Modifier.toString(con.getModifiers())
                + " ");

        // Parameters types

        // Display message only
        System.out.println(
            "\n\ngetting parameters type of each constructor");

        // Iterating to get parameter types of each
        // constructor using for-each loop
        for (Constructor con : cons) {
            Class[] parameratertypes
                = con.getParameterTypes();

            for (Class c1 : parameratertypes) {
                // Print and display parameter types of all
                // constructors
                System.out.print(c1.getName() + " ");
            }

            // Here we are done with inner loop
            // New line
            System.out.println();
        }
    }
}
```

## 输出

```java
All public constructor are :
Employee Employee

All constructor irrespective of access modifiers
Employee Employee Employee Employee

access modifiers of each constructor
protected private public public

getting parameters type of each constructor
int 
java.lang.String 
int java.lang.String 
int java.lang.String java.lang.String 
```