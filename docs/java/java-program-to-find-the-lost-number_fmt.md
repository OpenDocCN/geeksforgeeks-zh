# 寻找丢失号码的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-find-the-lost-number/](https://www.geeksforgeeks.org/java-program-to-find-the-lost-number/)

鲍勃是个小孩，刚学会数数。他坐在家里，开始玩他的许多玩具。他左手拿着一些`n`玩具号码，右手数着那些`n`玩具。突然他妈妈打电话给他，他把所有的号码混在一起就走了。当他回来时，他意识到他忘记了他正在数的数字。给定所有的玩具号码，帮助他找到`n`的值，如果在数组中存在的话，否则打印`-1`。

### 示例

> **输入**：5 7 4 3 2 6
>
> **输出**：5
>
> **说明**：有6个玩具号码，其中一个是长度，所以我们打印5。
>
> **输入**：10 14 11 15
>
> **输出**：-1
>
> **解释**：有4个玩具号码，但我们没有3作为数组中的值，因此我们打印-1。

### 接近

解决办法很简单。我们可以只取一个字符串中的输入，计算空格数，这将是数组的实际长度。

### 算法

1.  将输入作为一个字符串。
2.  计算字符串中的空格数。
3.  如果空格数等于数组中的任何一个元素，则打印该数字；否则，打印`-1`。
4.  为了找出元素是否存在，我们使用`String.indexOf()`方法。

#### 它是如何工作的？

*   当我们把输入当作一个字符串时，字符串中的元素数等于空格数+1。
*   元素的实际数量等于字符串中的元素数量-1。

> 所需答案 = 空格数 + 1 - 1 = 空格数

### 实现

## 实现代码

```java
// Java program to find the lost count

import java.util.*;
public class GFG {

    // find lost count
    public static void findLostCount(String s)
    {
        // counting the number of elements using the split
        // function -1
        int count = s.split(" ").length - 1;

        // if the value count is present then print count
        // else print -1
        if (s.indexOf(Integer.toString(count)) != -1)
            System.out.println("Number of elements "
                               + count);
        else
            System.out.println(-1);
    }

    public static void main(String args[])
    {
        Scanner in = new Scanner(System.in);

        // Taking input as string
        String s = "5 7 4 3 2 6";

        findLostCount(s);
    }
}
```

### 输出

```java
Number of elements 5
```