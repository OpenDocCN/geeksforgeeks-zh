# java 中的 java.lang.reflect.Parameter 类

> 原文: [https://www.geeksforgeeks.org/java-lang-reflect-parameter-class-in-java/](https://www.geeksforgeeks.org/java-lang-reflect-parameter-class-in-java/)

`java.lang.reflect.Parameter` 类提供了关于方法参数的信息，包括它们的名称和修饰符。它还提供了获取参数属性的替代方法。

`Parameter` 类的一些有用的方法有:

1.  `Public GetModifiers()`: It returns the modifier flag of the Parameter represented by this parameter object.
2.  `Public string getName()`: Returns the name of the method parameter.
3.  `Public getParameterizedType()`: Returns the type of the parameter.

`java.lang.reflect.Parameter` 类的所有方法如下:

| way | describe |
| --- | --- |
| `equals(Object object)` | Compare based on executable file and index. |
| [`getAnnotatedType()`](https://www.geeksforgeeks.org/field-getannotatedtype-method-in-java-with-examples/) | Returns an `AnnotatedType` object, which represents that a type is used to specify the type of formal parameter represented by the parameter. |
| `getAnnotation(Class<T> annotationClass)` | Returns the comment of this element of the specified type, or null if such comment exists. |
| [`getAnnotations()`](https://www.geeksforgeeks.org/class-getannotations-method-in-java-with-examples/) | Returns the comments that exist on this element. |
| `getAnnotationsByType(Class<T> annotationClass)` | Returns the comment associated with this element. |
| `getDeclaredAnnotations()` | Returns the comment that appears directly on this element. |
| `getDeclaredAnnotation(Class<T> annotationClass)` | Returns the comment of this element of the specified type, or null if such comment exists directly. |
| `getDeclaringExecutable()` | Returns the executable file that declares this parameter. |
| `getDeclaredAnnotationsByType(Class<T> annotationClass)` | If the comment of the specified type exists directly or indirectly, the comment of the element is returned. |
| [`getModifiers()`](https://www.geeksforgeeks.org/method-class-getmodifiers-method-in-java/) | Gets the modifier flag of this parameter represented by this parameter object. |
| [`getName()`](https://www.geeksforgeeks.org/file-getname-method-in-java-with-examples/) | Returns the name of the parameter. |
| `getParameterizedType()` | Returns a `Type` object that identifies the parameterized type of the parameter represented by the parameter object. |
| [`getType()`](https://www.geeksforgeeks.org/field-gettype-method-in-java-with-examples/) | Returns a `Class` object that identifies the declaration type of the parameter represented by the parameter object. |
| [`hashCode()`](https://www.geeksforgeeks.org/equals-hashcode-methods-java/) | Returns the hash code according to the hash code and index of the executable file. |
| [`isImplicit()`](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Parameter.html#isImplicit--) | Returns true if the parameter is implicitly declared in the source code, otherwise returns false. |
| [`isNamePresent()`](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Parameter.html#isNamePresent--) | Returns true if the parameter has a name. |
| `isSynthetic()` | If a parameter is neither implicitly nor explicitly declared else false |
| [`toString()`](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Parameter.html#toString--) | |

## 示例

```java
// Java program to illustrate Parameter class of
// java.lang.reflect package

// Importing  java.lang.reflect package to
// obtain reflective information about classes and objects
import java.lang.reflect.*;

// Class 1
// Helper class
class Calculate {

    // Function 1
    // To add to numbers
    int add(int a, int b)
    {
        // Returning the sum
        return (a + b);
    }

    // Function 2
    // To multiply two numbers
    int mul(int a, int b)
    {
        // Returning the number obtained
        // after multiplying numbers
        return (b * a);
    }

    // Function 3
    // Substracting two numbers
    long subtract(long a, long b)
    {
        // Return the numbers after substracting
        // second number from the first number
        return (a - b);
    }
}

// Class 2
// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of helper class
        // in the main method
        Class cls = Calculate.class;

        // Getting all the methods of
        // a particular class
        Method[] methods = cls.getDeclaredMethods();

        // Iterating over each method
        // using the for each loop
        for (Method method : methods) {

            // Print and display the method name
            // using getName() method
            System.out.print(
                "Method Name: " + method.getName() + " ");

            // Getting all the parameters of
            // a particular method
            Parameter parameters[] = method.getParameters();

            // Print and display
            System.out.println("\nparameters of "
                               + method.getName()
                               + "() methods: ");

            // Iterating over parameters
            // using for each loop
            for (Parameter parameter : parameters) {

                // Display the type of parameters
                System.out.print(
                    parameter.getParameterizedType() + " ");

                // Print the parameters of method
                System.out.print(parameter.getName() + " ");
            }

            // New line
            System.out.print("\n\n");
        }
    }
}
```

## 输出

```java
Method Name: subtract 
parameters of subtract() methods: 
long arg0 long arg1

Method Name: add 
parameters of add() methods: 
int arg0 int arg1

Method Name: mul 
parameters of mul() methods: 
int arg0 int arg1 
```