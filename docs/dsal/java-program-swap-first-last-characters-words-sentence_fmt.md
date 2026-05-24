# Java 程序交换一个句子中单词的第一个和最后一个字符

> 原文：[https://www.geeksforgeeks.org/java-program-swap-first-last-characters-words-sentence/](https://www.geeksforgeeks.org/java-program-swap-first-last-characters-words-sentence/)

编写一个 Java 程序来交换句子中单词的第一个和最后一个字符，就像例子中提到的那样？

示例：

```
Input : geeks for geeks
Output :seekg rof seekg
```

**方法：** 如示例中所述，我们必须替换单词的第一个和最后一个字符，并保持其余字母不变。

*   首先，我们将使用 `toCharArray()` 方法来创建给定字符串的 `char` 数组。
*   现在我们使用 `for` 循环来遍历这个字符数组。
*   在 `for` 循环中，我们声明一个其值依赖于 `i` 的变量。
*   每当我们找到一个字母时，我们就增加 `i` 的值；每当我们到达一个空格时，我们就会交换空格前一个单词的首尾字符。

```
class SwapFirstLastCharacters {
    static String count(String str)
    {
        // Create an equivalent char array
        // of given string
        char[] ch = str.toCharArray();
        for (int i = 0; i < ch.length; i++) {

            // k stores index of first character
            // and i is going to store index of last
            // character.
            int k = i;
            while (i < ch.length && ch[i] != ' ')
                i++;

            // Swapping
            char temp = ch[k];
            ch[k] = ch[i - 1];
            ch[i - 1] = temp;

            // We assume that there is only one space
            // between two words.
        }
        return new String(ch);
    }
    public static void main(String[] args)
    {
        String str = "geeks for geeks";
        System.out.println(count(str));
    }
}
```

输出：

```
seekg rof seekg
```