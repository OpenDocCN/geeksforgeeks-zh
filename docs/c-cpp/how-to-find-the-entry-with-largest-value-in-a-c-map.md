# 如何在 C++ 图中找到值最大的条目

> 原文:[https://www . geesforgeks . org/如何找到 c-a-c-map 中价值最大的条目/](https://www.geeksforgeeks.org/how-to-find-the-entry-with-largest-value-in-a-c-map/)

给定一个 C++ 中的[图，任务是找到这个图中值最高的条目。](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)

**示例:**

```cpp
Input: Map = {ABC = 10, DEF = 30, XYZ = 20}
Output: DEF = 30

Input: Map = {1 = 40, 2 = 30, 3 = 60}
Output: 3 = 60

```

**接近**

1.  [在](https://www.geeksforgeeks.org/traversing-a-map-or-unordered_map-in-cpp-stl/)[迭代器](https://www.geeksforgeeks.org/iterators-c-stl/)

    ```cpp
    map::iterator itr;
    for (itr = some_map.begin();
         itr != some_map.end();
         ++ itr) 
    {
        // operations
    } 
    ```

    的帮助下，逐个条目迭代地图条目
2.  将第一个条目存储在引用变量中，以便最初进行比较。
3.  如果当前条目的值大于引用条目的值，则将当前条目存储为引用条目。
4.  对地图中的所有条目重复此过程。
5.  最后，引用变量具有映射中最高值的必需条目。
6.  打印此条目

下面是上述方法的实现:

```cpp
// C++ program to find the Entry
// with largest Value in a Map

#include <bits/stdc++.h>
using namespace std;

// Function to print the Map
void printMap(map<int, int> sampleMap)
{
    map<int, int>::iterator itr;
    for (itr = sampleMap.begin();
         itr != sampleMap.end();
         ++ itr) {
        cout << itr->first
             << " = " << itr->second << ", ";
    }
    cout << endl;
}

// Function tp find the Entry
// with largest Value in a Map
pair<int, int> findEntryWithLargestValue(
    map<int, int> sampleMap)
{

    // Reference variable to help find
    // the entry with the highest value
    pair<int, int> entryWithMaxValue
        = make_pair(0, 0);

    // Iterate in the map to find the required entry
    map<int, int>::iterator currentEntry;
    for (currentEntry = sampleMap.begin();
         currentEntry != sampleMap.end();
         ++ currentEntry) {

        // If this entry's value is more
        // than the max value
        // Set this entry as the max
        if (currentEntry->second
            > entryWithMaxValue.second) {

            entryWithMaxValue
                = make_pair(
                    currentEntry->first,
                    currentEntry->second);
        }
    }

    return entryWithMaxValue;
}

// Driver code
int main()
{

    // Map
    map<int, int> sampleMap;
    sampleMap.insert(pair<int, int>(1, 40));
    sampleMap.insert(pair<int, int>(2, 30));
    sampleMap.insert(pair<int, int>(3, 60));

    // Printing map
    cout << "Map: ";
    printMap(sampleMap);

    // Get the entry with largest value
    pair<int, int> entryWithMaxValue
        = findEntryWithLargestValue(sampleMap);

    // Print the entry
    cout << "Entry with highest value: "
         << entryWithMaxValue.first << " = "
         << entryWithMaxValue.second << endl;

    return 0;
}
```

**Output:**

```cpp
Map: 1 = 40, 2 = 30, 3 = 60, 
Entry with highest value: 3 = 60

```