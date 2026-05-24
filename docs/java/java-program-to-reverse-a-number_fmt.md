# Java 程序反转一个数字

> 原文：`https://www.geeksforgeeks.org/java-program-to-reverse-a-number/`

**反转**一个数字意味着第一个位置的数字应该与最后一个数字交换，第二个数字将与第二个最后一个数字交换，以此类推，直到中间元素。

要反转一个数字，应执行以下步骤：

> *   取这个数的模 10。
> *   将反数乘以 10，并将模值加到反数中。
> *   把这个数除以 10。
> *   重复以上步骤，直到数字变为零。

我们可以使用**两种方法在 java 中反转一个数字**。

**1、使用 While 循环：**

只需应用所讨论的步骤/算法，并在数字变为零时终止循环。

*   取这个数的模 10。
*   将反数乘以 10，并将模值加到反数中。
*   把这个数除以 10。
*   重复以上步骤，直到数字变为零。

下面是上述方法的实现：

## 使用 While 循环的实现

```java
// Java program to reverse a number

import java.io.*;

class GFG {

    // Function to reverse the number
    static int reverse(int n){

        int rev = 0; // reversed number
        int rem;   // remainder

        while(n>0){

            rem = n%10;
            rev = (rev*10) + rem;
            n = n/10;
        }

        return rev;
    }

    // Driver Function
    public static void main (String[] args) {
        int n = 4526;

        System.out.print("Reversed Number is "+ reverse(n));
    }
}
```

**Output**

```java
Reversed Number is 6254
```

**2、使用递归：**

在递归中，最终的反向值将存储在全局 `rev` 变量中。遵循以下说明。

> *   如果数字变为零，则递归终止，这将是基本情况。
> *   取模，乘以 `rev*10`。
> *   将数字除以 10 并更新为 `n/10`，然后对数字调用反转函数。

下面是递归方法的 Java 实现。

## 使用递归的实现

```java
// Java program to reverse a number recursively

import java.io.*;

class GFG {

    // stores reversed number
    static int rev = 0;

    // Function to reverse the number
    static void reverse(int n){

        if(n<=0)
            return ;

        int rem = n%10;  // remainder

        rev = (rev*10) + rem;

        reverse(n/10);
    }

    // Driver Function
    public static void main (String[] args) {

        int n = 4526;

        reverse(n);

        System.out.print("Reversed Number is "+ rev);
    }
}
```

**Output**

```java
Reversed Number is 6254
```