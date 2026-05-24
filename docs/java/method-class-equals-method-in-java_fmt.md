# Java 中的 Method 类 | equals() 方法

> 原文: [https://www.geeksforgeeks.org/method-class-equals-method-in-java/](https://www.geeksforgeeks.org/method-class-equals-method-in-java/)

`Method` 类的 `equals(Object obj)` 方法将该 `Method` 对象作为参数与指定的对象进行比较。如果 `Method` 对象与传递的对象相同，则此方法返回 `true`。如果两个方法由同一个类声明，并且具有相同的名称、形式参数类型和返回类型，则它们是相同的。

## 语法

```java
public boolean equals(Object obj)
```

## 参数

此方法接受一个强制参数 `obj`，它是要比较的对象。

## 返回值

如果 `Method` 对象与作为参数传递的对象相同，则方法返回 `true`，否则返回 `false`。

下面的程序说明了 `Method` 类的 `equals(Object obj)` 方法：

### 例 1：当两个对象相同时

```java
/*
 * Program Demonstrate equals(Object Obj)
 * method of Method Class.
 */
import java.lang.reflect.Method;

public class GFG {

    public static void main(String[] args)
        throws NoSuchMethodException,
               SecurityException,
               ClassNotFoundException
    {

        // Get all method of class GFGClass
        // and store in an Array of Method Objects
        Method[] methods = GFGClass.class.getMethods();

        // create a method object by passing
        // method name and parameter type
        Method method = GFGClass.class
                            .getMethod("add", String.class);

        System.out.println("First Method object from array "
                           + "create by getMethods():");
        System.out.println(methods[0]);
        System.out.println("Method object created by "
                           + "getMethod():");
        System.out.println(method);

        // compare both objects by equals method
        if (methods[0].equals(method)) {
            System.out.println("Both Method objects"
                               + " are equal");
        }
        else {
            System.out.println("Both Method objects"
                               + " are not equal");
        }
    }
}

// This is Sample Class for which
// the class object are created
class GFGClass {

    // We have two variables in this class
    private String field1;

    public GFGClass()
    {
    }

    // creatin methods
    public String add(String field2)
    {
        return this.field1 + field2;
    }
}
```

**输出：**

```java
First Method object from array create by getMethods():
public java.lang.String GFGClass.add(java.lang.String)
Method object created by getMethod():
public java.lang.String GFGClass.add(java.lang.String)
Both Method objects are equal
```

### 例 2：当两个对象不同时

```java
/*
 * Program Demonstrate equals(Object Obj) method of Method Class.
 */
import java.lang.reflect.Method;

// This is Main Class
public class GFG {

    public static void main(String[] args)
    {

        // Get all method of class GFGClass
        // and store as Array of Method Objects
        Method[] methods = GFGClass.class.getMethods();

        // select any two method and compare
        System.out.println("Methods are :");
        System.out.println(methods[0]);
        System.out.println(methods[1]);
        if (methods[0].equals(methods[1])) {
            System.out.println("Methods are equal");
        }
        else {
            System.out.println("Methods are not equal");
        }
    }
}

// This is Sample Class
class GFGClass {

    // We have two variables in this class
    private String field1;
    private String field2;

    public GFGClass()
    {
    }

    // we have four methods in this class
    public String getField1()
    {
        return field1;
    }

    public void setField1(String field1)
    {
        this.field1 = field1;
    }

    public String getField2()
    {
        return field2;
    }

    public void setField2(String field2)
    {
        this.field2 = field2;
    }
}
```

**输出：**

```java
Methods are :
public java.lang.String GFGClass.getField1()
public void GFGClass.setField1(java.lang.String)
Methods are not equal
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#equals-java.lang.Object-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#equals-java.lang.Object-)