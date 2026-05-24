# 用 Java 的逆波兰符号计算算术表达式的值

> 原文：[https://www.geeksforgeeks.org/evaluate-the-value-of-an-arithmetic-expression-in-reverse-polish-notation-in-java/](https://www.geeksforgeeks.org/evaluate-the-value-of-an-arithmetic-expression-in-reverse-polish-notation-in-java/)

**逆波兰符号**是后缀符号，用数学概念来表示操作数后面的运算符。让我们用一个问题陈述来实现 RPN。

## 问题陈述

任务是使用像 `+`、`-`、`*`、`/` 这样的有效运算符找到数组中存在的算术表达式的值。每个操作数可以是整数或其他表达式。

**注意：**

1.  两个整数之间的除法结果应向零截断。
2.  给定的 RPN 表达式总是有效的。这意味着表达式总是计算的结果，并且不会出现除以零的情况。

图示为 RPN 的外行操作：

```java
Input: ["2", "1", "+", "3", "*"]
Output: 9
Explanation: ((2 + 1) * 3) = 9

Input: ["4", "13", "5", "/", "+"]
Output: 6
Explanation: (4 + (13 / 5)) = 6

Input: ["10", "6", "9", "3", "+", "-11", "*", "/", "*", "17", "+", "5", "+"]
Output: 22
Explanation: 
  ((10 * (6 / ((9 + 3) * -11))) + 17) + 5
= ((10 * (6 / (12 * -11))) + 17) + 5
= ((10 * (6 / -132)) + 17) + 5
= ((10 * 0) + 17) + 5
= (0 + 17) + 5
= 17 + 5
= 22
```

## 进场

解决这个问题的基本方法是使用**堆栈**。

*   遍历数组中的所有元素，如果元素不匹配特殊字符（`"+"`、`"-"`、`"*"`、`"/"`），则将元素压入堆栈。
*   然后，每当找到一个特殊字符时，从堆栈中弹出前两个元素并执行操作，然后将结果元素再次压入堆栈。
*   对数组中的所有元素重复上述两个过程。
*   最后，从堆栈中弹出元素并打印结果。

## 实现

### Java

```java
// Java Program to find the
// solution of the arithmetic
// using the stack
import java.io.*;
import java.util.*;

class solution {
    public int stacky(String[] tokens)
    {

// Initialize the stack and the variable
        Stack<String> stack = new Stack<String>();
        int x, y;
        String result = "";
        int get = 0;
        String choice;
        int value = 0;
        String p = "";

// Iterating to the each character
        // in the array of the string
        for (int i = 0; i < tokens.length; i++) {

// If the character is not the special character
            // ('+', '-' ,'*' , '/')
            // then push the character to the stack
            if (tokens[i] != "+" && tokens[i] != "-"
                && tokens[i] != "*" && tokens[i] != "/") {
                stack.push(tokens[i]);
                continue;
            }
            else {
                // else if the character is the special
                // character then use the switch method to
                // perform the action
                choice = tokens[i];
            }

// Switch-Case
            switch (choice) {
            case "+":

// Performing the "+" operation by poping
                // put the first two character
                // and then again store back to the stack

                x = Integer.parseInt(stack.pop());
                y = Integer.parseInt(stack.pop());
                value = x + y;
                result = p + value;
                stack.push(result);
                break;

            case "-":

// Performing the "-" operation by poping
                // put the first two character
                // and then again store back to the stack
                x = Integer.parseInt(stack.pop());
                y = Integer.parseInt(stack.pop());
                value = y - x;
                result = p + value;
                stack.push(result);
                break;

            case "*":

// Performing the "*" operation
                // by poping put the first two character
                // and then again store back to the stack

                x = Integer.parseInt(stack.pop());
                y = Integer.parseInt(stack.pop());
                value = x * y;
                result = p + value;
                stack.push(result);
                break;

            case "/":

// Performing the "/" operation by poping
                // put the first two character
                // and then again store back to the stack

                x = Integer.parseInt(stack.pop());
                y = Integer.parseInt(stack.pop());
                value = y / x;
                result = p + value;
                stack.push(result);
                break;

            default:
                continue;
            }
        }

// Method to convert the String to integer
        return Integer.parseInt(stack.pop());
    }
}

class GFG {

    public static void main(String[] args)
    {
        // String Input
        String[] s
            = { "10", "6", "9",  "3", "+", "-11", "*",
                "/",  "*", "17", "+", "5", "+" };

        solution str = new solution();
        int result = str.stacky(s);
        System.out.println(result);
    }
}
```

## 输出

```java

```

**时间复杂度：** `O(n)`