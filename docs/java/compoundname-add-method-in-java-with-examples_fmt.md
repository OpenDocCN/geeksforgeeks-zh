# Java 中的 `CompoundName` `add()` 方法示例

> 原文：[https://www.geeksforgeeks.org/compoundname-add-method-in-java-with-examples/](https://www.geeksforgeeks.org/compoundname-add-method-in-java-with-examples/)

`javax.naming.CompoundName` 类的 `add()` 方法用于将组件添加到 `CompoundName` 对象中。有两种不同的添加方法。

## 1. `add(int, String)`

此方法用于在此复合名称的指定位置 `posn` 添加一个组件。该位置之后的其他组件将向上移动一个位置以容纳新组件。

**语法：**

```java
public Name add(int posn, String comp)
         throws InvalidNameException
```

**参数：** 该方法接受：
*   `posn` 是添加新组件的索引，并且
*   `comp` 是要添加到复合名称对象中的新组件。

**返回值：** 这个方法返回更新后的 `CompoundName`，而不是一个新的对象。返回值不能为空。

**异常：** 如果 `posn` 超出范围，此方法将抛出 `ArrayIndexOutOfBoundsException`；如果在指定位置添加 `comp` 将违反复合名称的语法，则抛出 `InvalidNameException`。

下面的程序说明了 `CompoundName.add()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// CompoundName.add()

import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {
        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", "@");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName CompoundName1
            = new CompoundName(
                "1@2@3@4@5@6@7",
                props);

        // apply add() to add
        // new component at posn 0
        CompoundName newCompoundName
            = (CompoundName)
                  CompoundName1.add(0, "000");

        // print value
        System.out.println(
            "Updated CompoundName Object: "
            + newCompoundName);
    }
}
```

**输出：**

```java
Updated CompoundName Object: 000@1@2@3@4@5@6@7
```

**程序 2：**

```java
// Java program to demonstrate
// CompoundName.add() method

import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {
        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", "/");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName CompoundName1
            = new CompoundName(
                "c/e/d/v/a/b/z/y/x/f",
                props);

        // apply add() to add
        // new component at posn 9
        CompoundName newCompoundName
            = (CompoundName)
                  CompoundName1.add(
                      9, "zzzzz");

        // print value
        System.out.println(
            "Updated CompoundName Object: "
            + newCompoundName);
    }
}
```

**输出：**

```java
Updated CompoundName Object: c/e/d/v/a/b/z/y/x/zzzzz/f
```

## 2. `add(String)`

此方法用于在此复合名称的末尾添加一个组件。

**语法：**

```java
public Name add(String comp)
       throws InvalidNameException
```

**参数：** 此方法接受 `comp`，这是要添加到复合名称对象末尾的新组件。

**返回值：** 这个方法返回更新后的 `CompoundName`，而不是一个新的对象。返回值不能为空。

**异常：** 如果在名称末尾添加 `comp` 会违反复合名称的语法，此方法将抛出 `InvalidNameException`。

下面的程序说明了 `CompoundName.add()` 方法：

**程序 1：**

```java
// Java program to demonstrate
// CompoundName.add()

import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {
        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", "@");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName CompoundName1
            = new CompoundName(
                "1@2@3@4@5@6@7",
                props);

        // apply add() to add
        // new component at end
        CompoundName newCompoundName
            = (CompoundName)
                  CompoundName1.add("9");

        // print value
        System.out.println(
            "Updated CompoundName Object: "
            + newCompoundName);
    }
}
```

**输出：**

```java
Updated CompoundName Object: 1@2@3@4@5@6@7@9
```

**程序 2：**

```java
// Java program to demonstrate
// CompoundName.add() method

import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {
        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", "/");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName CompoundName1
            = new CompoundName(
                "c/e/d/v/a/b/z/y/x/f",
                props);

        // apply add() to add
        // new component at end
        CompoundName newCompoundName
            = (CompoundName)
                  CompoundName1.add("ppp");

        // print value
        System.out.println(
            "Updated CompoundName Object: "
            + newCompoundName);
    }
}
```

**输出：**

```java
Updated CompoundName Object: c/e/d/v/a/b/z/y/x/f/ppp
```

参考文献：
[https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#add(int, java.lang.String)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#add(int, java.lang.String))
[https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#add(java.lang.String)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#add(java.lang.String))