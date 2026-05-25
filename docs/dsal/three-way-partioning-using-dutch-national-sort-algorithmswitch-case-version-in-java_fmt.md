# Java 中使用荷兰国家排序算法(开关盒版本)的三路分区

> 原文: [https://www.geeksforgeeks.org/three-way-partioning-using-dutch-national-sort-algorithmswitch-case-version-in-java/](https://www.geeksforgeeks.org/three-way-partioning-using-dutch-national-sort-algorithmswitch-case-version-in-java/)

给定一个数组列表 `arr` 和值 `lowVal` 和 `highVal`。任务是围绕范围对数组进行分区，以便将数组列表分为三个部分。

1.  所有小于 `lowVal` 的元素优先。
2.  接下来是范围 `lowVal` 到 `highVal` 的所有元素。
3.  所有大于 `highVal` 的元素出现在最后。

三套单个元素可以任意顺序出现。您需要返回修改后的排列数组。

**注:** 这是[荷兰国旗](https://www.geeksforgeeks.org/3-way-quicksort-dutch-national-flag/)算法的开关盒版本，用于[三路分区](https://www.geeksforgeeks.org/three-way-partitioning-of-an-array-around-a-given-range/)。

**示例:**

```
Input: arr[] = {1, 14, 5, 20, 4, 2, 54, 20, 87, 98, 3, 1, 32}  
        lowVal = 14, highVal = 20
Output: arr[] = {1, 5, 4, 2, 1, 3, 14, 20, 20, 98, 87, 32, 54}

Input: arr[] = {1, 14, 5, 20, 4, 2, 54, 20, 87, 98, 3, 1, 32}  
       lowVal = 20, highVal = 20       
Output: arr[] = {1, 14, 5, 4, 2, 1, 3, 20, 20, 98, 87, 32, 54} 
```

**算法:**

1.  我们创建三个变量，并将它们命名为 `low = 0`, `mid = 0`, `high = arr.size()`。
2.  现在，遍历给定的 `arr` 直到 `mid` 小于或等于 `high`，即 `mid <= high`。
3.  现在创建另一个变量作为 `value`，这里我们将存储在[开关情况](https://www.geeksforgeeks.org/switch-statement-in-java/)中使用的条件。
4.  如果 `arr.get(mid) < lowVal` 那么我们将把 `0` 存储在 `value` 中。
5.  如果 `arr.get(mid) >= lowVal && arr.get(mid) <= highVal` 那么将 `1` 存储在该值中。
6.  如果 `arr.get(mid) > highVal`，那么我们将 `2` 存储在该值中。
7.  现在检查开关中的 `value`。
8.  如果是 `0`，那么我们将元素从 `mid` 位置交换到 `low` 位置和 `low` 位置到 `mid` 位置，即 `Collections.swap(arr, mid, low)`。然后递增 `mid` 和 `low`，即 `mid++; low++;` 最后 `break`。
9.  如果是 `1`，那么我们**不会**从它们的位置交换元素，因为元素满足第二个条件，即如果元素在 `lowVal` 和 `highVal` 之间，它保持原样。根据语句，我们只交换只满足第一个和第三个条件的元素。然后增加 `mid`，即 `mid++;` 最后，`break`。
10. 如果是 `2` 那么我们从 `arr` 的 `mid` 到 `high` 和 `high` 到 `mid` 的位置交换元素，即 `Collections.swap(arr, mid, high)`。然后递增 `mid`，递减 `high`，即 `mid++; high--;` 最后 `break`。
11. 最后，返回数组列表 `arr`。

## Java 实现

```java
// Dutch National Sort algorithm
// using switch in Java

import java.io.*;
import java.util.*;

class GFG {

static ArrayList<Integer>
    threeWayPartition(ArrayList<Integer> arr, int lowVal,
                      int highVal)
    {
        // dutch national sort algorithm
        // using switch
        int low = 0, mid = 0, high = arr.size() - 1;

        while (mid <= high) {

            int value;

            // satisfying condition 1
            if (arr.get(mid) < lowVal)
                value = 0;

            // satisfying condition 2
            else if (arr.get(mid) >= lowVal
                     && arr.get(mid) <= highVal)
                value = 1;

            // satisfying condition 3
            else
                value = 2;

            switch (value) {

                // incase of first condition, do this
                case 0:
                    Collections.swap(arr, mid, low);
                    mid++;
                    low++;
                    break;

                // incase of second condition, do this
                case 1:
                    mid++;
                    break;

                // incase of third condition, do this
                case 2:
                    Collections.swap(arr, mid, high);
                    high--;
                    break;
            }
        }

        // return the modified arraylist
        return arr;
    }

    public static void main(String[] args)
    {

        Scanner s = new Scanner(System.in);

        // create an empty arraylist
        ArrayList<Integer> a = new ArrayList<>();

        // add elements
        a.add(1);
        a.add(14);
        a.add(5);
        a.add(20);
        a.add(4);
        a.add(2);
        a.add(54);
        a.add(20);
        a.add(87);
        a.add(98);
        a.add(3);
        a.add(1);
        a.add(32);

        // stores the modified arraylist
        ArrayList<Integer> res
            = threeWayPartition(a, 14, 20);

        // Output the arraylist
        for (int i = 0; i < 13; i++)
            System.out.print(res.get(i) + " ");
    }
}
```

**Output**

```
1 5 4 2 1 3 14 20 20 98 87 32 54 
```

*   **时间复杂度:** `O(n)`
*   **辅助空间:** `O(1)`