# Java 中的 `URLPermission` 类

> 原文：[https://www.geeksforgeeks.org/java-net-urlpermission-class-in-java/](https://www.geeksforgeeks.org/java-net-urlpermission-class-in-java/)

`URLPermission` 类用于表示访问给定 URL 的资源的权限。给定的 URL 作为许可的名称。动作代表请求方法和标题。

## 类声明

```java
public final class URLPermission extends Permission
```

## 构造函数

| 构造函数 | 描述 |
| --- | --- |
| `URLPermission(String url, String actions)` | 该构造函数用于用指定的 URL 和动作创建 `URLPermission` 类的新实例。 |
| `URLPermission(String url)` | 该构造函数用于用指定的 URL 创建 `URLPermission` 类的新实例。 |

## 方法

| 方法 | 描述 |
| --- | --- |
| `equals(Object p)` | 此方法检查两个 `URLPermission` 对象是否相等。 |
| `getActions()` | 该方法以 `String` 格式返回动作，目前是一个规范化的方法列表，并发送请求头列表。 |
| `hashCode()` | 这个方法返回这个对象的哈希值。 |
| `implies(Permission p)` | 该方法检查给定的权限是否由该对象隐含。 |

## 例 1

```java
// Java program to illustrate working of hashCode() method
import java.net.URLPermission;

public class URLPermission {
    public static void main(String[] args) {
        String url = "https://www.geeksforgeeks.org";
        // creating a new URLPermission object
        URLPermission permission = new URLPermission(url, "connect");
        // printing the actions of this URLPermission object
        System.out.println("Actions: " + permission.getActions());
        // printing the hash value of this URLPermission object
        System.out.println("Hashcode: " + permission.hashCode());
    }
}
```

**输出**

```java
Actions: CONNECT:
Hashcode: -1592744539
```

## 例 2

```java
// Java program to illustrate working of equals() method
import java.net.URLPermission;

public class URLPermission {
    public static void main(String[] args) {
        String url1 = "https://www.geeksforgeeks.org";
        String url2 = "https://www.geeksforgeeks.org/data-structure-gq/linked-list-gq/";
        URLPermission permission1 = new URLPermission(url1);
        URLPermission permission2 = new URLPermission(url2);

        if (permission1.equals(permission2)) {
            System.out.println("Both objects are equal");
        } else {
            System.out.println("Both objects are not equal");
        }
    }
}
```

**输出**

```java
Both objects are not equal
```