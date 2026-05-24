# 在 Java 的 String 和 StringBuffer 对象上

## equals()

> 原文: [https://www.geeksforgeeks.org/equals-string-stringbuffer-objects-java/](https://www.geeksforgeeks.org/equals-string-stringbuffer-objects-java/)

考虑以下 Java 代码：

```java
// This program prints false
class GFG {
  public static void main(String[] args) {
    StringBuffer sb1 = new StringBuffer("GFG");
    StringBuffer sb2 = new StringBuffer("GFG");
    System.out.println(sb1.equals(sb2));
  }
}
```

**Output:**

```java
false
```

```java
// This program prints true
class GFG {
  public static void main(String[] args) {
    String s1 = "GFG";
    String s2 = "GFG";
    System.out.println(s1.equals(s2));
  }
}
```

**Output:**

```java
true
```

第一个示例的输出为假，第二个示例为真。在第二个例子中，`equals()`的参数属于`String`类，而在第一个例子中，它属于`StringBuffer`类。当`String`对象被传递时，字符串内容被比较。但是当传递`StringBuffer`的对象时，会比较引用，因为`StringBuffer`不会[覆盖`Object`类的`equals`方法](https://www.geeksforgeeks.org/overriding-equals-method-in-java/)。

例如，以下第一个程序打印假，第二个打印真。

```java
// This program prints false
class GFG {
  public static void main(String[] args) {
    String s1 = "GFG";
    StringBuffer sb1 = new StringBuffer("GFG");
    System.out.println(s1.equals(sb1));
  }
}
```

**Output:**

```java
false
```

```java
// This program prints true
class GFG {
  public static void main(String[] args) {
    String s1 = "GFG";
    StringBuffer sb1 = new StringBuffer("GFG");
    String s2 = sb1.toString();
    System.out.println(s1.equals(s2));
  }
}
```

**Output:**

```java
true
```