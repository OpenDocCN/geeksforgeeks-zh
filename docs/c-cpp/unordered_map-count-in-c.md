# c++ 中无序 _ 映射计数()

> 原文:[https://www.geeksforgeeks.org/unordered_map-count-in-c/](https://www.geeksforgeeks.org/unordered_map-count-in-c/)

无序映射::count()是 C++ 中的一个内置方法，用于计算具有给定键的无序映射中的元素数量。

**注意**:由于无序 _map 不允许存储重复键的元素，所以 count()函数基本上是检查给定键的无序 _map 中是否存在元素。

**语法**:

```cpp
size_type count(Key);

```

**参数**:该功能接受单个参数*键*，需要在给定的无序地图容器中进行检查。

**返回值**:如果给定键的地图中存在值，则该函数返回 1，否则返回 0。

下面的程序说明了无序 _map::count()函数:

**程序 1** :

```cpp
// C++ program to illustrate the 
// unordered_map::count() function

#include<iostream>
#include<unordered_map>

using namespace std;

int main()
{
    // unordered map
    unordered_map<int , string> umap;

    // Inserting elements into the map
    umap.insert(make_pair(1,"Welcome"));
    umap.insert(make_pair(2,"to"));
    umap.insert(make_pair(3,"GeeksforGeeks"));

    // Check if element with key 1 is present using 
    // count() function
    if(umap.count(1))
    {
        cout<<"Element Found"<<endl;
    }
    else
    {
        cout<<"Element Not Found"<<endl;    
    }

    return 0;
}
```

**Output:**

```cpp
Element Found

```

**程序 2** :

```cpp
// C++ program to illustrate the 
// unordered_map::count() function

#include<iostream>
#include<unordered_map>

using namespace std;

int main()
{
    // unordered map
    unordered_map<int , string> umap;

    // Inserting elements into the map
    umap.insert(make_pair(1,"Welcome"));
    umap.insert(make_pair(2,"to"));
    umap.insert(make_pair(3,"GeeksforGeeks"));

    // Try inserting element with
    // duplicate keys
    umap.insert(make_pair(3,"CS Portal"));

    // Print the count of values with key 3
    // to check if duplicate values are stored 
    // or not
    cout<<"Count of elements in map, mapped with key 3: "
            <<umap.count(3);

    return 0;
}
```

**Output:**

```cpp
Count of elements in map, mapped with key 3: 1

```