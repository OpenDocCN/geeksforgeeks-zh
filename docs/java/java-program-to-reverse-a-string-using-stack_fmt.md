# 使用堆栈反转字符串的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-reverse-a-string-using-stack/](https://www.geeksforgeeks.org/java-program-to-reverse-a-string-using-stack/)

[`栈`](https://www.geeksforgeeks.org/stack-class-in-java/)是遵循[`后进先出`](https://www.geeksforgeeks.org/lifo-last-in-first-out-approach-in-programming/)原则的线性数据结构，即最后插入的元素是最先出来的元素。

**方法：**

1.  将字符逐个推入`Stack<Character>`数据类型。
2.  逐个从栈中弹出字符，直到栈变为空。
3.  将弹出的元素添加到`char`数组。
4.  将`char`数组转换为`String`。
5.  返回反转后的字符串。

下面是上述方法的实现。

## Java 实现

```java
import java.util.Stack;

public class GFG {
    public static void main(String[] args)
    {
        String originalString = "GeeksForGeeks";
        String reversedString = reverse(originalString);
        System.out.println(originalString
                           + " <- Reverse -> "
                           + reversedString);

        originalString = "Hello World";
        reversedString = reverse(originalString);
        System.out.println(originalString
                           + " <- Reverse -> "
                           + reversedString);
    }

    public static String reverse(String inputString)
    {
        Stack<Character> stack = new Stack<>();

        char[] charArray = inputString.toCharArray();

        for (char c : charArray) {
            stack.push(c);
        }

        char[] reversedCharArray = new char[charArray.length];
        int i = 0;

        while (!stack.isEmpty()) {
            reversedCharArray[i++] = stack.pop();
        }

        return new String(reversedCharArray);
    }
}
```

#### 输出：

```
GeeksForGeeks <- Reverse -> skeeGroFskeeG
Hello World <- Reverse -> dlroW olleH
```

**时间复杂度：** `O(n)`，其中 `n` 是字符串中的字符数。

**辅助空间：** `O(n)`，用于栈空间。