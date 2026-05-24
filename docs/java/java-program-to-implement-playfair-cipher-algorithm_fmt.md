# 实现 Playfair 密码算法的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-implement-playfair-cipher-algorithm/](https://www.geeksforgeeks.org/java-program-to-implement-playfair-cipher-algorithm/)

密码是一种加密和解密算法。密文是应用于不同类型的算法将纯文本转换为编码文本的过程。它被称为密文。Playfair 密码是第一个实用的有向图替换密码。这个方案是查尔斯·惠斯通在 1854 年发明的，但它是以推广密码使用的 Playfair 勋爵的名字命名的。在 Playfair 密码中，与传统密码不同，我们加密一对字母(有向图)，而不是一个字母。在第二次布尔战争和第一次世界大战中，英国军队将它用于战术目的，在第二次世界大战中，澳大利亚人也将它用于同样的目的。这是因为 Playfair 使用起来相当快，不需要特殊设备。

## 算法

1.  创建一个由五行五列组成的矩阵，其中放置了所有英文字母。现在，你一定想知道有 26 个字母，而矩阵只有 25 个单元格。为了解决这个问题，字母 `I` 和 `J` 被放在一个单元格中。
2.  现在插入密钥，并将剩余的字母放入矩阵中。矩阵是通过将密钥值和剩余的字母从左到右逐行插入矩阵而形成的。
3.  将文本转换为字母对，并记住没有两个字母应该连续重复。例如，`code` 被写为 `co` 和 `de`。
4.  如果字母重复，则添加 `x` 以使配对集重复多次。例如，`helloh` 被写为 `he`、`lx`、`lx` 和 `oh`。这里，字母 `L` 连续出现两次，因此有两个集合并添加了两个 `X`。
5.  现在，如果在分成对后还剩下一个字母，就像我们为单个字母添加 `X` 一样。例如，`hello` 被写为 `he`、`lx`、`lx` 和 `oz`。
6.  使用 3 条标准规则：
    *   在矩阵中形成一个矩形。如果两个字母在同一行，则用它们右边的字母替换它们。
    *   如果两个字母在同一列，则用它们正下方的字母替换它们。
    *   如果它们不在同一行或同一列，则用同一行但另一对角线上的字母替换它们。

插图：

| c | o | d | e | u |
|---|---|---|---|---|
| f | s | t | k | g |
| l | r | m | n | p |
| e | i/j | a | h | b |
| v | w | x | y | z |

## 实施

*   生成关键方块(5×5)
*   加密明文

## 示例

### Java

```java
// Java Program for Playfair Cipher Algorithm

// Importing all utility classes
import java.util.*;

// Main class
public class Main {

    // Removing the duplicate values from the key
    static String removeDuplicate(String s)
    {
        int j, index = 0, len = s.length();
        char c[] = s.toCharArray();
        for (int i = 0; i < len; i++) {
            for (j = 0; j < i; j++) {
                if (c[i] == c[j])
                    break;
            }
            if (i == j)
                c[index++] = c[i];
        }
        s = new String((Arrays.copyOf(c, index)));
        return s;
    }

    // Method 1
    // Removing the white spaces from string 'st'
    // which was replaced by the key as space.
    static String removeWhiteSpace(char[] ch, String key)
    {
        char[] c = key.toCharArray();
        // removing character which are input by the user
        // from string st
        for (int i = 0; i < c.length; i++) {
            for (int j = 0; j < ch.length; j++) {
                if (c[i] == ch[j])
                    c[i] = ' ';
            }
        }
        key = new String(c);
        key = key.replaceAll(" ", "");
        return key;
    }

    // Method 2
    // To make the pair for encryption in plaintext.
    static String makePair(String pt)
    {
        String s = "";
        char c = 'a';
        for (int i = 0; i < pt.length(); i++) {
            if (pt.charAt(i) == ' ')
                continue;
            else {
                c = pt.charAt(i);
                s += pt.charAt(i);
            }
            if (i < pt.length() - 1)
                if (pt.charAt(i) == pt.charAt(i + 1))
                    s += "x";
        }
        // If plain text length is odd then
        // adding x to make length even.
        if (s.length() % 2 != 0)
            s += "x";
        System.out.println(s);
        return s;
    }

    // Method 3
    // To find the position of row and column in matrix
    // for encryption of the pair.
    static int[] findIJ(char a, char b, char x[][])
    {
        int[] y = new int[4];
        if (a == 'j')
            a = 'i';
        else if (b == 'j')
            b = 'i';
        for (int i = 0; i < 5; i++) {
            for (int j = 0; j < 5; j++) {
                if (x[i][j] == a) {
                    y[0] = i;
                    y[1] = j;
                }
                else if (x[i][j] == b) {
                    y[2] = i;
                    y[3] = j;
                }
            }
        }
        if (y[0] == y[2]) {
            y[1] += 1;
            y[3] += 1;
        }
        else if (y[1] == y[3]) {
            y[0] += 1;
            y[2] += 1;
        }
        for (int i = 0; i < 4; i++)
            y[i] %= 5;
        return y;
    }

    // Method 4
    // To encrypt the plaintext
    static String encrypt(String pt, char x[][])
    {
        char ch[] = pt.toCharArray();
        int a[] = new int[4];
        for (int i = 0; i < pt.length(); i += 2) {
            if (i < pt.length() - 1) {
                a = findIJ(pt.charAt(i), pt.charAt(i + 1),
                           x);
                if (a[0] == a[2]) {
                    ch[i] = x[a[0]][a[1]];
                    ch[i + 1] = x[a[0]][a[3]];
                }
                else if (a[1] == a[3]) {
                    ch[i] = x[a[0]][a[1]];
                    ch[i + 1] = x[a[2]][a[1]];
                }
                else {
                    ch[i] = x[a[0]][a[3]];
                    ch[i + 1] = x[a[2]][a[1]];
                }
            }
        }
        pt = new String(ch);
        return pt;
    }

    // Method 5
    // Main driver method
    public static void main(String[] args)
    {
        // Creating an Scanner clas object to
        // take input from user
        Scanner sc = new Scanner(System.in);
        String pt = "instruments";
        // Key input
        String key = "monarchy";
        key = removeDuplicate(key);
        char[] ch = key.toCharArray();
        // Reading string array of Letters of english
        // alphabet as Playfair to implement
        String st = "abcdefghiklmnopqrstuvwxyz";
        st = removeWhiteSpace(ch, st);
        char[] c = st.toCharArray();
        // Matrix input using above key
        char[][] x = new char[5][5];
        int indexOfSt = 0, indexOfKey = 0;
        for (int i = 0; i < 5; i++) {
            for (int j = 0; j < 5; j++) {
                if (indexOfKey < key.length())
                    x[i][j] = ch[indexOfKey++];
                else
                    x[i][j] = c[indexOfSt++];
            }
        }
        // Printing Matrix
        for (int i = 0; i < 5; i++) {
            for (int j = 0; j < 5; j++)
                System.out.print(x[i][j] + " ");
            System.out.println();
        }
        // For getting encrypted output
        // Calling makePair() method over object created in
        // main()
        pt = makePair(pt);
        // Calling makePair() method over object created in
        // main()
        pt = encrypt(pt, x);
        // Print and display in the console
        System.out.println(pt);
    }
}
```

## 输出

```java
m o n a r 
c h y b d 
e f g i k 
l p q s t 
u v w x z 
instrumentsx
gatlmzclrqxa
```