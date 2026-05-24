# 如何在 C++ 中高效使用无序 _ map

> 原文:[https://www . geesforgeks . org/如何使用-无序 _ 地图-高效 in-c/](https://www.geeksforgeeks.org/how-to-use-unordered_map-efficiently-in-c/)

**先决条件** : [无序 _ 集合，](https://www.geeksforgeeks.org/unordered_set-in-cpp-stl/)T4】无序 _ 地图

C++ 提供 [std::无序 _ 集合](https://www.geeksforgeeks.org/unordered_set-in-cpp-stl/)和 [std::无序 _ 映射](https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/)分别作为[哈希](https://www.geeksforgeeks.org/hashing-data-structure/)集合和哈希映射。它们在恒定的平均时间内执行插入/删除/访问。

1.  然而，最坏情况的复杂度是 O(n <sup>2</sup> )。
2.  原因是无序映射存储的键值对是通过对输入值取素数的模，然后将其存储在哈希表中。
3.  当输入数据很大，输入值是这个质数的倍数时，会发生大量的碰撞，并可能导致 O 的复杂性(n <sup>2</sup> )。
4.  取决于编译器，质数可能是 107897 或 126271。

**例 1:** 如果我们插入以上两个素数的倍数，计算执行时间。其中一个质数比另一个质数花费的时间长得多。

## C++

```cpp
// C++ program to determine worst case
// time complexity of an unordered_map

#include <bits/stdc++.h>
using namespace std;
using namespace std::chrono;
int N = 55000;
int prime1 = 107897;
int prime2 = 126271;

void insert(int prime)
{

    // Starting the clock
    auto start
        = high_resolution_clock::now();

    unordered_map<int, int> umap;

    // Inserting multiples of prime
    // number as key in the map
    for (int i = 1; i <= N; i++)
        umap[i * prime] = i;

    // Stopping the clock
    auto stop
        = high_resolution_clock::now();

    // Typecasting the time to
    // milliseconds
    auto duration
        = duration_cast<milliseconds>(
            stop - start);

    // Time in seconds
    cout << "for " << prime << " : "
         << duration.count() / 1000.0
         << " seconds "
         << endl;
}

// Driver code
int main()
{
    // Function call for prime 1
    insert(prime1);

    // Function call for prime 2
    insert(prime2);
}
```

**Output:** 

```cpp
for 107897 : 2.261 seconds 
for 126271 : 0.024 seconds
```

显然，对于其中一个素数，时间复杂度为 O(n <sup>2</sup> )。

无序映射工作的标准内置[散列函数](https://www.geeksforgeeks.org/what-are-hash-functions-and-how-to-choose-a-good-hash-function/)与此类似:

## C++

```cpp
struct hash {
    size_t operator()(uint64_t x)
        const { return x; }
};
```

上述函数会产生大量的冲突。在 **HashMap** 中插入的密钥分布不均匀，在插入大量的素数倍数后，进一步的插入会导致 hash 函数将所有先前的密钥重新分配到新的槽中，从而使其变慢。所以，我们必须随机化散列函数。
我们的想法是使用一种方法，使我们的散列表中的键均匀分布。这将防止碰撞发生。为此，我们使用斐波那契数。与[斐波那契数列](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/)(**φ= 1.618**)相关的[黄金分割比](https://www.geeksforgeeks.org/check-whether-two-numbers-are-in-golden-ratio/)具有可以均匀细分任意范围而不循环回到起始位置的特性。

我们可以创建自己的简单散列函数。下面是散列函数:

## C++

```cpp
struct modified_hash {
    static uint64_t splitmix64(uint64_t x)
    {

        // 0x9e3779b97f4a7c15,
        // 0xbf58476d1ce4e5b9,
        // 0x94d049bb133111eb are numbers
        // that are obtained by dividing
        // high powers of two with Phi
        // (1.6180..) In this way the
        // value of x is modified
        // to evenly distribute
        // keys in hash table
        x += 0x9e3779b97f4a7c15;
        x = (x ^ (x >> 30)) * 0xbf58476d1ce4e5b9;
        x = (x ^ (x >> 27)) * 0x94d049bb133111eb;
        return x ^ (x >> 31);
    }

    int operator()(uint64_t x) const
    {
        static const uint64_t random
            = steady_clock::now()
                  .time_since_epoch()
                  .count();

        // The above line generates a
        // random number using
        // high precision clock
        return splitmix64(

            // It returns final hash value
            x + random);
    }
};
```

基本上，上述散列函数生成随机散列值来存储密钥。要了解更多信息，请参考本文[斐波那契哈希。](https://probablydance.com/2018/06/16/fibonacci-hashing-the-optimization-that-the-world-forgot-or-a-better-alternative-to-integer-modulo/)

**示例 2:** 使用上面的哈希函数，程序运行非常快。

## C++

```cpp
// C++ program to determine worst case
// time complexity of an unordered_map
// using modified hash function

#include <bits/stdc++.h>
using namespace std;
using namespace std::chrono;

struct modified_hash {

    static uint64_t splitmix64(uint64_t x)
    {
        x += 0x9e3779b97f4a7c15;
        x = (x ^ (x >> 30))
            * 0xbf58476d1ce4e5b9;
        x = (x ^ (x >> 27))
            * 0x94d049bb133111eb;
        return x ^ (x >> 31);
    }

    int operator()(uint64_t x) const
    {
        static const uint64_t random
            = steady_clock::now()
                  .time_since_epoch()
                  .count();
        return splitmix64(x + random);
    }
};

int N = 55000;
int prime1 = 107897;
int prime2 = 126271;

// Function to insert in the hashMap
void insert(int prime)
{
    auto start = high_resolution_clock::now();

    // Third argument in initialisation
    // of unordered_map ensures that
    // the map uses the hash function
    unordered_map<int, int, modified_hash>
        umap;

    // Inserting multiples of prime
    // number as key in the map
    for (int i = 1; i <= N; i++)
        umap[i * prime] = i;

    auto stop
        = high_resolution_clock::now();

    auto duration
        = duration_cast<milliseconds>(
            stop - start);

    cout << "for " << prime << " : "
         << duration.count() / 1000.0
         << " seconds "
         << endl;
}

// Driver Code
int main()
{
    // Function call for prime 1
    insert(prime1);

    // Function call for prime 2
    insert(prime2);
}
```

**Output:** 

```cpp
for 107897 : 0.025 seconds 
for 126271 : 0.024 seconds
```

**手前预留空间**

默认情况下，无序映射的容量为 16，并为此创建一个哈希表。但是每次当达到阈值时，无序映射的容量就会翻倍，并且所有的值都会根据新的哈希表重新散列。

因此，我们可以使用根据我们的输入大小预先预留容量。reserve()方法。

```cpp
umap.reserve(1024);
```

根据输入大小，1024 可以被任何 int 值替换。这防止了重新散列和动态分配，这使得程序更加有效。

**设置最大负荷系数**

无序地图的 max_load_factor 决定了碰撞的概率。默认值设置为 1。

通过将其设置为较低的值，如 0.25，可以在很大程度上降低碰撞的概率。

```cpp
umap.max_load_factor(0.25);
```

**例:**使用以上两种方法可以使 umap 更快:

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;
using namespace std::chrono;
int N = 55000;
int prime1 = 107897;
int prime2 = 126271;

void insert(int prime)
{

    // Starting the clock
    auto start
        = high_resolution_clock::now();

    unordered_map<int, int> umap;
    umap.reserve(1024); // RESERVING SPACE BEFOREHAND
    umap.max_load_factor(0.25); // DECREASING MAX_LOAD_FACTOR
    // Inserting multiples of prime
    // number as key in the map
    for (int i = 1; i <= N; i++)
        umap[i * prime] = i;

    // Stopping the clock
    auto stop
        = high_resolution_clock::now();

    // Typecasting the time to
    // milliseconds
    auto duration
        = duration_cast<milliseconds>(
            stop - start);

    // Time in seconds
    cout << "for " << prime << " : "
         << duration.count() / 1000.0
         << " seconds "
         << endl;
}

// Driver code
int main()
{
    // Function call for prime 1
    insert(prime1);

    // Function call for prime 2
    insert(prime2);
}
```

**输出:**

```cpp
for 107897 : 0.029 seconds
for 126271 : 0.026 seconds
```