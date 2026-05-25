# 油藏取样

> 原文: [https://www.geeksforgeeks.org/reservoir-sampling/](https://www.geeksforgeeks.org/reservoir-sampling/)

[储层采样](http://en.wikipedia.org/wiki/Reservoir_sampling)是一系列随机算法，用于从 *n* 项列表中随机选择 *k* 个样本，其中 *n* 是一个非常大或未知的数字。通常 *n* 足够大，以至于列表不适合主内存。例如，谷歌和脸书的搜索查询列表。

所以给我们一个大的数字数组（或流）（为了简化），我们需要写一个高效的函数来随机选择 *k* 个数字，其中 `1 <= k <= n`。让输入数组成为 `stream[]`。

一个**简单的解决方案**是创建一个最大尺寸 *k* 的数组 `reservoir[]`。逐一从 `stream[0..n-1]` 中随机选择一个项目。如果选择的项目不是先前选择的，则将其放入 `reservoir[]`。要检查一个项目之前是否被选中，我们需要在 `reservoir[]` 中搜索该项目。这个算法的时间复杂度将是 `O(k^2)`。如果 *k* 很大，这可能会很昂贵。此外，如果输入是流的形式，这也是无效的。

它**可以在 `O(n)` 时间**内解决。该解决方案也非常适合流形式的输入。想法和[这个](https://www.geeksforgeeks.org/shuffle-a-given-array/)帖子差不多。以下是步骤。

**1)** 创建数组 `reservoir[0..k-1]` 并将 `stream[]` 的第一个 *k* 项复制到其中。
**2)** 现在逐一考虑从 *(k+1)* 项到 *n* 项的所有项目。
… **a)** 生成一个从 0 到 *i* 的随机数，其中 *i* 是 `stream[]` 中当前项目的索引。让生成的随机数为 *j*。
……**b)** 如果 *j* 在 0 到 *k-1* 的范围内，用 `stream[i]` 替换 `reservoir[j]`。

下面是上述算法的实现。

## C++

```cpp
// An efficient program to randomly select
// k items from a stream of items
#include <bits/stdc++.h>
#include <time.h>
using namespace std;

// A utility function to print an array
void printArray(int stream[], int n)
{
    for (int i = 0; i < n; i++)
        cout << stream[i] << " ";
    cout << endl;
}

// A function to randomly select
// k items from stream[0..n-1].
void selectKItems(int stream[], int n, int k)
{
    int i; // index for elements in stream[]

    // reservoir[] is the output array. Initialize
    // it with first k elements from stream[]
    int reservoir[k];
    for (i = 0; i < k; i++)
        reservoir[i] = stream[i];

    // Use a different seed value so that we don't get
    // same result each time we run this program
    srand(time(NULL));

    // Iterate from the (k+1)th element to nth element
    for (; i < n; i++)
    {
        // Pick a random index from 0 to i.
        int j = rand() % (i + 1);

        // If the randomly picked index is smaller than k,
        // then replace the element present at the index
        // with new element from stream
        if (j < k)
        reservoir[j] = stream[i];
    }

    cout << "Following are k randomly selected items \n";
    printArray(reservoir, k);
}

// Driver Code
int main()
{
    int stream[] = {1, 2, 3, 4, 5, 6,
                    7, 8, 9, 10, 11, 12};
    int n = sizeof(stream)/sizeof(stream[0]);
    int k = 5;
    selectKItems(stream, n, k);
    return 0;
}

// This is code is contributed by rathbhupendra
```

## C

```c
// An efficient program to randomly select k items from a stream of items

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// A utility function to print an array
void printArray(int stream[], int n)
{
    for (int i = 0; i < n; i++)
        printf("%d ", stream[i]);
    printf("\n");
}

// A function to randomly select k items from stream[0..n-1].
void selectKItems(int stream[], int n, int k)
{
    int i;  // index for elements in stream[]

    // reservoir[] is the output array. Initialize it with
    // first k elements from stream[]
    int reservoir[k];
    for (i = 0; i < k; i++)
        reservoir[i] = stream[i];

    // Use a different seed value so that we don't get
    // same result each time we run this program
    srand(time(NULL));

    // Iterate from the (k+1)th element to nth element
    for (; i < n; i++)
    {
        // Pick a random index from 0 to i.
        int j = rand() % (i+1);

        // If the randomly  picked index is smaller than k, then replace
        // the element present at the index with new element from stream
        if (j < k)
          reservoir[j] = stream[i];
    }

    printf("Following are k randomly selected items \n");
    printArray(reservoir, k);
}

// Driver program to test above function.
int main()
{
    int stream[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};
    int n = sizeof(stream)/sizeof(stream[0]);
    int k = 5;
    selectKItems(stream, n, k);
    return 0;
}
```

## Java

```java
// An efficient Java program to randomly
// select k items from a stream of items
import java.util.Arrays;
import java.util.Random;
public class ReservoirSampling {

    // A function to randomly select k items from
    // stream[0..n-1].
    static void selectKItems(int stream[], int n, int k)
    {
        int i; // index for elements in stream[]

        // reservoir[] is the output array. Initialize it
        // with first k elements from stream[]
        int reservoir[] = new int[k];
        for (i = 0; i < k; i++)
            reservoir[i] = stream[i];

        Random r = new Random();

        // Iterate from the (k+1)th element to nth element
        for (; i < n; i++) {
            // Pick a random index from 0 to i.
            int j = r.nextInt(i + 1);

            // If the randomly  picked index is smaller than
            // k, then replace the element present at the
            // index with new element from stream
            if (j < k)
                reservoir[j] = stream[i];
        }

        System.out.println(
            "Following are k randomly selected items");
        System.out.println(Arrays.toString(reservoir));
    }

    // Driver Program to test above method
    public static void main(String[] args)
    {
        int stream[]
            = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12 };
        int n = stream.length;
        int k = 5;
        selectKItems(stream, n, k);
    }
}
// This code is contributed by Sumit Ghosh
```

## Python 3

```python
# An efficient Python3 program
# to randomly select k items
# from a stream of items
import random
# A utility function
# to print an array
def printArray(stream,n):
    for i in range(n):
        print(stream[i],end=" ");
    print();

# A function to randomly select
# k items from stream[0..n-1].
def selectKItems(stream, n, k):
        i=0;
        # index for elements
        # in stream[]

        # reservoir[] is the output
        # array. Initialize it with
        # first k elements from stream[]
        reservoir = [0]*k;
        for i in range(k):
            reservoir[i] = stream[i];

        # Iterate from the (k+1)th
        # element to nth element
        while(i < n):
            # Pick a random index
            # from 0 to i.
            j = random.randrange(i+1);

            # If the randomly picked
            # index is smaller than k,
            # then replace the element
            # present at the index
            # with new element from stream
            if(j < k):
                reservoir[j] = stream[i];
            i+=1;

        print("Following are k randomly selected items");
        printArray(reservoir, k);

# Driver Code

if __name__ == "__main__":
    stream = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12];
    n = len(stream);
    k = 5;
    selectKItems(stream, n, k);

# This code is contributed by mits
```

## C\#

```csharp
// An efficient C# program to randomly
// select k items from a stream of items
using System;
using System.Collections;

public class ReservoirSampling
{
    // A function to randomly select k
    // items from stream[0..n-1].
    static void selectKItems(int []stream,
                            int n, int k)
    {
        // index for elements in stream[]
        int i;

        // reservoir[] is the output array.
        // Initialize it with first k
        //  elements from stream[]
        int[] reservoir = new int[k];
        for (i = 0; i < k; i++)
            reservoir[i] = stream[i];

        Random r = new Random();

        // Iterate from the (k+1)th
        // element to nth element
        for (; i < n; i++)
        {
            // Pick a random index from 0 to i.
            int j = r.Next(i + 1);

            // If the randomly picked index
            // is smaller than k, then replace
            // the element present at the index
            // with new element from stream
            if(j < k)
                reservoir[j] = stream[i];        
        }

        Console.WriteLine("Following are k " +
                    "randomly selected items");
        for (i = 0; i < k; i++)
        Console.Write(reservoir[i]+" ");
    }

    //Driver code
    static void Main()
    {
        int []stream = {1, 2, 3, 4, 5, 6, 7,
                        8, 9, 10, 11, 12};
        int n = stream.Length;
        int k = 5;
        selectKItems(stream, n, k);
    }
}

// This code is contributed by mits
```

## PHP

```php
<?php
// An efficient PHP program
// to randomly select k items
// from a stream of items

// A utility function
// to print an array
function printArray($stream,$n)
{
    for ($i = 0; $i < $n; $i++)
        echo $stream[$i]." ";
    echo "\n";
}

// A function to randomly select
// k items from stream[0..n-1].
function selectKItems($stream, $n, $k)
    {
        $i; // index for elements
            // in stream[]

        // reservoir[] is the output
        // array. Initialize it with
        // first k elements from stream[]
        $reservoir = array_fill(0, $k, 0);
        for ($i = 0; $i < $k; $i++)
            $reservoir[$i] = $stream[$i];

        // Iterate from the (k+1)th
        // element to nth element
        for (; $i < $n; $i++)
        {
            // Pick a random index
            // from 0 to i.
            $j = rand(0,$i + 1);

            // If the randomly picked
            // index is smaller than k,
            // then replace the element
            // present at the index
            // with new element from stream
            if($j < $k)
                $reservoir[$j] = $stream[$i];    
        }

        echo "Following are k randomly ".
                  "selected items\n";
        printArray($reservoir, $k);
    }

// Driver Code
$stream = array(1, 2, 3, 4, 5, 6, 7,
                8, 9, 10, 11, 12);
$n = count($stream);
$k = 5;
selectKItems($stream, $n, $k);

// This code is contributed by mits
?>
```

## JavaScript

```javascript
// An efficient program to randomly select
// k items from a stream of items

// A utility function to print an array
function printArray(stream, n)
{
    for(let i = 0; i < n; i++)
        document.write(stream[i] + " ");

    document.write('\n');
}

// A function to randomly select
// k items from stream[0..n-1].
function selectKItems(stream, n, k)
{

    // Index for elements in stream[]
    let i;

    // reservoir[] is the output array. Initialize
    // it with first k elements from stream[]
    let reservoir = [];
    for(i = 0; i < k; i++)
        reservoir[i] = stream[i];

    // Use a different seed value so that
    // we don't get same result each time
    // we run this program

    // Iterate from the (k+1)th element
    // to nth element
    for(; i < n; i++)
    {
        // Pick a random index from 0 to i.
        let j = (Math.floor(Math.random() *
                 100000000) % (i + 1));

        // If the randomly picked index is
        // smaller than k, then replace the
        // element present at the index
        // with new element from stream
        if (j < k)
            reservoir[j] = stream[i];
    }

    document.write("Following are k randomly " +
                   "selected items \n");
    printArray(reservoir, k);
}

// Driver Code
let stream = [ 1, 2, 3, 4, 5, 6,
               7, 8, 9, 10, 11, 12 ];
let n = stream.length;
let k = 5;

selectKItems(stream, n, k);

// This code is contributed by rohan07
```

**输出:**

```
Following are k randomly selected items
6 2 11 8 12
Note: Output will differ every time as it selects and prints random elements
```

**时间复杂度:** `O(n)`

**辅助空间:** `O(k)`

**这是如何工作的？**
为了证明这个解决方案是完美的，我们必须证明`stream[i]`中 `0 <= i < n` 的任何一个项目在最终`reservoir[]`中的概率是 `k/n` 。让我们将证明分为两种情况，首先 `k` 项被区别对待。

**情况 1:对于最后一个** `n-k` **流项目，即对于** `stream[i]`**其中**`k <= i < n`**对于每一个这样的流项目`stream[i]`，我们从 0 到`i`随机选取一个索引`j`。如果`j`在`0`到`k-1`之间，`stream[i]`将被选中进入水库。`stream[i]`成为最终水库中一个项目的概率=为`stream[i]`选取的索引`j`在`0`到`k-1`之间的概率= `k/(i+1)`。`stream[i]`在后续迭代中不被替换的概率= `k/(i+1)` * `(i+1)/(i+2)` * `(i+2)/(i+3)` * ... * `(n-1)/n` = `k/n`。因此，对于`i >= k`，`stream[i]`最终留在水库中的概率是`k/n`。特别地，对于最后一个项目`stream[n-1]`，它被选中的概率是`k/n`。**

**情况 2:对于第一个** `k` **流项目，即对于** `stream[i]`**其中**`0 <= i < k`**
第一个 `k` 项目最初被复制到`reservoir[]`并可能在后面的`stream`的迭代中被移除。`stream[0..k-1]`中的一个项目最终留在数组中的概率=当物品`stream[k], stream[k+1], ..., stream[n-1]`被考虑时，该项目未被替换的概率。对于`stream[0]`，它不被`stream[k]`替换的概率是`k/(k+1)`。它不被`stream[k+1]`替换的概率是`(k+1)/(k+2)`，以此类推。因此，`stream[0]`最终留在水库中的概率是`k/(k+1)` * `(k+1)/(k+2)` * ... * `(n-1)/n` = `k/n`。对于`stream[1]`到`stream[k-1]`，论证类似。

**参考文献:**
[http://en.wikipedia.org/wiki/Reservoir_sampling](http://en.wikipedia.org/wiki/Reservoir_sampling)

发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息。