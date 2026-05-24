# java 中的 java.lang.MethodType 类

> 原文: [https://www.geeksforgeeks.org/java-lang-methodtype-class-in-java/](https://www.geeksforgeeks.org/java-lang-methodtype-class-in-java/)

`MethodType` 是一个属于 `java.lang` 包的类。这个类由各种类型的方法组成，这些方法在大多数情况下有助于根据输入对象或方法的参数找到方法类型。

*   `methodType` 的所有实例都是不可变的。这意味着方法类型类的对象不能被任何其他对象数据覆盖。
*   在或多或少的情况下，方法类型对象是从字节码指令中派生出来的。
*   像所有其他类一样，方法类型类也可以单独向常量池表示常量 `_METHOD_TYPE`。
*   类 `MethodType` 的大多数方法都是使用 `static` 定义的，因为这些方法需要绑定到它们的 `MethodType` 类，而不是对象。

**语法:** 类声明

```java
public final class MethodType extends Object implements Serializable {

// MethodType extends Object Class which is root of class hierarchy
// The serialization interface has no methods or fields and serves only
// to identify the semantics of being serializable.

}
```

`MethodType` 类的方法:

| 方法 | 描述 |
| --- | --- |
| `appendParameterTypes(Class<?>... ptypesToInsert)` | 此方法查找或创建一个具有附加参数类型的方法类型。 |
| `appendParameterTypes(List<Class<?>> ptypesToInsert)` | 此方法查找或创建一个具有附加参数类型的方法类型。 |
| `changeParameterType()` | 此方法查找或创建一个具有单个不同参数类型的方法类型。 |
| `changeReturnType()` | 此方法查找或创建具有不同返回类型的方法类型。 |
| `dropParameterTypes()` | 此方法查找或创建一个方法类型，但省略一些参数类型。 |
| `equals()` | 此方法比较指定的对象是否等于此类型。 |
| `erase()` | 此方法将所有引用类型擦除为 `Object`。 |
| `fromMethodDescriptorString()` | 给定方法的字节码描述符拼写，此方法查找或创建方法类型的实例。 |
| `generic()` | 此方法将所有类型（包括引用和基本类型）转换为 `Object`。 |
| `genericMethodType(int objectArgCount)` | 此方法查找或创建一个其组件全为 `Object` 的方法类型。 |
| `genericMethodType(int objectArgCount, boolean finalArray)` | 此方法查找或创建一个其组件为 `Object` 的方法类型，可选地带有尾随的 `Object[]` 数组。 |
| `hashCode()` | 此方法返回此方法类型的哈希码值。 |
| `hasPrimitives()` | 此方法报告此类型是否包含基本参数或返回值。 |
| `hasWrappers()` | 此方法报告此类型是否包含包装器参数或返回值。 |
| `insertParameterTypes(int num, Class<?>... ptypesToInsert)` | 此方法查找或创建一个具有附加参数类型的方法类型。 |
| `insertParameterTypes(int num, List<Class<?>> ptypesToInsert)` | 此方法查找或创建一个具有附加参数类型的方法类型。 |
| `methodType(Class<?> rtype)` | 此方法使用给定的组件查找或创建一个方法类型。 |
| `methodType(Class<?> rtype, Class<?> ptype0)` | 此方法使用给定的组件查找或创建一个方法类型。 |
| `methodType(Class<?> rtype, Class<?>[] ptypes)` | 此方法查找或创建给定方法类型的实例。 |
| `methodType(Class<?> rtype, Class<?> ptype0, Class<?>... ptypes)` | 此方法使用给定的组件查找或创建一个方法类型。 |
| `methodType(Class<?> rtype, List<Class<?>> ptypes)` | 此方法使用给定的组件查找或创建一个方法类型。 |
| `methodType(Class<?> rtype, MethodType ptypes)` | 此方法使用给定的组件查找或创建一个方法类型。 |
| `parameterArray()` | 此方法将参数类型表示为数组（一个便捷方法）。 |
| `parameterCount()` | 此方法返回此方法类型中的参数类型数量。 |
| `parameterList()` | 此方法将参数类型表示为列表（一个便捷方法）。 |
| `parameterType(int)` | 此方法返回此方法类型中指定索引处的参数类型。 |
| `returnType()` | 此方法返回此方法类型的返回类型。 |
| `methodDescriptorString()` | 此方法生成方法类型的字节码描述符表示。 |
| `toString()` | 此方法以 `"(PT0, PT1, ...) RT"` 的形式返回方法类型的字符串表示。 |
| `unwrap()` | 此方法将所有包装器类型转换为其对应的基本类型。 |
| `wrap()` | 此方法将所有基本类型转换为其对应的包装器类型。 |

**本类示例**方法

## Java 语言示例

```java
// Java Program to demonstrate MethodType Class
// from java.lang.invoke package

// Importing required classes from java.lang package
import java.lang.invoke.MethodHandle;
import java.lang.invoke.MethodHandles;
import java.lang.invoke.MethodType;

// Main class
class GFG {

    // Method 1
    // Helper method
    static void hello()
    {
        // Print statement
        System.out.println("GeeksForGeeks");
    }

    // Method 2
    // Main driver method
    public static void main(String[] args) throws Throwable
    {
        // Creating an object MethodHandles class to
        // create an object lookup
        MethodHandles.Lookup lookup
            = MethodHandles.lookup();

        // Returning the type of method used using
        // methodType class

        // Now, we are also invoking the hello() method to
        // print the context present in it
        MethodHandle mh = lookup.findStatic(
            GFG.class, "hello",
            MethodType.methodType(void.class));

        // Lastly invoking invokeExact() method
        // using method handle
        mh.invokeExact();
    }
}
```

**Output**

```java
GeeksForGeeks
```