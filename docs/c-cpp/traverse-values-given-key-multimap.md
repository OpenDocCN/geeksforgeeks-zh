# 如何遍历 multimap 中给定键的所有值？

> 原文:[https://www . geeksforgeeks . org/traverse-values-given-key-multimap/](https://www.geeksforgeeks.org/traverse-values-given-key-multimap/)

给定一个[多重映射](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/)和多重映射的一个键，我们的任务是简单地显示给定键的(键-值)对。在 multimap 中，同一个键可以有多个(键-值)对。假设我们的多重地图包含

```cpp
key     value
1         10
2         20
2         30
2         40
3         50
4         60
4         70

key : 2
key     value
2         20
2         30
2         40
```

就像 C++ STL 中的无序映射一样，我们不能像
那样获取值

```cpp
int key = 2;
multimap  map;

// insert values in map
cout << "Key : " << key;
cout << "Value : " < second;
```

输出:

```cpp
Key : 2
Value : 20
```

因为上面的方法将只返回当前键的第一次出现，所以如果同一个键有多个(键-值)对，该方法将失败。
有两种方法可以达到预期的效果:
**方法 1(简单遍历)**遍历整个地图，只要键等于给定的键，我们就显示键值对。

## C++

```cpp
// CPP program to find all values for a
// given key.
#include <bits/stdc++.h>
using namespace std;

int main()
{
    multimap <int, int> map;

    // insert the values in multimap
    map.insert(make_pair(1, 10));
    map.insert(make_pair(2, 20));
    map.insert(make_pair(2, 30));
    map.insert(make_pair(2, 40));
    map.insert(make_pair(3, 50));
    map.insert(make_pair(4, 60));
    map.insert(make_pair(4, 70));

    int key = 2;   
    for (auto itr = map.begin(); itr != map.end(); itr++)   
        if (itr -> first == key)       
            cout << itr -> first << "  "
                 << itr -> second << endl;

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// JAVA program to find all values for a
// given key.
import java.util.*;

class GFG
{

static class pair
{
    int first, second;
    public pair(int first, int second)
    {
        this.first = first;
        this.second = second;
    }
}

public static void main(String[] args)
{
    HashSet <pair> map = new LinkedHashSet<>();

    // add the values in multimap
    map.add(new pair(1, 10));
    map.add(new pair(2, 20));
    map.add(new pair(2, 30));
    map.add(new pair(2, 40));
    map.add(new pair(3, 50));
    map.add(new pair(4, 60));
    map.add(new pair(4, 70));

    int key = 2;
    for (pair itr : map)
        if (itr.first == key)    
            System.out.println(itr.first+ " "
                + itr.second);
}
}

// This code is contributed by 29AjayKumar
```

## 蟒蛇 3

```cpp
# Python program to find all values for a
# given key.
map = []

# insert the values in multimap
map.append((1, 10));
map.append((2, 20));
map.append((2, 30));
map.append((2, 40));
map.append((3, 50));
map.append((4, 60));
map.append((4, 70));

key = 2;   
for i in map:
    if i[0] == key:
        print(i[0],i[1])

# This code is contributed by shubhamsingh10
```

## C#

```cpp
// C# program to find all values for a
// given key.
using System;
using System.Collections.Generic;

class GFG
{

class pair
{
    public int first, second;
    public pair(int first, int second)
    {
        this.first = first;
        this.second = second;
    }
}

// Driver code
public static void Main(String[] args)
{
    HashSet<pair> map = new HashSet<pair>();

    //.Add the values in multimap
    map.Add(new pair(1, 10));
    map.Add(new pair(2, 20));
    map.Add(new pair(2, 30));
    map.Add(new pair(2, 40));
    map.Add(new pair(3, 50));
    map.Add(new pair(4, 60));
    map.Add(new pair(4, 70));

    int key = 2;
    foreach (pair itr in map)
        if (itr.first == key)    
            Console.WriteLine(itr.first+ " "
                + itr.second);
}
}

// This code is contributed by Rajput-Ji
```

## java 描述语言

```cpp
<script>

class pair
{
    constructor(first,second)
    {
        this.first=first;
        this.second=second;
    }
}

let map = new Set();
// add the values in multimap
map.add(new pair(1, 10));
map.add(new pair(2, 20));
map.add(new pair(2, 30));
map.add(new pair(2, 40));
map.add(new pair(3, 50));
map.add(new pair(4, 60));
map.add(new pair(4, 70));

let key = 2;
for (let itr of map.values())
    if (itr.first == key)    
        document.write(itr.first+ " "
                   + itr.second+"<br>");

// This code is contributed by rag2127
</script>
```

**输出:**

```cpp
2  20
2  30
2  40
```

**方法 2(使用二分搜索法)**找到给定键的[下界](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)和[上界](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)，并在它们之间遍历。
下界(key):返回指向大于或等于 key 的第一个元素的迭代器。
upper_bound(key):返回指向大于 key 的第一个元素的迭代器。

```cpp
key     value
1         10
2         20 <-- lower_bound(20)
2         30
2         40
3         50 <-- upper_bound(20)
4         60
4         70
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    multimap <int, int> map;

    // insert the values in multimap
    map.insert(make_pair(1, 10));
    map.insert(make_pair(2, 20));
    map.insert(make_pair(2, 30));
    map.insert(make_pair(2, 40));
    map.insert(make_pair(3, 50));
    map.insert(make_pair(4, 60));
    map.insert(make_pair(4, 70));

    int key = 2;   
    auto itr1 = map.lower_bound(key);
    auto itr2 = map.upper_bound(key);

    while (itr1 != itr2)   
    {
        if (itr1 -> first == key)
           cout << itr1 -> first << "  " 
                << itr1 -> second << endl;       
        itr1++ ;
    }   
    return 0;
}
```

输出:

```cpp
2  20
2  30
2  40
```