# 用 C++ 打印金字塔图案的程序

> 原文:[https://www . geesforgeks . org/programs-printing-金字塔-patterns-c/](https://www.geeksforgeeks.org/programs-printing-pyramid-patterns-c/)

本文旨在给出一个模式打印的 C++ 实现。

**简单金字塔图案**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate star pattern
#include <iostream>
using namespace std;

// Function to demonstrate printing pattern
void pypart(int n)
{
    // Outer loop to handle number of rows
    // n in this case
    for (int i = 0; i < n; i++) {

        // Inner loop to handle number of columns
        // values changing acc. to outer loop
        for (int j = 0; j <= i; j++) {

            // Printing stars
            cout << "* ";
        }

        // Ending line after each row
        cout << endl;
    }
}

// Driver Function
int main()
{
    int n = 5;
    pypart(n);
    return 0;
}
```

**Output**

```cpp
* 
* * 
* * * 
* * * * 
* * * * * 
```

**使用 while Loop**
打印上述图案

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate star pattern
#include <iostream>
using namespace std;

// Function to demonstrate printing pattern
void pypart(int n)
{
    // Outer loop to handle number of rows
    // n in this case
    int i = 0, j = 0;
    while (i < n) {

        // Inner loop to handle number of columns
        // values changing acc. to outer loop
        while (j <= i) {

            // Printing stars
            cout << "* ";
            j++ ;
        }
        j = 0; // we have to reset j value so as it can
               // start from beginning and print * equal to i.
        i++ ;
        // Ending line after each row
        cout << endl;
    }
}

// Driver Code
int main()
{
    int n = 5;
    pypart(n);
    return 0;
}
```

**Output**

```cpp
* 
* * 
* * * 
* * * * 
* * * * * 
```

**旋转 180 度后**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate star pattern
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int n = 5;

    //looping rows
    for(int i=n; i>0; i--)
    {
      for(int j=0; j<=n; j++) //looping columns
      {
        if (j>=i)
        {
          cout<<"*";
        }
        else
        {
          cout<<" ";
        }
      }
      cout<<endl;
    }
    return 0;
}
```

**Output**

```cpp
        * 
      * * 
    * * * 
  * * * * 
* * * * * 
```

**使用 while loop 打印上面的图案**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ code to demonstrate pattern printing
#include <iostream>
using namespace std;

// Function to demonstrate printing pattern
void pypart2(int n)
{
    int i = 0, j = 0, k = 0;
    while (i < n) {

          // for number of spaces
        while (k < (n - i - 1)) {
            cout << "  ";
            k++ ;
        }

          // resetting k because we want to run k from
        // beginning.
        k = 0;
        while (j <= i) {
            cout << "* ";
            j++ ;
        }

          // resetting k so as it can start from 0.
        j = 0;
        i++ ;
        cout << endl;
    }
}

// Driver Code
int main()
{
    int n = 5;

      // Function Call
    pypart2(n);
    return 0;
}
```

**Output**

```cpp
        * 
      * * 
    * * * 
  * * * * 
* * * * * 
```