# Java 中的 Java.util.Locale 类 | 集合 2

> 原文: [https://www.geeksforgeeks.org/java-util-locale-class-java-set-2/](https://www.geeksforgeeks.org/java-util-locale-class-java-set-2/)

[Java.util.locale Class in Java | Set 1](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)

## 更多方法

### 1. `getDisplayVariant()`
`Java.util.Locale.getDisplayVariant()` 显示区域的变体。

**语法:**
```java
public final String getDisplayVariant()
```
**参数：**
**返回：**

### 2. `getDisplayVariant(Locale in)`
`Java.util.Locale.getDisplayVariant(Locale in)` 返回“in”Locale 的变体。

**语法:**
```java
public final String getDisplayVariant(Locale in)
```
**参数：**
`in` : the instance local
**返回：**

### 3. `getISO3Language()`
`Java.util.Locale.getISO3Language()` 显示 Locale Language 的 3 个字母缩写。

**语法:**
```java
public String getISO3Language()
```
**参数：**
**返回：**

### 4. `getISOLanguages()`
`Java.util.Locale.getISOLanguages()` 按照 ISO 639 显示 2 个字母的语言缩写列表。

**语法:**
```java
public static String[] getISOLanguages()
```
**参数：**
**返回：**

### 5. `getISOCountries()`
`Java.util.Locale.getISOCountries()` 按照 ISO 3166 显示两个字母的国家缩写列表。

**语法:**
```java
public static String[] getISOCountries()
```
**参数：**
**返回：**

### 6. `getVariant()`
`Java.util.Locale.getVariant()` 返回 Locale 的变体代码。

**语法:**
```java
public String getVariant()
```
**参数：**
**返回：**

### 7. `getLanguage()`
`Java.util.Locale.getLanguage()` 返回区域设置的语言代码，该代码将为空或按照 ISO 639 代码以小写形式显示。

**语法:**
```java
public String getLanguage()
```
**参数：**
**返回：**

### 8. `hashCode()`
`Java.util.Locale.hashCode()` 返回 Locale 的 hashCode。

**语法:**
```java
public int hashCode()
```
**参数：**
**返回：**
`hashcode` for the Locale.

### 9. `toString()`
`Java.util.Locale.toString()` 返回整个 Locale 的字符串表示形式。

**语法:**
```java
public final String toString()
```
**参数：**
**返回：**
`string` representation of Locale.

### 10. `setDefault(Locale newLocale)`
`Java.util.Locale.setDefault(Locale newLocale)` 为 JVM 的 Locale 设置新值。

**语法:**
```java
public static void setDefault(Locale newLocale)
```
**参数：**
**返回：**
`string` representation of Locale.

## 代码示例

```java
// Java Program illustrating the use of methods :
// getDisplayVariant(), getDisplayVariant(Locale in),
// getISO3Language(), getISOLanguages(), getVariant(),
// getISOCountries(), getISOLanguages(), hashCode(),
// getLanguage(), toString(), setDefault()

import java.util.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Creating a new Locale
        Locale geek1 = new Locale("English", "IN", "IND");

        // Use of getDefault() :
        Locale geek2 = Locale.getDefault();

        // Use of getDisplayVariant() :
        System.out.println("\nUse of getDisplayVariant : "
                            + geek1.getDisplayVariant());

        // Use of getDisplayVariant(Locale in) :
        System.out.println("Name of in Locale : "
                +geek2.getDisplayVariant(new Locale("English",
                                          "english", "WNN")));

        // Use of getISO3Language() :
        System.out.println("Language of geek2 : " +
                              geek2.getISO3Language());

        // Use of getISOLanguages() :
        String[] languages = geek2.getISOLanguages();

        // We are not printing the entire list
        System.out.println("\nList of language codes : ");
        for (int i = 1; i < languages.length/20; i++)
            System.out.println(i + ":" + languages[i]);

        // Use of getISOCountries() :
        String[] countries = Locale.getISOCountries();

        // We are not printing the entire list
        System.out.println("\n Countries of geek2 : ");
        for (int i = 1; i < countries.length/30; i++)
            System.out.println(i + ":" + countries[i]);

        // Use of getVariant() :
        System.out.println("\nUse of getVariant : " +
                                geek1.getVariant());

        // Use of getLanguage() :
        System.out.println("Use of getLanguage : " +
                                geek1.getLanguage());

        // Use of hashCode() :
        System.out.println("HashCode for the geek1 : " +
                               geek1.hashCode());

        // Use of toString() :
        System.out.println("String representation for the geek1 : "
                                + geek1.toString());

        // Use of getDefault() :
        Locale geek3 = Locale.getDefault();
        System.out.println("\nInitial Default : " + geek3);

        // Use of setDefault() :
        geek3.setDefault(new Locale("fr", "FRANCE", "MAC"));

        Locale geek4 = Locale.getDefault();
        System.out.println("NEW Default : " + geek4);
    }
}
```

### 输出

```java
Use of getDisplayVariant : IND
Name of in Locale : 
Language of geek2 : eng

List of language codes : 
1:ab
2:ae
3:af
4:ak
5:am
6:an
7:ar
8:as

Countries of geek2 : 
1:AE
2:AF
3:AG
4:AI
5:AL
6:AM
7:AN

Use of getVariant : IND
Use of getLanguage : english
HashCode for the geek1 : -322025782
String representation for the geek1 : english_IN_IND

Initial Default : en_US
NEW Default : fr_FRANCE_MAC
```

本文由**莫希特·古普塔 _OMG 供稿🙂**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `review-team@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。