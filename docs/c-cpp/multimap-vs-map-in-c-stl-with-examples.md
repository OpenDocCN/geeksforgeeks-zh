# c++ STL 中的多映射与映射，示例

> 原文:[https://www . geesforgeks . org/multimap-vs-map-in-c-STL-with-examples/](https://www.geeksforgeeks.org/multimap-vs-map-in-c-stl-with-examples/)

[**<u>c++ STL 中的地图</u>**](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)

Map 以排序的方式存储唯一的键值对。每个键都与一个可能唯一也可能不唯一的值唯一关联。可以在地图中插入或删除关键字，但不能修改。分配给键的值可以更改。这是一种使用密钥快速访问值的好方法，并且在 0(1)分钟内完成。

## C++

```cpp
#include <iostream>
#include <iterator>
#include <map>

using namespace std;

int main()
{

    // empty map container
    map<int, int> gquiz1;

    // insert elements in random order
    gquiz1.insert(pair<int, int>(1, 40));
    gquiz1.insert(pair<int, int>(2, 30));
    gquiz1.insert(pair<int, int>(3, 60));
    gquiz1.insert(pair<int, int>(4, 20));
    gquiz1.insert(pair<int, int>(5, 50));
    gquiz1.insert(pair<int, int>(6, 50));
    gquiz1.insert(pair<int, int>(7, 10));

    // printing map gquiz1
    map<int, int>::iterator itr;
    cout << "\nThe map gquiz1 is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz1.begin(); itr != gquiz1.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }
    cout << endl;

    // assigning the elements from gquiz1 to gquiz2
    map<int, int> gquiz2(gquiz1.begin(), gquiz1.end());

    // print all elements of the map gquiz2
    cout << "\nThe map gquiz2 after"
         << " assign from gquiz1 is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }
    cout << endl;

    // remove all elements up to
    // element with key=3 in gquiz2
    cout << "\ngquiz2 after removal of"
            " elements less than key=3 : \n";
    cout << "\tKEY\tELEMENT\n";
    gquiz2.erase(gquiz2.begin(), gquiz2.find(3));
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }

    // remove all elements with key = 4
    int num;
    num = gquiz2.erase(4);
    cout << "\ngquiz2.erase(4) : ";
    cout << num << " removed \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }

    cout << endl;

    // lower bound and upper bound
    // for map gquiz1 key = 5
    cout << "gquiz1.lower_bound(5) : "
         << "\tKEY = ";
    cout << gquiz1.lower_bound(5)->first << '\t';
    cout << "\tELEMENT = "
         << gquiz1.lower_bound(5)->second << endl;
    cout << "gquiz1.upper_bound(5) : "
         << "\tKEY = ";
    cout << gquiz1.upper_bound(5)->first << '\t';
    cout << "\tELEMENT = "
         << gquiz1.upper_bound(5)->second << endl;

    return 0;
}
```

**Output**

> 地图 gquiz1 为:
> 关键要素
> 1 40
> 2 30
> 3 60
> 4 20
> 5 50
> 6 50
> 7 10
> 
> 从 gquiz1 分配后的地图 gquiz2 为:
> 关键元素
> 1 40
> 2 30
> 3 60
> 4 20
> 5 50
> 6 50
> 7 10
> 
> 移除小于键的元素后 gquiz 2 = 3:
> 键元素
> 3 60
> 4 20
> 5 50
> 6 50
> 7 10
> 
> gquiz2.erase(4) : 1 已移除
> 关键元素
> 3 60
> 5 50
> 6 50
> 7 10
> 
> gquiz1 .下界(5) : KEY = 5 ELEMENT = 50
> gquiz1 .上界(5) : KEY = 6 ELEMENT = 50

[**<u>c++ STL 中的 Multimap</u>**](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/)

<u>多重映射类似于映射，除此之外，多个元素可以有相同的键。此外，在这种情况下，不要求键值和映射值对必须是唯一的。关于 multimap 需要注意的一点是，multimap 始终保持所有键的排序顺序。multimap 的这些特性使得它在竞争性编程中非常有用。</u>

## <u>C++ </u>

```cpp
#include <iostream>
#include <iterator>
#include <map>

using namespace std;

int main()
{
    // empty multimap container
    multimap<int, int> gquiz1;

    // insert elements in random order
    gquiz1.insert(pair<int, int>(1, 40));
    gquiz1.insert(pair<int, int>(2, 30));
    gquiz1.insert(pair<int, int>(3, 60));
    gquiz1.insert(pair<int, int>(6, 50));
    gquiz1.insert(pair<int, int>(6, 10));

    // printing multimap gquiz1
    multimap<int, int>::iterator itr;
    cout << "\nThe multimap gquiz1 is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz1.begin(); itr != gquiz1.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }
    cout << endl;

    // adding elements randomly,
    // to check the sorted keys property
    gquiz1.insert(pair<int, int>(4, 50));
    gquiz1.insert(pair<int, int>(5, 10));

    // printing multimap gquiz1 again

    cout << "\nThe multimap gquiz1 after"
         << " adding extra elements is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz1.begin(); itr != gquiz1.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }
    cout << endl;

    // assigning the elements from gquiz1 to gquiz2
    multimap<int, int> gquiz2(gquiz1.begin(),
                              gquiz1.end());

    // print all elements of the multimap gquiz2
    cout << "\nThe multimap gquiz2 after"
         << " assign from gquiz1 is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }
    cout << endl;

    // remove all elements up to
    // key with value 3 in gquiz2
    cout << "\ngquiz2 after removal of"
         << " elements less than key=3 : \n";
    cout << "\tKEY\tELEMENT\n";
    gquiz2.erase(gquiz2.begin(), gquiz2.find(3));
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }

    // remove all elements with key = 4
    int num;
    num = gquiz2.erase(4);
    cout << "\ngquiz2.erase(4) : ";
    cout << num << " removed \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }

    cout << endl;

    // lower bound and upper bound
    // for multimap gquiz1 key = 5
    cout << "gquiz1.lower_bound(5) : "
         << "\tKEY = ";
    cout << gquiz1.lower_bound(5)->first << '\t';
    cout << "\tELEMENT = "
         << gquiz1.lower_bound(5)->second
         << endl;
    cout << "gquiz1.upper_bound(5) : "
         << "\tKEY = ";
    cout << gquiz1.upper_bound(5)->first << '\t';
    cout << "\tELEMENT = "
         << gquiz1.upper_bound(5)->second
         << endl;

    return 0;
}
```

<u>**Output**

> 多点 gquiz1 为:
> 关键要素
> 1 40
> 2 30
> 3 60
> 6 50
> 6 10
> 
> 添加额外元素后的多参数 gquiz1 为:
> 关键元素
> 1 40
> 2 30
> 3 60
> 4 50
> 5 10
> 6 50
> 6 10
> 
> 从 gquiz1 分配后的多映射 gquiz2 为:
> 关键元素
> 1 40
> 2 30
> 3 60
> 4 50
> 5 10
> 6 50
> 6 10
> 
> 移除小于键的元素后 gquiz 2 = 3:
> 键元素
> 3 60
> 4 50
> 5 10
> 6 50
> 6 10
> 
> gquiz2.erase(4) : 1 已移除
> 关键元素
> 3 60
> 5 10
> 6 50
> 6 10
> 
> gquiz1 .下界(5) : KEY = 5 ELEMENT = 10
> gquiz1 .上界(5) : KEY = 6 ELEMENT = 50</u> 

<u>**<u>c++ STL 中 Map 和 Multimap 的区别</u>**</u>

<figure class="table"><u>T22】1</u>

| **S number** | **地图** | **多工位** |
| It stores unique key-value pairs, where each key is unique. | It can store duplicate key-value pairs where the key may not be unique. |
| Two | Using the count () function on the map can only return two values of 0 or 1. | Use the count () function on multiple maps to return any non-negative integer. |
| three | It is easy to access the value of any key, and you can access it directly. | It is not easy to access the value of any key, nor can it be accessed directly. |
| four | Using the key to delete in the map will only delete one key-value pair. | Using key deletion in multi-mapping will delete all key-value pairs with the same key. |
| five | Map can be used when a simple lookup table with a unique key-value pair is needed to quickly access the value using the key. | You can use multiple mappings when you need to use keys to group values together. |

</figure>