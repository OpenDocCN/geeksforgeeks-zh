# Java中的Field getBoolean()方法，带示例

> 原文：[https://www.geeksforgeeks.org/field-getboolean-method-in-java-with-examples/](https://www.geeksforgeeks.org/field-getboolean-method-in-java-with-examples/)

`getBoolean()`方法是Java反射机制中`Field`类的一部分，用于获取类中包含的静态或实例布尔字段的值。当一个类包含一个静态或实例布尔字段，并且我们想要得到该字段的值时，可以使用这个方法。

## 语法

```java
public boolean getBoolean(Object obj)
               throws IllegalArgumentException,
                      IllegalAccessException
```

## 参数

该方法接受单个参数`obj`，该参数是要从中提取布尔值的对象。

## 返回值

该方法返回所需的布尔字段的值。

## 异常

该方法抛出以下异常：

1.  `IllegalAccessException`：如果`Field`对象正在执行Java语言访问控制，并且基础字段不可访问，则会引发此异常。
2.  `IllegalArgumentException`：如果指定的对象不是声明基础字段的类或接口的实例，或者如果字段值不能通过扩展转换转换为`boolean`类型，则会引发此异常。
3.  `NullPointerException`：如果指定的对象为空，并且该字段是实例字段，则会引发此异常。
4.  `ExceptionInInitializerError`：如果此方法引发的初始化失败，则会引发此异常。

下面的程序说明`getBoolean()`方法：

### 程序1

```java
// Java program to demonstrate the above method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException,
               IllegalArgumentException,
               IllegalAccessException
    {

        // Create the User class object
        User user = new User();

        // Get the isEmployee field object
        Field field = User.class.getField("isEmployee");

        // Apply getBoolean Method on User Object
        // to get the value of isEmployee field
        boolean value = field.getBoolean(user);

        // print result
        System.out.println("Value of Boolean Field"
                           + " isEmployee is " + value);

        // Now Get the isActive field object
        field = User.class.getField("isActive");

        // Apply getBoolean Method on User Object
        // to get the value of isActive field
        value = field.getBoolean(user);

        // print result
        System.out.println("Value of Boolean Field"
                           + " isActive is " + value);
    }
}

// sample User class
class User {

    // static boolean values
    public static boolean isEmployee = true;
    public static boolean isActive = false;

    public static boolean isEmployee()
    {
        return isEmployee;
    }
    public static void setEmployee(boolean isEmployee)
    {
        User.isEmployee = isEmployee;
    }
    public static boolean isActive()
    {
        return isActive;
    }
    public static void setActive(boolean isActive)
    {
        User.isActive = isActive;
    }
}
```

**输出：**

> Value of Boolean Field isEmployee is true
> Value of Boolean Field isActive is false

### 程序2

```java
// Java program to demonstrate the above method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException,
               IllegalArgumentException,
               IllegalAccessException
    {

        // Create the mathDigit class object
        mathDigit math = new mathDigit();

        // Get the isEmployee field object
        Field field = mathDigit.class.getField("isZero");

        // Apply getBoolean Method on field Object
        // to get the value of isZero field
        boolean value = field.getBoolean(math);

        // print result
        System.out.println("Value: " + value);
    }

    // mathDigit class
    static class mathDigit {

        public static boolean isZero = false;
        public int number;

        public static boolean isZero()
        {
            return isZero;
        }
        public static void setZero(boolean isZero)
        {
            mathDigit.isZero = isZero;
        }
        public int getNumber()
        {
            return number;
        }
        public void setNumber(int number)
        {
            this.number = number;
        }
    }
}
```

**输出：**

> Value: false

**参考文献：** [https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Field.html#getBoolean(java.lang.Object)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Field.html#getBoolean(java.lang.Object))