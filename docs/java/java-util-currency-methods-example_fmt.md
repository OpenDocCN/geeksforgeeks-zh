# java.util.Currency 方法示例

> 原文: [https://www.geeksforgeeks.org/java-util-currency-methods-example/](https://www.geeksforgeeks.org/java-util-currency-methods-example/)

这个类代表货币。这里，货币由他们的 [ISO 4217](http://www.iso.org/iso/home/standards/currency_codes.htm) 货币代码识别。ISO 4217 的目的是建立国际公认的货币表示代码。货币可以用两种方式在代码中表示:三个字母的字母代码和三位数的数字代码。

```
                        util.Currency methods in Java
               /        /           |            \         \
  getCurrency   getInstance  getDisplayName   getSymbol   getDefaultFractionDigits
```

## 一些货币类方法:

### 1. `getCurrencyCode()`
`java.util.Currency.getCurrencyCode()` 方法返回传递的 currency 参数的 ISO 4217 货币代码。

**语法:**
```java
public String getCurrencyCode()
```
**返回:**
传递的参数的 ISO 4217 货币代码。

### 2. `getInstance()`
`java.util.Currency.getInstance()` 方法为 Currency 代码创建货币实例。

**语法:**
```java
public static Currency getInstance(String cCode)
```
**参数:**
`cCode` - 传递的货币参数的 ISO 4217 货币代码。
**返回:**
Currency 代码的货币实例。

### 3. `getDefaultFractionDigits()`
`java.util.Currency.getDefaultFractionDigits()` 方法返回默认的参数化货币分数位数。

**语法:**
```java
public int getDefaultFractionDigits()
```
**返回:**
返回参数化货币的默认分数位数。

### 4. `getDisplayName()`
`java.util.Currency.getDisplayName()` 方法生成参数化货币代码的货币名称。

**语法:**
```java
public String getDisplayName()
```
**返回:**
参数化货币代码的货币名称。

### 5. `getSymbol()`
`java.util.Currency.getSymbol()` 方法返回参数化货币代码的货币符号。如果没有符号，则返回正常的货币代码。

**语法:**
```java
public String getSymbol()
```
**返回:**
参数化货币代码的货币符号。

## 解释 Currency 类中 `getInstance()`，`getCurrencyCode()`，`getDefaultFractionDigits()`，`getDisplayName()`，`getSymbol()` 方法的 Java 代码

```java
// Java program explaining Currency class methods
// getInstance(), getCurrencyCode(),getDefaultFractionDigits()
// getDisplayName(), getSymbol()
import java.util.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Use of getInstance() method to 'AUD' instance
        Currency c1 = Currency.getInstance("AUD"); //Australian Dollar
        Currency c2 = Currency.getInstance("JPY");  //Japan Yen
        Currency c3 = Currency.getInstance("USD");  //Japan Yen

        // Use of getCurrencyCode() method
        String cCode1 = c1.getCurrencyCode();
        String cCode2 = c2.getCurrencyCode();
        System.out.println("Australian Dollar code : " + cCode1);
        System.out.println("Japan Yen code : " + cCode2);
        System.out.println("");

        // Use of getDefaultFractionDigits() method
        int D1 = c1.getDefaultFractionDigits();
        System.out.println("AUD Fraction digits : " + D1);
        int D2 = c2.getDefaultFractionDigits();
        System.out.println("JPY fraction digits : " + D2);
        System.out.println("");

        // Use of getDisplayName() method
        System.out.println("AUD Display : "+c1.getDisplayName());
        System.out.println("JPY Display : "+c2.getSymbol());
        System.out.println("");

        // Use of getSymbol() method
        System.out.println("JPY Symbol : "+c2.getSymbol());
        System.out.println("USD Symbol : "+c3.getSymbol());
    }
}
```

**输出:**
```
Australian Dollar code : AUD
Japan Yen code : JPY

AUD Fraction digits : 2
JPY fraction digits : 0

AUD Display : Australian Dollar
JPY Display : JPY

JPY Symbol : JPY
USD Symbol : $
```

**ISO 4217 货币代码列表参考链接:**
[http://www.xe.com/iso4217.php](http://www.xe.com/iso4217.php)

本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。