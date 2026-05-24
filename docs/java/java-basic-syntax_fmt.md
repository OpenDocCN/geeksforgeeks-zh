# Java 基本语法

> 原文：[https://www.geeksforgeeks.org/java-basic-syntax/](https://www.geeksforgeeks.org/java-basic-syntax/)

Java 程序是对象的集合，这些对象通过方法调用相互通信，共同工作。这里简单讨论一下 Java 的[类和对象](https://www.geeksforgeeks.org/classes-objects-java/)、[方法](https://www.geeksforgeeks.org/methods-in-java/)、[实例变量](https://www.geeksforgeeks.org/variables-in-java/)、语法和语义。

## Java 中的基本术语

1.  **对象**：对象是一个类的实例，有行为和状态。
    *   例如：汽车是一个物体，它的`状态`是：品牌、颜色、车牌。
    *   行为：在路上奔跑。
2.  **类**：类是类对象和状态的蓝图（计划）。
    *   例：房子蓝图是类。
3.  **方法**：物体的行为就是方法。
    *   示例：燃油指示灯指示车内剩余燃油量。
4.  **实例变量**：每个对象都有自己唯一的一组实例变量。对象的状态通常由分配给这些实例变量的值创建。

**示例：** 在控制台中编译和运行 java 程序的步骤

```bash
javac GFG.java
java GFG
```

## Java 语言

```java
public class GFG {
    public static void main(String[] args) {
        System.out.println("GFG!");
    }
}
```

**Output**

```java
GFG!
```

**注意：** 当类为公共类时，文件名应为类名。

## 基本语法

### 1. Java 中的注释

Java 中有三种类型的注释。

**i.** 单行注释

```java
// System.out.println("GFG!");
```

**ii.** 多行注释

```java
/*
    System.out.println("GFG!");
    System.out.println("Alice!");
*/
```

**iii.** 文档注释。又叫 `doc` 注释。

```java
/** documentation */
```

### 2. 程序文件名

程序文件的名称应该与扩展名为 `.java` 的类名完全匹配。如果程序没有任何公共类，文件名可以是其他名称。假设你有一个公共类 `GFG`。

```java
GFG.java // valid syntax
*gfg*.java // invalid syntax
```

### 3. 区分大小写

Java 是一种区分大小写的语言，这意味着标识符 `AB`、`Ab`、`aB` 和 `ab` 在 Java 中是不同的。

```java
System.out.println("Alice"); // valid syntax
*s*ystem.out.println("Alice"); // invalid syntax
```

### 4. 类名

**i.** 类的首字母应该是大写。
**ii.** 如果用几个单词组成一个类名，每个内部单词的第一个字母应该大写，下划线是允许的。

```java
class MyJavaProgram    // valid syntax
class myJavaProgram    // invalid syntax
```

### 5. public static void main(String [] args)

Java 程序处理从方法 `main()` 开始。

### 6. 方法名称

**i.** 所有的方法名称都应该以小写字母开头。
**ii.** 如果用几个单词组成方法名，那么内部单词的每个首字母都应该大写，允许下划线。（这在 java 中是允许的，请纠正下面的例子，这两个例子都是正确的语法，但是作为标准，人们在函数名中遵循小写的第一个字符）

```java
public void employeeRecords() // valid syntax
public void EmployeeRecords() // valid syntax
```

### 7. java 中的标识符

**i.** 所有标识符都可以以字母（`A` 到 `Z` 或 `a` 到 `z`）或下划线 `_` 开头。
**ii.** 标识符的第一个字符可以是任意字符组合。
**iii.** 最重要的是标识符区分大小写。
**iv.** 关键字不能用作标识符，因为它是保留字，有一些特殊的含义。

```java
Legal identifiers: MinNumber, total, ak74, hello_world, $amount, _under_value
Illegal identifiers: 74ak, -amount
```

### 8. Java 中的空格

一行只包含空格，可能带有注释，被称为空行，Java 编译器完全忽略它。

### 9. 访问修饰符

这些修饰符控制类和方法的范围。
*   **访问修饰符：** `default`、`public`、`protected`、`private`
*   **非访问修饰符：** `final`、`abstract`、`strictfp`

### 10. Java 关键词

**关键词或保留词** 是一种语言中用于某些内部过程或代表某些预定义动作的词。因此，这些词不允许用作变量名或对象。

| abstract | assert | boolean | break |
| byte | case | catch | char |
| class | const | continue | default |
| do | double | else | enum |
| extends | final | finally | float |
| for | goto | if | implements |
| import | instanceof | int | interface |
| long | native | new | package |
| private | protected | public | return |
| short | static | strictfp | super |
| switch | synchronized | this | throw |
| throws | transient | try | void |
| volatile | while |  |  |