# Java中的java.util.Locale类 | 集合1

> 原文：[https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)

顾名思义，`java.util.Locale`类用于执行区域设置任务，为用户提供区域设置信息。

## 声明

```java
public final class Locale
   extends Object
   implements Cloneable, Serializable
```

## 构造方法

*   `Locale(String l)`: 根据给定的语言代码创建区域设置。
*   `Locale(String l, String c)`: 根据给定的语言、国家代码创建区域设置。
*   `Locale(String l, String c, String v)`: 根据给定的语言、国家和变体代码创建区域设置。

## 方法

**1. `getDisplayCountry()`: `java.util.Locale.getDisplayCountry()`** 返回区域设置所属的国家。

**语法：**

```java
public final String getDisplayCountry()
Parameters :

Return :
```

**2. `getDefault()`: `java.util.Locale.getDefault()`** 根据JVM实例返回当前区域设置的默认值。

**语法：**

```java
public static Locale getDefault()
Parameters :

Return :
current - default value for the locale as per the JVM instance.
```

**3. `getCountry()`: `java.util.Locale.getCountry()`** 返回区域设置的国家，可以是空的或者ISO 3166 2字母代码。

**语法：**

```java
public String getCountry()
Parameters :

Return :
```

**4. `equals(Object locale2)`: `java.util.Locale.equals(Object locale2)`** 检查两个locale是否相等。

**语法：**

```java
public boolean equals(Object locale2)
Parameters : 
locale2 : another locale to be compare with.
Return :
returns true if two locales are equal, else false. 
```

**5. `clone()`: `java.util.Locale.clone()`** 创建区域设置的克隆。

**语法：**

```java
public Object clone()
Parameters :

Return :
clone of this instance
```

**6. `getAvailableLocales()`: `java.util.Locale.getAvailableLocales()`** 返回所有已安装区域的数组。

**语法：**

```java
public static Locale[] getAvailableLocales()
Parameters :

Return :
array of installed locales.
```

**7. `getDisplayLanguage()`: `java.util.Locale.getDisplayLanguage()`** 返回带有区域设置的语言。

**语法：**

```java
public final String getDisplayLanguage()
Parameters :

Return :
```

**8. `getDisplayLanguage(Locale in)`: `java.util.Locale.getDisplayLanguage(Locale in)`** 如果可能的话，返回根据“in”Locale本地化的语言。

**语法：**

```java
public String getDisplayLanguage(Locale in)
Parameters : 
in : the instance local
Return :

Exception :
NullPointerException : if "in" is null.
```

**9. `getDisplayName()`: `java.util.Locale.getDisplayName()`** 显示区域设置的名称。

**语法：**

```java
public final String getDisplayName()
Parameters :

Return :
```

**10. `getDisplayLanguage(Locale in)`: `java.util.Locale.getDisplayLanguage(Locale in)`** 返回“in”区域设置的语言。

**语法：**

```java
public final String getDisplayLanguage()
Parameters : 
in : the instance local
Return :
```

**11. `getISO3Country()`: `java.util.Locale.getISO3Country()`** 显示Locale country的3个字母缩写。

**语法：**

```java
public String getISO3Country()
Parameters :

Return :
```

## Java程序示例

```java
// Java Program illustrating the use of methods :
// getDisplayCountry(), getCountry(), equal(), clone(),
// getAvailableLocales(), getDefault(),
// getDisplayLanguage(Locale in), getDisplayLanguage(),
// getDisplayName(Locale in), getDisplayName(),
// getISO3Country()
import java.util.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Creating a new Locale
        Locale geek1 = new Locale("English", "IN");

// Use of getDefault() :
        Locale geek2 = Locale.getDefault();

System.out.println("Locale name : " + geek1);
        System.out.println("Locale name Default : " + geek2);

// Use of getDisplayCountry() :
        System.out.println("\nCountry Name : "
                            + geek1.getDisplayCountry());

// Use of getCountry() :
        System.out.println("Country Name ISO 3166 2-letter code : "
                                            + geek1.getCountry());

// Use of equal() :
        System.out.println("\nIs geek1 equals geek2 : "
                                 + geek1.equals(geek2));

// clone() : geek3 is a clone of geek2
        Locale geek3 = (Locale) geek2.clone();

// Locale : geek3
        System.out.println("Locale geek3 same as geek2 : "
                                                + geek3);

// Use of getAvailableLocales()
        Locale[] geek4 = Locale.getAvailableLocales();

// We are not printing all the locales.
        System.out.println("\nInstalled locales are : ");
        for (int i = 1; i < geek4.length/10; i++)
            System.out.println(i + ":" + geek4[i]);

// Use of getDisplayLanguage() :
        System.out.println("\ngeek2 Language : "
                        + geek2.getDisplayLanguage());

// Use of getDisplayLanguage(Locale in) :
        System.out.println("Language of in Locale : "
          + geek1.getDisplayLanguage(new Locale("France", "French")));

// Use of getDisplayName :
        System.out.println("\nUse of getDisplayName : "
                              + geek1.getDisplayName());

// Use of getDisplayName(Locale in) :
        System.out.println("Name of in Locale : "
          + geek2.getDisplayName(new Locale("English", "english")));

// Use of getISO3Country() :
        System.out.println("\nISO3 Country Name of geek3 : "
                                    + geek3.getISO3Country());

}
}
```

## 输出

```java
Locale name : english_IN
Locale name Default : en_US

Country Name : India
Country Name ISO 3166 2-letter code : IN

Is geek1 equals geek2 : false
Locale geek3 same as geek2 : en_US

Installed locales are : 
1:ar_AE
2:ar_JO
3:ar_SY
4:hr_HR
5:fr_BE
6:es_PA
7:mt_MT
8:es_VE
9:bg
10:zh_TW
11:it
12:ko
13:uk
14:lv
15:da_DK

geek2 Language : English
Language of in Locale : english

Use of getDisplayName : english (India)
Name of in Locale : English (United States)

ISO3 Country Name of geek3 : USA
```

**下一个：** [Java.util.Locale 类在 Java | Set 2](https://www.geeksforgeeks.org/java-util-locale-class-java-set-2/)

本文由**Mohit Gupta_OMG**供稿🙂。如果你喜欢GeeksforGeeks并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。