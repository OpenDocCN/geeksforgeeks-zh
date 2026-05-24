# Java中的Byte类

> 原文：[https://www.geeksforgeeks.org/java-lang-byte-class-java/](https://www.geeksforgeeks.org/java-lang-byte-class-java/)

`Byte`类是基元类型`byte`的[包装类](https://www.geeksforgeeks.org/wrapper-classes-java/)，它包含几种有效处理字节值的方法，如将其转换为字符串表示，反之亦然。`Byte`类的对象可以保存单个字节值。初始化一个`Byte`对象主要有两个构造函数：

*   **`Byte(byte b)`**：创建一个用提供的值初始化的`Byte`对象。

```java
Syntax:  public Byte(byte b)
Parameters :
b : value with which to initialize
```

*   **`Byte(String s)`**：用字符串表示提供的字节值创建一个`Byte`对象。默认基数为10。

```java
Syntax : public Byte(String s) 
                    throws NumberFormatException
Parameters :
s : string representation of the byte value 
Throws :
NumberFormatException : If the string provided does not represent any byte value.
```

## `Byte`类中的字段

1.  [**`static int BYTES`**](https://www.geeksforgeeks.org/byte-class-fields-in-java-with-example/)：以二进制补码形式表示一个字节值的字节数。
2.  [**`static byte MAX_VALUE`**](https://www.geeksforgeeks.org/byte-class-fields-in-java-with-example/)：保存一个字节可以拥有的最大值的常数，2^7-1。
3.  [**`static byte MIN_VALUE`**](https://www.geeksforgeeks.org/byte-class-fields-in-java-with-example/)：一个常量，保存一个字节可以拥有的最小值，-2^7。
4.  [**`static int SIZE`**](https://www.geeksforgeeks.org/byte-class-fields-in-java-with-example/)：二进制补码二进制形式中用于表示一个字节值的位数。
5.  [**`static Class<Byte> TYPE`**](https://www.geeksforgeeks.org/byte-class-fields-in-java-with-example/)：代表原始类型`byte`的类实例。

## 方法

1.  [**`toString()`**](https://www.geeksforgeeks.org/byte-tostring-method-in-java-with-examples/)：返回字节值对应的字符串。

```java
Syntax : public String toString(byte b)
Parameters :
b : byte value for which string representation required.
```

2.  **`valueOf()`**：返回用提供的值初始化的`Byte`对象。

```java
Syntax : public static Byte valueOf(byte b)
Parameters :
b : a byte value
```

3.  另一个重载函数`valueOf(String val, int radix)`，提供类似于`new Byte(Byte.parseByte(val, radix))`的函数。

```java
Syntax : public static Byte valueOf(String val, int radix)
            throws NumberFormatException
Parameters :
val : String to be parsed into byte value
radix : radix to be used while parsing
Throws :
NumberFormatException : if String cannot be parsed to a byte value in given radix.
```

4.  另一个重载函数`valueOf(String val)`，提供类似于`new Byte(Byte.parseByte(val, 10))`的功能。

```java
Syntax : public static Byte valueOf(String s)
           throws NumberFormatException
Parameters :
s : a String object to be parsed as byte
Throws :
NumberFormatException : if String cannot be parsed to a byte value in given radix.
```

5.  **`parseByte()`**：通过解析提供的基数字符串返回字节值。不同于`valueOf()`，因为它返回一个基本`byte`值，而`valueOf()`返回`Byte`对象。

```java
Syntax : public static byte parseByte(String val, int radix)
             throws NumberFormatException
Parameters :
val : String representation of byte 
radix : radix to be used while parsing
Throws :
NumberFormatException : if String cannot be parsed to a byte value in given radix.
```

6.  另一个重载方法只包含字符串作为参数，默认情况下基数设置为10。

```java
Syntax : public static byte parseByte(String val)
             throws NumberFormatException
Parameters :
val : String representation of byte 
Throws :
NumberFormatException : if String cannot be parsed to a byte value in given radix.
```

7.  **`decode()`**：返回一个`Byte`对象，保存所提供字符串的解码值。提供的字符串必须是以下形式，否则将抛出`NumberFormatException`异常：
    *   十进制 - `(符号)十进制_数字`
    *   十六进制 - `(符号)"0x"十六进制_数字`
    *   十六进制 - `(符号)"0X"十六进制_数字`
    *   八进制 - `(符号)"0"八进制_数字`

```java
Syntax : public static Byte decode(String s)
             throws NumberFormatException
Parameters :
s : encoded string to be parsed into byte val
Throws :
NumberFormatException : If the string cannot be decoded into a byte value
```

8.  [**`byteValue()`**](https://www.geeksforgeeks.org/byte-bytevalue-method-in-java-with-examples/)：返回与该`Byte`对象对应的`byte`值。

```java
Syntax : public byte byteValue()
```

9.  **`shortValue()`**：返回与该`Byte`对象对应的`short`值。

```java
Syntax : public short shortValue()
```

10. [**`intValue()`**](https://www.geeksforgeeks.org/byte-intvalue-method-in-java-with-examples/)：返回与该`Byte`对象对应的`int`值。

```java
Syntax : public int intValue()
```

11. [**`longValue()`**](https://www.geeksforgeeks.org/byte-longvalue-method-in-java-with-examples/)：返回该`Byte`对象对应的`long`值。

```java
Syntax : public long longValue()
```

12. **`doubleValue()`**：返回与该`Byte`对象对应的`double`值。

```java
Syntax : public double doubleValue()
```

13. **`floatValue()`**：返回与该`Byte`对象对应的`float`值。

```java
Syntax : public float floatValue()
```

14. [**`hashCode()`**](https://www.geeksforgeeks.org/byte-hashcode-method-in-java-with-examples/)：返回该`Byte`对象对应的`hashCode`。

```java
Syntax : public int hashCode()
```

15. [**`equals()`**](https://www.geeksforgeeks.org/byte-equals-method-in-java-with-examples/)：用于比较两个`Byte`对象的相等性。如果两个对象包含相同的字节值，则此方法返回`true`。仅当检查是否相等时才应使用。在所有其他情况下，应首选`compareTo`方法。

```java
Syntax : public boolean equals(Object obj)
Parameters :
obj : object to compare with
```

16. [**`compareTo()`**](https://www.geeksforgeeks.org/byte-compareto-method-in-java-with-examples/)：用于比较两个`Byte`对象的数值是否相等。当比较两个字节的数值是否相等时，应该使用这种方法，因为它可以区分较小的值和较大的值。返回小于0，0的值，对于小于、等于和大于，返回大于0的值。

```java
Syntax : public int compareTo(Byte b)
Parameters :
b : Byte object to compare with
```

17. [**`compare()`**](https://www.geeksforgeeks.org/byte-compare-method-in-java-with-examples/)：用于比较两个原始`byte`值是否数值相等。由于它是一个静态方法，因此可以在不创建任何`Byte`对象的情况下使用。

```java
Syntax : public static int compare(byte x, byte y)
Parameters :
x : byte value
y : another byte value
```

### Java示例代码

```java
// Java program to illustrate
// various methods of Byte class
public class Byte_test 
{
    public static void main(String[] args) 
    {

        byte b = 55;
        String bb = "45";

        // Construct two Byte objects
        Byte x = new Byte(b);
        Byte y = new Byte(bb);

        // toString()
        System.out.println("toString(b) = " + Byte.toString(b));

        // valueOf()
        // return Byte object
        Byte z = Byte.valueOf(b);
        System.out.println("valueOf(b) = " + z);
        z = Byte.valueOf(bb);
        System.out.println("ValueOf(bb) = " + z);
        z = Byte.valueOf(bb, 6);
        System.out.println("ValueOf(bb,6) = " + z);

        // parseByte()
        // return primitive byte value
        byte zz = Byte.parseByte(bb);
        System.out.println("parseByte(bb) = " + zz);
        zz = Byte.parseByte(bb, 6);
        System.out.println("parseByte(bb,6) = " + zz);

        //decode()
        String decimal = "45";
        String octal = "005";
        String hex = "0x0f";

        Byte dec=Byte.decode(decimal);
        System.out.println("decode(45) = " + dec);
        dec=Byte.decode(octal);
        System.out.println("decode(005) = " + dec);
        dec=Byte.decode(hex);
        System.out.println("decode(0x0f) = " + dec);

        System.out.println("bytevalue(x) = " + x.byteValue());
        System.out.println("shortvalue(x) = " + x.shortValue());
        System.out.println("intvalue(x) = " + x.intValue());
        System.out.println("longvalue(x) = " + x.longValue());
        System.out.println("doublevalue(x) = " + x.doubleValue());
        System.out.println("floatvalue(x) = " + x.floatValue());

        int hash=x.hashCode();
        System.out.println("hashcode(x) = " + hash);

        boolean eq=x.equals(y);
        System.out.println("x.equals(y) = " + eq);

        int e=Byte.compare(x, y);
        System.out.println("compare(x,y) = " + e);

        int f=x.compareTo(y);
        System.out.println("x.compareTo(y) = " + f);
    }
}
```

**输出：**

```java
toString(b) = 55
valueOf(b) = 55
ValueOf(bb) = 45
ValueOf(bb,6) = 29
parseByte(bb) = 45
parseByte(bb,6) = 29
decode(45) = 45
decode(005) = 5
decode(0x0f) = 15
bytevalue(x) = 55
shortvalue(x) = 55
intvalue(x) = 55
longvalue(x) = 55
doublevalue(x) = 55.0
floatvalue(x) = 55.0
hashcode(x) = 55
x.equals(y) = false
compare(x,y) = 10
x.compareTo(y) = 10
```

参考资料：[Java官方文档](https://docs.oracle.com/javase/7/docs/api/java/lang/Byte.html)

本文由**里沙布·马尔塞**供稿。如果你喜欢GeeksforGeeks并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。