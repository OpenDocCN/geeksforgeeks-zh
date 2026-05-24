# Method 类的 getTypeParameters() 方法

> 原文: [https://www.geeksforgeeks.org/method-class-gettypeparameters-method-in-java/](https://www.geeksforgeeks.org/method-class-gettypeparameters-method-in-java/)

`Method` 类的 [`getTypeParameters()`](https://www.geeksforgeeks.org/reflection-in-java/) 方法按照声明顺序返回由该方法对象的泛型声明所声明的类型变量对象数组。数组元素表示方法声明的类型变量对象。如果方法对象的泛型声明不包含类型变量，则 `getTypeParameters()` 将返回长度为 0 的数组。

## 语法

```java
public TypeVariable<Method>[] getTypeParameters()
```

## 返回值

这个方法返回一个由这个方法对象的泛型声明所声明的类型变量对象的数组。

## 异常

如果这个方法对象的泛型签名与 JVM 规范中指定的格式不匹配，这个方法抛出 `GenericSignatureFormatError`。

下面的程序说明了 `Method` 类的 `getTypeParameters()` 方法。

### 示例 1

**解释:** 这段代码获取一个类的所有 `Method` 的列表。然后，如果在声明这些方法时定义了一些类型变量，则通过循环迭代这些方法并获取类型变量。如果有一些类型变量可用于这些方法，则打印类型变量名称。

```java
/*
* Program Demonstrate getTypeParameters() method
* of Method Class.
*/
import java.lang.reflect.Method;
import java.lang.reflect.TypeVariable;

public class GFG {

    // In this method, there is a
    // Type parameter N which extends Number class
    public <N extends Number> void getSampleMethod(N n)
    {
    }

    // create main method
    public static void main(String args[])
    {

        try {

            // create class object for class name GFG
            Class c = GFG.class;

            // get list of all Method objects of class GFG
            Method[] methods = c.getMethods();

            // loop through all methods and
            // try to get Type Parameter of Method
            for (Method m : methods) {

                // get TypeVariable array by getTypeParameters() method
                TypeVariable[] types = m.getTypeParameters();

                // print Type Parameter details for every TypeVariable
                for (TypeVariable t : types) {

                    // print type parameter name
                    // along with there method name
                    System.out.println("Type variable for Method Name "
                                       + m.getName() + " is "
                                       + t.getName());
                }
            }
        }
        catch (Exception e) {

            // print Exception Message if
            // any exception occured in program
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
Type variable for Method Name getSampleMethod is N
```

### 示例 2

在这个程序中，方法的类型参数不止一个。在这个程序中，类型参数是使用 `getTypeParameters()` 函数获取的，并打印这些类型参数的详细信息。

```java
/*
* Program Demonstrate getTypeParameters() method
* of Method Class having more than one type
parameter of methods
*/
import java.lang.*;

public class GFG {

    // In this method,
    // there are three Type parameters
    // N which extends Number class,
    // E extends RuntimeException Class
    // and C extends Character class.
    public <N extends Number,
                  E extends RuntimeException,
                        C extends Character> void
    getSampleMethod(N n) throws E
    {
    }

    // In this method,
    // there are Two Type parameters :
    // A which extends the ArrayList class,
    // L extends the LinkedList class
    public <A extends ArrayList, L extends LinkedList> L
    SetSampleMethod(A a, L l)
    {
        return l;
    }

    // create main method of class
    public static void main(String args[])
    {

        try {

            // create class object for
            // class name GFG to get methods list
            // of GFG class
            Class c = GFG.class;

            // get list of all Method objects of
            // class GFG in array of Methods
            Method[] methods = c.getMethods();

            // loop through all methods and
            // try to get Type Parameter of Method
            for (Method m : methods) {

                // get TypeVariable array by
                // getTypeParameters method
                TypeVariable[] types = m.getTypeParameters();

                // If there are 1 or more than 1
                // type variables for the current
                // method of loop then print method name
                if (types.length > 0)
                    System.out.println("\nType variable Details"
                                       + " for Method Name "
                                       + m.getName());

                // print Type Parameter details
                // for Current Method of loop
                for (TypeVariable t : types) {
                    // get bounds for current TypeVariable
                    // and print the Name of TypeVariable and bounds
                    Type[] bounds = t.getBounds();

                    // print TypeVariable name and Bounds
                    System.out.println("Name : "
                                       + t.getName());
                    System.out.println("Bounds : "
                                       + Arrays.toString(bounds));
                }
            }
        }
        catch (Exception e) {
            // print Exception message if some Exception occurs
            e.printStackTrace();
        }
    }
}
```

**输出:**

```java
Type variable Details for Method Name getSampleMethod
Name : N
Bounds : [class java.lang.Number]
Name : E
Bounds : [class java.lang.RuntimeException]
Name : C
Bounds : [class java.lang.Character]

Type variable Details for Method Name SetSampleMethod
Name : A
Bounds : [class java.util.ArrayList]
Name : L
Bounds : [class java.util.LinkedList]
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getTypeParameters--](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getTypeParameters--)