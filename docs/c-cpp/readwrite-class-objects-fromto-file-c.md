# 在 C++ 中从/向文件读取/写入类对象

> 原文:[https://www . geesforgeks . org/read write-class-objects-from-file-c/](https://www.geeksforgeeks.org/readwrite-class-objects-fromto-file-c/)

给定一个文件“Input.txt”，其中每一行的值都与一个类的实例变量相同。
将值读入类的对象，并进行必要的操作。
**理论:**

```cpp
The data transfer is usually done using '>>'
and <<' operators. But if you have
a class with 4 data members and want 
to write all 4 data members from its
object directly to a file or vice-versa, 
we can do that using following syntax :

To write object's data members in a file :
// Here file_obj is an object of ofstream
file_obj.write((char *) & class_obj, sizeof(class_obj));

To read file's data members into an object :
// Here file_obj is an object of ifstream
file_obj.read((char *) & class_obj, sizeof(class_obj));

```

**示例:**

```cpp
Input : 
Input.txt :
Michael 19 1806
Kemp 24 2114
Terry 21 2400
Operation : Print the name of the highest 
            rated programmer.

Output : 
Terry

```

## C++

```cpp
// C++ program to demonstrate read/write of class
// objects in C++.
#include <iostream>
#include <fstream>
using namespace std;

// Class to define the properties
class Contestant {
public:
    // Instance variables
    string Name;
    int Age, Ratings;

    // Function declaration of input() to input info
    int input();

    // Function declaration of output_highest_rated() to
    // extract info from file Data Base
    int output_highest_rated();
};

// Function definition of input() to input info
int Contestant::input()
{
    // Object to write in file
    ofstream file_obj;

    // Opening file in append mode
    file_obj.open("Input.txt", ios::app);

    // Object of class contestant to input data in file
    Contestant obj;

    // Feeding appropriate data in variables
    string str = "Michael";
    int age = 18, ratings = 2500;

    // Assigning data into object
    obj.Name = str;
    obj.Age = age;
    obj.Ratings = ratings;

    // Writing the object's data in file
    file_obj.write((char*)&obj, sizeof(obj));

    // Feeding appropriate data in variables
    str = "Terry";
    age = 21;
    ratings = 3200;

    // Assigning data into object
    obj.Name = str;
    obj.Age = age;
    obj.Ratings = ratings;

    // Writing the object's data in file
    file_obj.write((char*)&obj, sizeof(obj));

    return 0;
}

// Function definition of output_highest_rated() to
// extract info from file Data Base
int Contestant::output_highest_rated()
{
    // Object to read from file
    ifstream file_obj;

    // Opening file in input mode
    file_obj.open("Input.txt", ios::in);

    // Object of class contestant to input data in file
    Contestant obj;

    // Reading from file into object "obj"
    file_obj.read((char*)&obj, sizeof(obj));

    // max to store maximum ratings
    int max = 0;

    // Highest_rated stores the name of highest rated contestant
    string Highest_rated;

    // Checking till we have the feed
    while (!file_obj.eof()) {
        // Assigning max ratings
        if (obj.Ratings > max) {
            max = obj.Ratings;
            Highest_rated = obj.Name;
        }

        // Checking further
        file_obj.read((char*)&obj, sizeof(obj));
    }

    // Output is the highest rated contestant
    cout << Highest_rated;
    return 0;
}

// Driver code
int main()
{
    // Creating object of the class
    Contestant object;

    // Inputting the data
    object.input();

    // Extracting the max rated contestant
    object.output_highest_rated();

    return 0;
}
```

**输出:**

```cpp
Terry

```

本文由 [**罗希特·塔普利亚尔**](https://www.linkedin.com/in/rohit-thapliyal-515b5913a/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。