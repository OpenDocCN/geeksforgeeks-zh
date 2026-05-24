# 使用堆栈反转字符串的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-reverse-a-string-using-stack/](https://www.geeksforgeeks.org/java-program-to-reverse-a-string-using-stack/)

[栈](https://www.geeksforgeeks.org/stack-class-in-java/)是遵循[后进先出](https://www.geeksforgeeks.org/lifo-last-in-first-out-approach-in-programming/)原则的线性数据结构，即最后插入的元素是最先出来的元素。

**方法：**

1.  将字符逐个推入`character stack`数据类型中。
2.  从栈中逐个弹出字符，直到栈变为空。
3.  将弹出的元素添加到`character array`中。
4.  将`character array`转换为字符串。
5.  返回反转后的字符串。

下面是上述方法的实现。

## Java

```java
// Java程序使用栈反转字符串
import java.util.*;

class GFG {

    // 使用栈反转字符串的函数
    public static String reverse(String inputString)
    {
        // 创建一个空栈来存储字符
        Stack<Character> stack = new Stack<>();

        // 将字符串的字符推入栈中
        char ch[] = inputString.toCharArray();
        for (int i = 0; i < ch.length; i++) {
            stack.push(ch[i]);
        }

        // 反转字符串
        String reverse = "";
        // 直到栈为空，逐个弹出字符
        while (!stack.isEmpty()) {
            reverse += stack.pop();
        }
        // 返回反转后的字符串
        return reverse;
    }

    // 主函数
    public static void main(String[] args)
    {
        String s = "GeeksForGeeks";
        System.out.println(s + " <- Reverse -> " + reverse(s));

        s = "Hello World";
        System.out.println(s + " <- Reverse -> " + reverse(s));
    }
}
```

### 输出：

```
GeeksForGeeks <- Reverse -> skeeGroFskeeG
Hello World <- Reverse -> dlroW olleH
```

**时间复杂度：**`O(n)`，其中`n`是栈中的字符数。

**辅助空间：**`O(n)`。