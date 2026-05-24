# Java 中的 Java.lang.Class 类

> 原文：[https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)

Java 在 `java.lang` 包中提供了一个名为 `Class` 的类。类的实例表示运行的 Java 应用程序中的类和接口。基本的 Java 类型（布尔型、字节型、字符型、短整型、整型、长整型、浮点型和双精度型）和关键字 `void` 也表示为类对象。它没有公共构造函数。类对象由 Java 虚拟机（[JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) ）自动构造。这是 `final` 类，所以我们不能继承它。

`Class` 类方法在[反射](https://www.geeksforgeeks.org/reflection-in-java/) API 中被广泛使用。

## 创建类对象

创建类对象有三种方式：

1.  **`Class.forName(“className”)`**：由于 `Class` 类不包含任何构造函数，因此类中存在静态工厂方法 `Class.forName()`，用于创建 `Class` 类的对象。语法如下：

    ```java
    Class c = Class.forName(String className)
    ```

    上面的语句为作为字符串参数（类名）传递的类创建了 `Class` 对象。请注意，参数 `className` 必须是要为其创建 `Class` 对象的所需类的完全限定名。Java 中返回相同类对象的任何类中的方法也称为工厂方法。要为其创建 `Class` 对象的类名在运行时确定。

2.  **`Myclass.class`**：当我们在类名后写 `.class` 时，它引用表示给定类的 `Class` 对象。它主要用于基本数据类型，并且仅在我们知道类名时使用。要为其创建 `Class` 对象的类名在编译时确定。语法如下：

    ```java
    Class c = int.class
    ```

    请注意，此方法与类名一起使用，而不是与类实例一起使用。例如：

    ```java
    A a = new A();   // Any class A
    Class c = A.class; // No error
    Class c = a.class; // Error
    ```

3.  **`obj.getClass()`**：此方法出现在 `Object` 类中。它返回此（`obj`）对象的运行时类。语法如下：

    ```java
    A a = new A();   // Any class A
    Class c = a.getClass();
    ```

## 方法

1.  **`String toString()`**：此方法将 `Class` 对象转换为字符串。它返回的字符串表示形式是字符串 "class" 或 "interface"，后跟一个空格，然后是类的完全限定名。如果 `Class` 对象表示基本类型，则此方法返回基本类型的名称；如果它表示 `void`，则返回 "void"。

    ```java
    Syntax : 
    public String toString()
    Parameters : 
    NA
    Returns :
    a string representation of this class object.
    Overrides :
    toString in class Object
    ```

    ```java
    // Java program to demonstrate toString() method
    public class Test
    {
        public static void main(String[] args)
                                  throws ClassNotFoundException
        { 
            // returns the Class object for the class 
            // with the specified name 
            Class c1 = Class.forName("java.lang.String");
            Class c2 = int.class;
            Class c3 = void.class;

            System.out.print("Class represented by c1: ");
            // toString method on c1
            System.out.println(c1.toString());

            System.out.print("Class represented by c2: ");
            // toString method on c2
            System.out.println(c2.toString());

            System.out.print("Class represented by c3: ");
            // toString method on c3
            System.out.println(c3.toString());
        }
    }
    ```

    输出：

    ```java
    Class represented by c1: class java.lang.String
    Class represented by c2: int
    Class represented by c3: void
    ```

2.  **`Class<?> forName(String className)`**：如前所述，此方法返回与给定字符串名称的类或接口关联的 `Class` 对象。此方法的另一个变体将在下文讨论。

    ```java
    Syntax : 
    public static Class<?> forName(String className) throws ClassNotFoundException
    Parameters : 
    className - the fully qualified name of the desired class.
    Returns :
    return the Class object for the class with the specified name.
    Throws :
    LinkageError : if the linkage fails
    ExceptionInInitializerError - if the initialization provoked by this method fails
    ClassNotFoundException - if the class cannot be located
    ```

    ```java
    // Java program to demonstrate forName() method
    public class Test
    {
        public static void main(String[] args)
                                  throws ClassNotFoundException
        {
            // forName method
            // it returns the Class object for the class 
            // with the specified name 
            Class c = Class.forName("java.lang.String");

            System.out.print("Class represented by c : " + c.toString());
        }
    }
    ```

    输出：

    ```java
    Class represented by c : class java.lang.String
    ```

3.  **`Class<?> forName(String className, boolean initialize, ClassLoader loader)`**：此方法也返回与给定字符串名称的类或接口关联的 `Class` 对象，并使用给定的类加载器。

    指定的类加载器用于加载类或接口。如果参数 `loader` 为 `null`，则通过引导类加载器加载该类。只有当 `initialize` 参数为 `true` 并且该类之前没有初始化过时，该类才会初始化。

    ```java
    Syntax : 
    public static Class<?> forName(String className,boolean initialize, ClassLoader loader) 
    throws ClassNotFoundException
    Parameters : 
    className - the fully qualified name of the desired class
    initialize - whether the class must be initialized
    loader - class loader from which the class must be loaded
    Returns :
    return the Class object for the class with the specified name.
    Throws :
    LinkageError : if the linkage fails
    ExceptionInInitializerError - if the initialization provoked by this method fails
    ClassNotFoundException - if the class cannot be located
    ```

    ```java
    // Java program to demonstrate forName() method
    public class Test
    {
        public static void main(String[] args)
                                  throws ClassNotFoundException
        {
            // returns the Class object for this class
            Class myClass = Class.forName("Test");

            ClassLoader loader = myClass.getClassLoader();

            // forName method
            // it returns the Class object for the class 
            // with the specified name using the given class loader
            Class c = Class.forName("java.lang.String",true,loader);

            System.out.print("Class represented by c : " + c.toString());
        }
    }
    ```

    输出：

    ```java
    Class represented by c : class java.lang.String
    ```

4.  **`T newInstance()`**：此方法创建由此 `Class` 对象表示的类的新实例。该类被创建，如同通过一个带有空参数列表的 `new` 表达式。如果该类尚未初始化，则会被初始化。

    ```java
    Syntax : 
    public T newInstance() throws InstantiationException,IllegalAccessException
    TypeParameters : 
    T - The class type whose instance is to be returned
    Parameters : 
    NA
    Returns :
    a newly allocated instance of the class represented by this object.
    Throws :
    IllegalAccessException - if the class or its nullary constructor is not accessible.
    InstantiationException - if this Class represents an abstract class, an interface,
    an array class, a primitive type, or void
    or if the class has no nullary constructor; 
    or if the instantiation fails for some other reason.
    ExceptionInInitializerError - if the initialization provoked by this method fails.
    SecurityException - If a security manager, s, is present
    ```

    ```java
    // Java program to demonstrate newInstance() method
    public class Test
    {
        public static void main(String[] args)
                                  throws ClassNotFoundException, InstantiationException,
                                  IllegalAccessException
        {
            // returns the Class object for this class
            Class myClass = Class.forName("Test");

            // creating new instance of this class
            // newInstance method
            Object obj = myClass.newInstance();

            // returns the runtime class of obj
            System.out.println("Class of obj : " + obj.getClass());
        }
    }
    ```

    输出：

    ```java
    Class of obj : class Test
    ```

### 5. `boolean isInstance(Object obj)`
此方法用于判断指定的 `Object` 是否与当前 `Class` 对象所表示的类或接口具有赋值兼容性。它等价于 Java 中的 `instanceof` 运算符。

**语法**
```java
public boolean isInstance(Object obj)
```
**参数**
- `obj`：要检查的对象。

**返回值**
- 如果 `obj` 是此类的一个实例，则返回 `true`；否则返回 `false`。

**示例**
```java
// Java program to demonstrate isInstance() method
public class Test {
    public static void main(String[] args) throws ClassNotFoundException {
        // returns the Class object for the class with the specified name
        Class c = Class.forName("java.lang.String");

        String s = "GeeksForGeeks";
        int i = 10;

        // checking for Class instance using isInstance method
        boolean b1 = c.isInstance(s);
        boolean b2 = c.isInstance(i);

        System.out.println("is s instance of String : " + b1);
        System.out.println("is i instance of String : " + b2);
    }
}
```
**输出**
```
is s instance of String : true
is i instance of String : false
```

### 6. `boolean isAssignableFrom(Class<?> cls)`
此方法用于判断当前 `Class` 对象所表示的类或接口，与指定的 `Class` 参数所表示的类或接口是否相同，或者是其父类或父接口。

**语法**
```java
public boolean isAssignableFrom(Class<?> cls)
```
**参数**
- `cls`：要检查的 `Class` 对象。

**返回值**
- 如果 `cls` 类型的对象可以赋值给当前类的对象，则返回 `true`。

**抛出**
- `NullPointerException`：如果指定的 `Class` 参数为 `null`。

**示例**
```java
// Java program to demonstrate isAssignableFrom() method
public class Test extends Thread {
    public static void main(String[] args) throws ClassNotFoundException, InstantiationException, IllegalAccessException {
        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        // returns the Class object for the class with the specified name
        Class c1 = Class.forName("java.lang.Thread");
        Class c2 = Class.forName("java.lang.String");

        // isAssignableFrom method on c1
        // it checks whether Thread class is assignable from Test
        boolean b1 = c1.isAssignableFrom(myClass);

        // isAssignableFrom method on c2
        // it checks whether String class is assignable from Test
        boolean b2 = c2.isAssignableFrom(myClass);

        System.out.println("is Thread class Assignable from Test : " + b1);
        System.out.println("is String class Assignable from Test : " + b2);
    }
}
```
**输出**
```
is Thread class Assignable from Test : true
is String class Assignable from Test : false
```

### 7. `boolean isInterface()`
此方法用于判断指定的 `Class` 对象是否表示一个接口类型。

**语法**
```java
public boolean isInterface()
```
**参数**
- 无。

**返回值**
- 当且仅当此类表示一个接口类型时返回 `true`；否则返回 `false`。

**示例**
```java
// Java program to demonstrate isInterface() method
public class Test {
    public static void main(String[] args) throws ClassNotFoundException {
        // returns the Class object for the class with the specified name
        Class c1 = Class.forName("java.lang.String");
        Class c2 = Class.forName("java.lang.Runnable");

        // checking for interface type

        // isInterface method on c1
        boolean b1 = c1.isInterface();

        // isInterface method on c2
        boolean b2 = c2.isInterface();

        System.out.println("is String an interface : " + b1);
        System.out.println("is Runnable an interface : " + b2);
    }
}
```
**输出**
```
is String an interface : false
is Runnable an interface : true
```

### 8. `boolean isPrimitive()`
此方法用于判断指定的 `Class` 对象是否表示一个基本类型。

```java
Syntax:
public boolean isPrimitive()
Parameters:
NA
Returns:
return true if and only if this class represents a primitive type else return false
```

```java
// Java program to demonstrate isPrimitive method
public class Test
{
    public static void main(String[] args)
    {
        // returns the Class object associated with an integer;
        Class c1 = int.class;

        // returns the Class object associated with Test class
        Class c2 = Test.class;

        // checking for primitive type

        // isPrimitive method on c1
        boolean b1 = c1.isPrimitive();

        // isPrimitive method on c2
        boolean b2 = c2.isPrimitive();

        System.out.println("is "+c1.toString()+" primitive : " + b1);
        System.out.println("is "+c2.toString()+" primitive : " + b2);
    }
}
```

输出:

```java
is int primitive : true
is class Test primitive : false
```

### 9. `boolean isArray()`
此方法用于判断指定的 `Class` 对象是否表示一个数组类。

```java
Syntax:
public boolean isArray()
Parameters:
NA
Returns:
return true if and only if this class represents an array type else return false
```

```java
// Java program to demonstrate isArray method
public class Test
{
    public static void main(String[] args)
    {
        int a[] = new int[2];

        // returns the Class object for array class
        Class c1 = a.getClass();

        // returns the Class object for Test class
        Class c2 = Test.class;

        // checking for array type

        // isArray method on c1
        boolean b1 = c1.isArray();

        // is Array method on c2
        boolean b2 = c2.isArray();

        System.out.println("is "+c1.toString()+" an array : " + b1);
        System.out.println("is "+c2.toString()+" an array : " + b2);
    }
}
```

输出:

```java
is class [I an array : true
is class Test an array : false
```

### 10. `boolean isAnonymousClass()`
当且仅当这个类是匿名类时，这个方法返回 `true`。匿名类类似于本地类，只是它们没有名称。

```java
Syntax:
public boolean isAnonymousClass()
Parameters:
NA
Returns:
true if and only if this class is an anonymous class.
false,otherwise.
```

### 11. `boolean isLocalClass()`
当且仅当此类是本地类时，此方法返回 `true`。本地类是在 Java 代码块中本地声明的类，而不是作为类的成员。

```java
Syntax:
public boolean isLocalClass()
Parameters:
NA
Returns:
true if and only if this class is a local class.
false,otherwise.
```

### 12. `boolean isMemberClass()`
此方法返回 `true` 当且仅当这个类是一个成员类。成员类是被声明为包含类的非静态成员的类。

```java
Syntax:
public boolean isMemberClass()
Parameters:
NA
Returns:
true if and only if this class is a Member class.
false,otherwise.
```

下面是解释 `isAnonymousClass()` 方法、`isLocalClass()` 方法和 `isMemberClass()` 方法的使用的 Java 程序。

```java
// Java program to demonstrate isAnonymousClass() ,isLocalClass
// and isMemberClass() method

public class Test
{
    // any Member class of Test
    class A{}

    public static void main(String[] args)
    {
        // declaring an anonymous class
        Test t1 = new Test()
        {
            //  class definition of anonymous class
        };

        // returns the Class object associated with t1 object
        Class c1 = t1.getClass();

        // returns the Class object associated with Test class
        Class c2 = Test.class;

        // returns the Class object associated with A class
        Class c3 = A.class;
```

// checking for Anonymous class
// isAnonymousClass method
boolean b1 = c1.isAnonymousClass();
System.out.println("is "+c1.toString()+" an anonymous class : "+b1);

// checking for Local class
// isLocalClass method
boolean b2 = c2.isLocalClass();
System.out.println("is "+c2.toString()+" a local class : " + b2);

// checking for Member class
// isMemberClass method
boolean b3 = c3.isMemberClass();
System.out.println("is "+c3.toString()+" a member class : " + b3);

}
}
```

输出:

```java
is class Test$1 an anonymous class : true
is class Test a local class : false
is class Test$A a member class : true
```

## `boolean isEnum()`

This method returns true if and only if this class was declared as an enum in the source code.

```java
Syntax :
public boolean isEnum()
Parameters :
NA
Returns :
true iff this class was declared as an enum in the source code.
false,otherwise.
```

```java
// Java program to demonstrate isEnum() method

enum Color
{
    RED, GREEN, BLUE;
}

public class Test
{
    public static void main(String[] args)
    {
        // returns the Class object associated with Color(an enum class)
        Class c1 = Color.class;

        // returns the Class object associated with Test class
        Class c2 = Test.class;

        // checking for Enum class
        // isEnum method
        boolean b1 = c1.isEnum();
        boolean b2 = c2.isEnum();

        System.out.println("is "+c1.toString()+" an Enum class : " + b1);
        System.out.println("is "+c2.toString()+" an Enum class : " + b2);
    }
}
```

输出:

```java
is class Color an Enum class : true
is class Test an Enum class : false
```

## `boolean isAnnotation()`

This method determines if this Class object represents an annotation type. Note that if this method returns true, `isInterface()` method will also return true, as all annotation types are also interfaces.

```java
Syntax :
public boolean isAnnotation()
Parameters :
NA
Returns :
return true if and only if this class represents an annotation type else return false
```

```java
// Java program to demonstrate isAnnotation() method

// declaring an Annotation Type
@interface A
{
     // Annotation element definitions
}

public class Test
{
    public static void main(String[] args)
                         throws ClassNotFoundException
    {
        // returns the Class object associated with A  annotation
        Class c1 = A.class;

        // returns the Class object associated with Test class
        Class c2 = Test.class;

        // checking for annotation type
        // isAnnotation method
        boolean b1 = c1.isAnnotation();
        boolean b2 = c2.isAnnotation();

        System.out.println("is "+c1.toString()+" an annotation  : " + b1);
        System.out.println("is "+c2.toString()+" an annotation : " + b2);
    }
}
```

输出:

```java
is interface A an annotation  : true
is class Test an annotation : false
```

## `String getName()`

This method returns the name of the entity (class, interface, array class, primitive type, or void) represented by this Class object, as a String.

```java
Syntax :
public String getName()
Parameters :
NA
Returns :
returns the name of the name of the entity
represented by this object.
```

```java
// Java program to demonstrate getName() method
public class Test
{
    public static void main(String[] args)
    {
        // returns the Class object associated with Test class
        Class c = Test.class;

        System.out.print("Class Name associated with c : ");

        // returns the name of the class
        // getName method
        System.out.println(c.getName());
    }
}
```

输出:

```java
Class Name associated with c : Test
```

## `String getSimpleName()`

This method returns the name of the underlying class as given in the source code. It returns an empty string if the underlying class is anonymous class.

数组的简单名称是附加了“]”的组件类型的简单名称。特别是组件类型为匿名的数组的简单名称是“[]”。

```java
Syntax :
public String getSimpleName()
Parameters :
NA
Returns :
the simple name of the underlying class
```

```java
// Java program to demonstrate getSimpleName() method
public class Test
{
    public static void main(String[] args)
            throws ClassNotFoundException
    {
        // returns the Class object for the class
        // with the specified name
        Class c1 = Class.forName("java.lang.String");

        System.out.print("Class Name associated with c : ");

        // returns the name of the class
        // getName method
        System.out.println(c1.getName());

        System.out.print("Simple class Name associated with c : ");

        // returns the simple name of the class
        // getSimpleName method
        System.out.println(c1.getSimpleName());
    }
}
```

输出:

```java
Class Name associated with c : java.lang.String
Simple class Name associated with c : String
```

## `ClassLoader getClassLoader()`

This method returns the class loader for this class. If the class loader is bootstrap classloader then this method returned null, as bootstrap classloader is implemented in native languages like C, C++.
If this object represents a primitive type or void,then also null is returned.

```java
Syntax :
public ClassLoader getClassLoader()
Parameters :
NA
Returns :
the class loader that loaded the class or interface represented by this object
represented by this object.
Throws :
SecurityException - If a security manager and its checkPermission method
denies access to the class loader for the class.
```

```java
// Java program to demonstrate getClassLoader() method
public class Test
{
    public static void main(String[] args)
                         throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        // returns the Class object for the class
        // with the specified name
        Class c1 = Class.forName("java.lang.String");

        // returns the Class object for primitive int
        Class c2 = int.class;

        System.out.print("Test class loader : ");

        // getting the class loader for Test class
        // getClassLoader method on myClass
        System.out.println(myClass.getClassLoader());

        System.out.print("String class loader : ");

        // getting the class loader for String class
        // we will get null as String class is loaded
        // by BootStrap class loader
        // getClassLoader method on c1
        System.out.println(c1.getClassLoader());

        System.out.print("primitive int loader : ");

        // getting the class loader for primitive int
        // getClassLoader method on c2
        System.out.println(c2.getClassLoader());
    }
}
```

输出:

```java
Test class loader : sun.misc.Launcher$AppClassLoader@73d16e93
String class loader : null
primitive int loader : null
```

## `TypeVariable<Class<T>>[ ] getTypeParameters()`

This method returns an array of [TypeVariable](https://docs.oracle.com/javase/7/docs/api/java/lang/reflect/TypeVariable.html) objects that represent the type variables declared by the generic declaration represented by this [GenericDeclaration](https://docs.oracle.com/javase/7/docs/api/java/lang/reflect/GenericDeclaration.html) object, in declaration order

## `getTypeParameters()` 方法

```java
Syntax : 
public TypeVariable<Class<T>>[] getTypeParameters()
```

**Specified by:**
`getTypeParameters` in interface `GenericDeclaration`

**Parameters :**
NA

**Returns :**
an array of `TypeVariable` objects that represent the type variables declared by this generic declaration represented by this object.

**Throws :**
`GenericSignatureFormatError` - if the generic signature of this generic declaration does not conform to the format specified in JVM.

```java
// Java program to demonstrate getTypeParameters() method

import java.lang.reflect.TypeVariable;

public class Test {
    public static void main(String[] args) throws ClassNotFoundException {
        // returns the Class object for the class 
        // with the specified name 
        Class c = Class.forName("java.util.Set");

        // getting array of TypeVariable for myClass object
        // getTypeParameters method
        TypeVariable[] tv = c.getTypeParameters();

        System.out.println("TypeVariables in " + c.getName() + " class : ");

        // iterating through all TypeVariables
        for (TypeVariable typeVariable : tv) {
            System.out.println(typeVariable);
        }
    }
}
```

**输出:**
```java
TypeVariables in java.util.Set class : 
E
```

## `getSuperclass()` 方法

`Class<? super T> getSuperclass()` : This method returns the `Class` representing the superclass of the entity (class, interface, primitive type or void) represented by this `Class`.
If this `Class` represents either the `Object` class, an interface, a primitive type, or void, then `null` is returned.
If this object represents an array class then the `Class` object representing the `Object` class is returned.

```java
Syntax : 
public Class<? super T> getSuperclass() 
```

**Parameters :**
NA

**Returns :**
the superclass of the class represented by this object

```java
// Java program to demonstrate getSuperclass() method

// base class
class A {
    // methods and fields
}

// derived class
class B extends A {
}

// Driver class
public class Test {
    public static void main(String[] args) throws ClassNotFoundException {
        // returns the Class object associated with Test class
        Class myClass = Test.class;

        // returns the Class object for the class 
        // with the specified name 
        Class c1 = Class.forName("A");
        Class c2 = Class.forName("B");
        Class c3 = Class.forName("java.lang.Object");

        // getSuperclass method returns the superclass of the class represented 
        // by this class object

        System.out.print("Test superclass : ");
        // getSuperclass method on myClass
        System.out.println(myClass.getSuperclass());

        System.out.print("A superclass : ");
        // getSuperclass method on c1
        System.out.println(c1.getSuperclass());

        System.out.print("B superclass : ");
        // getSuperclass method on c2
        System.out.println(c2.getSuperclass());

        System.out.print("Object superclass : ");
        // getSuperclass method on c3
        System.out.println(c3.getSuperclass());
    }
}
```

**输出:**
```java
Test superclass : class java.lang.Object
A superclass : class java.lang.Object
B superclass : class A
Object superclass : null
```

## `getGenericSuperclass()` 方法

`Type getGenericSuperclass()` : This method returns the `Type` representing the direct superclass of the entity (class, interface, primitive type or void) represented by this `Class`.

如果此类表示对象类、接口、基元类型或 void，则返回 null。如果此对象表示数组类，则返回表示对象类的类对象。

```java
Syntax : 
public Type getGenericSuperclass()
```

**Parameters :**
NA

**Returns :**
the superclass of the class represented by this object

**Throws:**
`GenericSignatureFormatError` - if the generic class signature does not conform to the format specified in JVM
`TypeNotPresentException` - if the generic superclass refers to a non-existent type declaration
`MalformedParameterizedTypeException` - if the generic superclass refers to a parameterized type that cannot be instantiated for any reason

```java
// Java program to demonstrate 
// getGenericSuperclass() method
public class Test {
    public static void main(String[] args) throws ClassNotFoundException {
        // returns the Class object associated with Test class
        Class myClass = Test.class;

        // returns the Class object for the class 
        // with the specified name 
        Class c1 = Class.forName("java.util.ArrayList");
        Class c3 = Class.forName("java.lang.Object");

        // getGenericSuperclass method returns the generic 
        // superclass of the class represented 
        // by this class object

        System.out.print("Test superclass : ");
        // getGenericSuperclass method on myClass
        System.out.println(myClass.getGenericSuperclass());

        System.out.print("ArrayList superclass : ");
        // getGenericSuperclass method on c1
        System.out.println(c1.getGenericSuperclass());

        System.out.print("Object superclass : ");
        // getGenericSuperclass method on c3
        System.out.println(c3.getGenericSuperclass());
    }
}
```

**输出:**
```java
Test superclass : class java.lang.Object
Set superclass : java.util.AbstractList<E>
Object superclass : null
```

## `getInterfaces()` 方法

`Class<?>[] getInterfaces()` : This method returns the interfaces implemented by the class or interface represented by this object.

如果此对象表示不实现接口的类或接口，则方法返回长度为 0 的数组。
如果这个对象表示一个基元类型或者 void，那么这个方法返回一个长度为 0 的数组。

```java
Syntax : 
public Class<?>[] getInterfaces()
```

**Parameters :**
NA

**Returns :**
an array of interfaces implemented by this class.

```java
// Java program to demonstrate getInterfaces() method

// base interface
interface A {
    // methods and constant declarations
}

// derived class
class B implements A {
    // methods implementations that were declared in A
}

// Driver class
public class Test {
    public static void main(String[] args) throws ClassNotFoundException {
        // returns the Class object for the class 
        // with the specified name 
        Class c1 = Class.forName("B");
        Class c2 = Class.forName("java.lang.String");

        // getInterface method on c1
        // it returns the interfaces implemented by B class
        Class c1Interfaces[] = c1.getInterfaces();

        // getInterface method on c2
        // returns the interfaces implemented by String class
        Class c2Interfaces[] = c2.getInterfaces();

        System.out.println("interfaces implemented by B class : ");
        // iterating through B class interfaces
        for (Class class1 : c1Interfaces) {
            System.out.println(class1);
        }

        System.out.println("interfaces implemented by String class : ");
        // iterating through String class interfaces
        for (Class class1 : c2Interfaces) {
            System.out.println(class1);
        }
    }
}
```

**输出:**
```java
interfaces implemented by B class : 
interface A
interfaces implemented by String class : 
interface java.io.Serializable
interface java.lang.Comparable
interface java.lang.CharSequence
```

## `getGenericInterfaces()` 方法

`Type[] getGenericInterfaces()` : This method returns the `Type`s representing the interfaces directly implemented by the class or interface represented by this object.

如果此对象表示不实现接口的类或接口，则方法返回长度为 0 的数组。
如果这个对象表示一个基元类型或者 void，那么这个方法返回一个长度为 0 的数组。

## getGenericInterfaces()

**语法：**
```java
public Type[] getGenericInterfaces()
```

**参数：**
NA

**返回值：**
一个由该类实现的接口组成的数组。

**抛出异常：**
- `GenericSignatureFormatError` - 如果泛型类签名不符合 JVM 中指定的格式。
- `TypeNotPresentException` - 如果泛型超接口引用了不存在的类型声明。
- `MalformedParameterizedTypeException` - 如果泛型超接口引用了因任何原因无法实例化的参数化类型。

**示例代码：**
```java
// Java program to demonstrate getGenericInterfaces() method
import java.lang.reflect.Type;

public class Test {
    public static void main(String[] args) throws ClassNotFoundException {
        // returns the Class object for the class with the specified name
        Class c1 = Class.forName("java.util.Set");

        // getGenericInterfaces() on c1
        // it returns the interfaces implemented by Set interface
        Type c1GenericInterfaces[] = c1.getGenericInterfaces();

        System.out.println("interfaces implemented by Set interface : ");

        // iterating through Set class interfaces
        for (Type type : c1GenericInterfaces) {
            System.out.println(type);
        }
    }
}
```

**输出：**
```
interfaces implemented by Set interface :
java.util.Collection<E>
```

## getPackage()

**描述：** 此方法返回此类的包。JVM 架构中的类加载器子系统使用此方法来查找类或接口的包。

**语法：**
```java
public Package getPackage()
```

**参数：**
NA

**返回值：**
该类的包，如果从存档或代码库中无法获得包信息，则返回 `null`。

**示例代码：**
```java
// Java program to demonstrate getPackage() method
public class Test {
    public static void main(String[] args) throws ClassNotFoundException {
        // returns the Class object for the class with the specified name
        Class c1 = Class.forName("java.lang.String");
        Class c2 = Class.forName("java.util.ArrayList");

        // getting package of class
        // getPackage method on c1
        System.out.println(c1.getPackage());

        // getPackage method on c2
        System.out.println(c2.getPackage());
    }
}
```

**输出：**
```
package java.lang, Java Platform API Specification, version 1.8
package java.util, Java Platform API Specification, version 1.8
```

## getFields()

**描述：** 此方法返回一个 `Field` 对象数组，反映由此 `Class` 对象表示的类（及其所有超类）或接口（及其所有超类）的所有可访问公共字段。

**语法：**
```java
public Field[] getFields() throws SecurityException
```

**参数：**
NA

**返回值：**
表示公共字段的 `Field` 对象数组；如果类或接口没有可访问的公共字段，或者此 `Class` 对象表示基元类型或 `void`，则返回长度为 0 的数组。

**抛出异常：**
- `SecurityException` - 如果存在安全管理器 `s`。

**示例代码：**
```java
// Java program to demonstrate getFields() method
import java.lang.reflect.Field;

public class Test {
    public static void main(String[] args) throws SecurityException, ClassNotFoundException {
        // returns the Class object for the class with the specified name
        Class c1 = Class.forName("java.lang.Integer");

        // getFields method on c1
        // it array of fields of Integer class
        Field F[] = c1.getFields();

        System.out.println("Below are the fields of Integer class : ");

        // iterating through all fields of Integer class
        for (Field field : F) {
            System.out.println(field);
        }
    }
}
```

**输出：**
```
Below are the fields of Integer class :
public static final int java.lang.Integer.MIN_VALUE
public static final int java.lang.Integer.MAX_VALUE
public static final java.lang.Class java.lang.Integer.TYPE
public static final int java.lang.Integer.SIZE
public static final int java.lang.Integer.BYTES
```

## getClasses()

**描述：** 此方法返回一个包含 `Class` 对象的数组，这些对象表示由此 `Class` 对象表示的类的所有公共类和接口成员。该数组包含从超类继承的公共类和接口成员，以及由此类声明的公共类和接口成员。

如果此类对象没有公共成员类或接口，则此方法返回长度为 0 的数组。
如果这个 `Class` 对象表示一个基元类型、一个数组类或 `void`，那么这个方法也返回一个长度为 0 的数组。

**语法：**
```java
Class<?>[ ] getClasses()
```

**参数：**
NA

**返回值：**
表示此类公共成员的 `Class` 对象数组。

**抛出异常：**
- `SecurityException` - 如果存在安全管理器 `s`。

**示例代码：**
```java
// Java program to demonstrate getClasses() method
public class Test {
    // base interface
    public interface A {
        // methods and constant declarations
    }

    // derived class
    public class B implements A {
        // methods implementations that were declared in A
    }

    public static void main(String[] args) throws ClassNotFoundException {
        // returns the Class object associated with Test class
        Class c1 = Test.class;

        // getClasses method on c1
        // it returns the array of Class objects containing the all
        // public classes and interfaces represented by Test class
        Class[] c1Classes = c1.getClasses();

        System.out.println("public members of Test class : ");

        // iterating through all public members of Test class
        for (Class class1 : c1Classes) {
            System.out.println(class1);
        }
    }
}
```

**输出：**
```
public members of Test class :
interface Test$A
class Test$B
```

## getMethods()

**描述：** 此方法返回一个 `Method` 对象数组，反映由此 `Class` 对象表示的类或接口的所有可访问公共方法，以及从超类和超接口继承的方法。

**语法：**
```java
public Method[] getMethods() throws SecurityException
```

**参数：**
NA

**返回值：**
表示公共方法的 `Method` 对象数组；如果类或接口没有可访问的公共方法，或者此 `Class` 对象表示基元类型或 `void`，则返回长度为 0 的数组。

**抛出异常：**
- `SecurityException` - 如果存在安全管理器 `s`。

**示例代码：**
```java
// Java program to demonstrate getMethods() method
import java.lang.reflect.Method;

public class Test {
    public static void main(String[] args) throws SecurityException, ClassNotFoundException {
        // returns the Class object for the class with the specified name
        Class c1 = Class.forName("java.lang.Object");

        // getMethods method on c1
        // it returns array of methods of Object class
        Method M[] = c1.getMethods();

        System.out.println("Below are the methods of Object class : ");

        // iterating through all methods of Object class
        for (Method method : M) {
            System.out.println(method);
        }
    }
}
```

**输出：**
（原文输出部分为空，此处保留原样）

## Object类的方法

```java
Below are the methods of Object class : 
public final void java.lang.Object.wait() throws java.lang.InterruptedException
public final void java.lang.Object.wait(long,int) throws java.lang.InterruptedException
public final native void java.lang.Object.wait(long) throws java.lang.InterruptedException
public boolean java.lang.Object.equals(java.lang.Object)
public java.lang.String java.lang.Object.toString()
public native int java.lang.Object.hashCode()
public final native java.lang.Class java.lang.Object.getClass()
public final native void java.lang.Object.notify()
public final native void java.lang.Object.notifyAll()
```

### 27. `getConstructors()`
此方法返回一个`Constructor`对象数组，反映由此`Class`对象表示的类的所有公共构造方法。

```java
Syntax : 
public Constructor<?>[] getConstructors() throws SecurityException
Parameters : 
NA
Returns :
the array of Constructor objects representing the public constructors of this class
and  array of length 0 if the class or interface has no accessible public constructor
or if this Class object represents a primitive type or void.
Throws :
SecurityException - If a security manager, s, is present.
```

```java
// Java program to demonstrate getConstructors() method

import java.lang.reflect.Constructor;

public class Test
{
    public static void main(String[] args) 
            throws SecurityException,ClassNotFoundException
    {
        // returns the Class object for the class 
        // with the specified name 
        Class c1 = Class.forName("java.lang.Boolean");

        // getConstructor method on c1
        // it returns an array of constructors of Boolean class
        Constructor C[] = c1.getConstructors();

        System.out.println("Below are the constructors of Boolean class :");

        // iterating through all constructors
        for (Constructor constructor : C) 
        {
            System.out.println(constructor);
        }
    }
}
```

输出:

```java
Below are the constructors of Boolean class :
public java.lang.Boolean(boolean)
public java.lang.Boolean(java.lang.String)
```

### 28. `getField(String fieldName)`
此方法返回一个`Field`对象，反映由此`Class`对象表示的类或接口的指定公共成员字段。

```java
Syntax : 
public Field getField(String fieldName) throws NoSuchFieldException,SecurityException
Parameters : 
fieldName -  the field name
Returns :
the Field object of this class specified by name
Throws :
NoSuchFieldException - if a field with the specified name is not found.
NullPointerException - if fieldName is null
SecurityException - If a security manager, s, is present.
```

```java
// Java program to demonstrate getField() method

import java.lang.reflect.Field;

public class Test
{
    public static void main(String[] args) 
            throws SecurityException,ClassNotFoundException,
                   NoSuchFieldException
    {
        // returns the Class object for the class 
        // with the specified name 
        Class c1 = Class.forName("java.lang.Integer");

        // getField method on c1
        // it checks a public field in Integer class with specified parameter
        Field f = c1.getField("MIN_VALUE");

        System.out.println("public field in Integer class with MIN_VALUE name :");
        System.out.println(f);
    }
}
```

输出:

```java
public field in Integer class with MIN_VALUE name :
public static final int java.lang.Integer.MIN_VALUE
```

### 29. `getMethod(String methodName,Class… parameterTypes)`
此方法返回一个`Method`对象，反映由此`Class`对象表示的类或接口的指定公共成员方法。

```java
Syntax : 
public Method getMethod(String methodName,Class... parameterTypes) throws 
NoSuchFieldException,SecurityException
Parameters : 
methodName -  the method name
parameterTypes - the list of parameters
Returns :
the method object of this class specified by name
Throws :
NoSuchMethodException - if a method with the specified name is not found.
NullPointerException - if methodName is null
SecurityException - If a security manager, s, is present.
```

```java
// Java program to demonstrate getMethod() method

import java.lang.reflect.Method;

public class Test
{
    public static void main(String[] args) 
            throws SecurityException,ClassNotFoundException,
                   NoSuchMethodException
    {
        // returns the Class object for the class 
        // with the specified name 
        Class c1 = Class.forName("java.lang.Integer");
        Class c2 = Class.forName("java.lang.String");

        // getMethod method on c1
        // it checks for a public Method in Integer class
        Method m = c1.getMethod("parseInt",c2);

        System.out.println("method in Integer class specified by parseInt : ");
        System.out.println(m);
    }
}
```

输出:

```java
public method in Integer class specified by parseInt : 
public static int java.lang.Integer.parseInt(java.lang.String) 
throws java.lang.NumberFormatException
```

### 30. `Constructor<?> getConstructor(Class<?>… parameterTypes)`
此方法返回一个`Constructor`对象，反映由此`Class`对象表示的类的指定公共构造方法。`parameterTypes`参数是一个`Class`对象数组，按声明顺序标识构造方法的形式参数类型。

```java
Syntax : 
public Constructor<?> getConstructor(Class<?>... parameterTypes) 
throws NoSuchMethodException,SecurityException
Parameters : 
parameterTypes - the list of parameters
Returns :
the Constructor object of the public constructor that matches the specified parameterTypes
Throws :
NoSuchMethodException - if a Constructor with the specified parameterTypes is not found.
SecurityException - If a security manager, s, is present.
```

```java
// Java program to demonstrate 
// getConstructor() Constructor

import java.lang.reflect.Constructor;

public class Test
{
    public static void main(String[] args) 
            throws SecurityException,ClassNotFoundException,
                NoSuchMethodException
    {
        // returns the Class object for the class 
        // with the specified name 
        Class c1 = Class.forName("java.lang.Integer");
        Class c2 = Class.forName("java.lang.String");

        // getConstructor method on c1
        // it checks a public Constructor in Integer class
        // with specified parameterTypes
        Constructor c = c1.getConstructor(c2);

        System.out.println("Constructor in Integer class & String parameterType:");
        System.out.println(c);
    }
}
```

输出:

```java
public Constructor in Integer class with String parameterType : 
public java.lang.Integer(java.lang.String) throws java.lang.NumberFormatException
```

**注:** 方法 `getFields()`、`getMethods()`、`getConstructors()`、`getField()`、`getMethod()`、`getConstructor()` 在反射中被广泛使用（参考[这篇](https://www.geeksforgeeks.org/reflection-in-java/)举例）。

### 31. `T cast(Object obj)`
此方法用于将对象强制转换为此`Class`对象表示的类或接口类型。

```java
Syntax : 
public T cast(Object obj)
TypeParameters : 
T - The class type whose object is to be cast
Parameters : 
obj - the object to be cast
Returns :
the object after casting, or null if obj is null
Throws :
ClassCastException - if the object is not null and is not assignable to the type T.
```

## cast()方法

```java
// Java program to demonstrate cast() method
class A
{
   // methods and fields
}

class B extends A 
{
    // methods and fields
}

// Driver Class
public class Test
{
    public static void main(String[] args) 
    {
        A a = new A();
        System.out.println(a.getClass());
        B b = new B();
        // casting b to a
        // cast method
        a = A.class.cast(b);
        System.out.println(a.getClass());
    }
}
```

输出:

```java
class A
class B
```

## asSubclass(Class<U> clazz)

此方法用于将此`Class`对象强制转换为表示由指定类对象表示的类的子类。它总是返回对此类对象的引用。

**语法：**
```java
public <U> Class<? extends U> asSubclass(Class<U> clazz)
```

**类型参数：**
- `U` - 要强制转换为其对象的超类类型

**参数：**
- `clazz` - 要强制转换的超类对象

**返回值：**
此`Class`对象，强制转换为表示指定类的子类。

**抛出：**
`ClassCastException` - 如果此`Class`对象不表示指定类的子类（此处“子类”包括类本身）。

```java
// Java program to demonstrate asSubclass() method
class A
{
   // methods and fields
}

class B extends A 
{
    // methods and fields
}

// Driver Class
public class Test
{
    public static void main(String[] args) 
    {
        A a = new A();
        // returns the Class object for super class(A)
        Class superClass = a.getClass();
        B b = new B();
        // returns the Class object for subclass(B)
        Class subClass = b.getClass();
        // asSubclass method
        // it represent a subclass of the specified class object
        Class cast = subClass.asSubclass(superClass);
        System.out.println(cast);
    }
}
```

输出:

```java
class B
```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢`GeeksforGeeks`并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到`review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。