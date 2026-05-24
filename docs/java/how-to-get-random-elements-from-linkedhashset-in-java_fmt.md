# 如何在 Java 中从 LinkedHashSet 获取随机元素？

> 原文: [https://www.geeksforgeeks.org/how-to-get-random-elements-from-linkedhashset-in-java/](https://www.geeksforgeeks.org/how-to-get-random-elements-from-linkedhashset-in-java/)

[`LinkedHashSet`](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 用于维护插入顺序，为了从 `LinkedHashSet` 生成随机元素，我们将使用 `Random` 类来生成介于 0 和 `LinkedHashSet` 大小之间的随机数。这个随机数将作为 `LinkedHashSet` 的索引。

## 我们可以通过三种方式得到一个随机元素:

1.  使用 `for` 循环遍历 `LinkedHashSet` 并获取随机元素。
2.  将 `LinkedHashSet` 存储在数组中，然后获取随机数索引处存在的元素。
3.  将 `LinkedHashSet` 存储在 `ArrayList` 中，然后获取随机数位置处的元素。

## 示例 1:

*   我们将生成从 0 到 `LinkedHashSet` 大小的随机数。
*   然后我们将在循环中遍历 `LinkedHashSet`，检查第 `i` 个索引是否等于随机数，然后打印该元素。

## Java

```java
// Java program to get the randome element
// from LinkedHashSet

import java.util.LinkedHashSet;
import java.util.Random;

class GFG {
    public static void main(String[] args)
    {
        LinkedHashSet<String> cset = new LinkedHashSet<>();

        // Adding elements to LinkedHashSet
        cset.add("Paneer Butter Masala");
        cset.add("Paneer Lababdar");
        cset.add("Kadai Paneer Gravy");
        cset.add("Malai Kofta Curry");
        cset.add("Palak Paneer");
        cset.add("Mughlai Shahi Paneer");
        cset.add("Restaurant Style Chilli Paneer");
        cset.add("Restaurant Style Matar Paneer");
        cset.add("Paneer Tikka Masala");
        cset.add("Paneer Makhani");
        cset.add("Achari Paneer Gravy");

        // This will generate a random number
        // between 0 and LinkedHashSet size()
        Random random = new Random();
        int randomNumber = random.nextInt(cset.size());

        // maintaining the index
        int count = 0;
        for (String s : cset) {

            // when ever our index counter variable "count"
            // will be equal to the random number it will
            // print the element at that position in the
            // LinkedHashSet and after printing we will break
            // the loop
            if (count == randomNumber) {
                System.out.println(s);
                break;
            }
            count++;
        }
    }
}
```

## 输出

```java
Paneer Butter Masala
```