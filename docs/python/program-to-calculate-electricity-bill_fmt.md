# 电费计算程序

> 原文: [https://www.geeksforgeeks.org/program-to-calculate-electricity-bill/](https://www.geeksforgeeks.org/program-to-calculate-electricity-bill/)

给定一个整数 `U` 表示用电量的千瓦时单位，任务是借助以下费用计算电费:

*   1 到 100 单位 – Rs. 10/单位
*   100 到 200 单位 – Rs. 15/单位
*   200 到 300 单位 – Rs. 20/单位
*   超过 300 单位 – Rs. 25/单位

**例:**

> **输入:** `U` = 250
> **输出:** 3500
> **说明:**
> 前 100 单位收费 – 10 * 100 = 1000
> 100 至 200 单位收费 – 15 * 100 = 1500
> 200 至 250 单位收费 – 20 * 50 = 1000
> 总电费 = 1000 + 1500 + 1000 = 3500

**做法:** 思路是识别其所属的收费条，然后根据上述收费计算账单。以下是步骤说明:

*   检查消耗的单位是否小于等于 100，如果是，则总电费为:
    `总电费 = (单位数 * 10)`
*   否则，如果检查消耗的单位小于等于 200，如果是，则总电费将为:
    `总电费 = (100*10) + (单位数-100) * 15`
*   否则，如果检查消耗的单位小于等于 300，如果是，则总电费将为:
    `总电费 = (100*10) + (100*15) + (单位数-200) * 20`
*   否则，如果检查消耗的单位大于 300，如果是，则总电费为:
    `总电费 = (100*10) + (100*15) + (100*20) + (单位数-300) * 25`

以下是上述方法的实现:

## C++

```cpp
// C++ implementation to calculate the
// electricity bill
#include<bits/stdc++.h>
using namespace std;

// Function to calculate the
// electricity bill
int calculateBill(int units)
{

    // Condition to find the charges
    // bar in which the units consumed
    // is fall
    if (units <= 100)
    {
        return units * 10;
    }
    else if (units <= 200)
    {
        return (100 * 10) +
               (units - 100) * 15;
    }
    else if (units <= 300)
    {
        return (100 * 10) +
               (100 * 15) +
               (units - 200) * 20;
    }
    else if (units > 300)
    {
        return (100 * 10) +
               (100 * 15) +
               (100 * 20) +
               (units - 300) * 25;
    }
    return 0;
}

// Driver Code
int main()
{
    int units = 250;
    cout << calculateBill(units);
}

// This code is contributed by spp____
```

## Java

```java
// Java implementation to calculate the
// electricity bill

import java.util.*;

class ComputeElectricityBill {

    // Function to calculate the
    // electricity bill
    public static int calculateBill(int units)
    {

        // Condition to find the charges
        // bar in which the units consumed
        // is fall
        if (units <= 100) {
            return units * 10;
        }
        else if (units <= 200) {
            return (100 * 10)
                + (units - 100)
                      * 15;
        }
        else if (units <= 300) {
            return (100 * 10)
                + (100 * 15)
                + (units - 200)
                      * 20;
        }
        else if (units > 300) {
            return (100 * 10)
                + (100 * 15)
                + (100 * 20)
                + (units - 300)
                      * 25;
        }
        return 0;
    }

    // Driver Code
    public static void main(String args[])
    {
        int units = 250;

        System.out.println(
            calculateBill(units));
    }
}
```

## Python 3

```python
# Python3 implementation to calculate the
# electricity bill

# Function to calculate the
# electricity bill
def calculateBill(units):

    # Condition to find the charges
    # bar in which the units consumed
    # is fall
    if (units <= 100):

        return units * 10;

    elif (units <= 200):

        return ((100 * 10) +
                (units - 100) * 15);

    elif (units <= 300):

        return ((100 * 10) +
                (100 * 15) +
                (units - 200) * 20);

    elif (units > 300):

        return ((100 * 10) +
                (100 * 15) +
                (100 * 20) +
                (units - 300) * 25);

    return 0;

# Driver Code
units = 250;
print(calculateBill(units));

# This code is contributed by Code_Mech
```

## C#

```csharp
// C# implementation to calculate the
// electricity bill
using System;

class ComputeElectricityBill{

// Function to calculate the
// electricity bill
public static int calculateBill(int units)
{

    // Condition to find the charges
    // bar in which the units consumed
    // is fall
    if (units <= 100)
    {
        return units * 10;
    }
    else if (units <= 200)
    {
        return (100 * 10) +
               (units - 100) * 15;
    }
    else if (units <= 300)
    {
        return (100 * 10) +
               (100 * 15) +
               (units - 200) * 20;
    }
    else if (units > 300)
    {
        return (100 * 10) +
               (100 * 15) +
               (100 * 20) +
               (units - 300) * 25;
    }
    return 0;
}

// Driver Code
public static void Main(String []args)
{
    int units = 250;

    Console.WriteLine(calculateBill(units));
}
}

// This code is contributed by spp____
```

## JavaScript

```javascript
<script>

// Javascript implementation to calculate the
// electricity bill

// Function to calculate the
// electricity bill
function calculateBill(units)
{

    // Condition to find the charges
    // bar in which the units consumed
    // is fall
    if (units <= 100)
    {
        return units * 10;
    }
    else if (units <= 200)
    {
        return (100 * 10)
            + (units - 100)
                  * 15;
    }
    else if (units <= 300)
    {
        return (100 * 10)
            + (100 * 15)
            + (units - 200)
                  * 20;
    }
    else if (units > 300)
    {
        return (100 * 10)
            + (100 * 15)
            + (100 * 20)
            + (units - 300)
                  * 25;
    }
    return 0;
}

// Driver Code
var units = 250;

document.write(calculateBill(units));

// This code is contributed by Khushboogoyal499

</script>
```

**输出:** 3500

时间复杂度: O(1)

辅助空间: O(1)