# Java String contains()方法示例

> 原文：[https://www.geeksforgeeks.org/java-string-contains-method-example/](https://www.geeksforgeeks.org/java-string-contains-method-example/)

`java.lang.String.contains()`方法搜索给定字符串中的字符序列。如果在该字符串中找到字符值序列，则返回 `true`，否则返回 `false`。

## 方法实现

```java
public boolean contains(CharSequence sequence)
{
 return indexOf(sequence.toString()) > -1;
}
```

这里发生字符序列到字符串的转换，然后调用`indexOf()`方法。`indexOf()`方法如果找到字符串则返回 `0` 或更高的数字，否则返回 `-1`。所以，执行后，如果存在字符值序列，`contains()`方法返回 `true`，否则返回 `false`。

## 语法

```java
public boolean contains(CharSequence sequence)
```

**参数：**
- `sequence`：这是要搜索的字符序列。

**异常：**
- `NullPointerException`：如果 `seq` 为 `null`。

## 示例：检查字符序列是否存在

### Java 代码

```java
// Java program to demonstrate working
// contains() method
class Gfg {

    // Driver code
    public static void main(String args[])
    {
        String s1 = "My name is GFG";

        // prints true
        System.out.println(s1.contains("GFG"));

        // prints false
        System.out.println(s1.contains("geeks"));
    }
}
```

### 输出

```java
true
false
```