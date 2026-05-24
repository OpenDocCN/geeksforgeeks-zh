# 在 C/C++ 中高精度测量执行时间

> 原文:[https://www . geesforgeks . org/measure-execution-time-with-high-precision-in-c/](https://www.geeksforgeeks.org/measure-execution-time-with-high-precision-in-c-c/)

**执行时间:**给定任务的执行时间或 CPU 时间定义为系统执行该任务所花费的时间换句话说你可以说是程序运行的时间。
有多种方法可以测量一个程序的执行时间，在本文中我将讨论 5 种不同的方法来
测量一个程序的执行时间。

1.  **Using **`time()`** function in C & C++**.

    > **time() :** time()函数以秒为单位返回自 Epoch(1970 年 1 月 1 日)以来的时间。
    > **头文件:**【time . h】
    > **原型/语法:**time _ t time(time _ t * tloc)；
    > **返回值:**成功时，返回纪元以来的时间值(秒)，出错时返回-1。

    下面程序演示如何使用`time()`功能测量执行时间。

    ```cpp
    #include <bits/stdc++.h>
    using namespace std;

    // A sample function whose time taken to
    // be measured
    void fun()
    {
        for (int i=0; i<10; i++)
        {
        }
    }

    int main()
    {
        /* Time function returns the time since the 
            Epoch(jan 1 1970). Returned time is in seconds. */
        time_t start, end;

        /* You can call it like this : start = time(NULL);
         in both the way start contain total time in seconds 
         since the Epoch. */
        time(&start);

        // unsync the I/O of C and C++.
        ios_base::sync_with_stdio(false);

        fun();

        // Recording end time.
        time(&end);

        // Calculating total time taken by the program.
        double time_taken = double(end - start);
        cout << "Time taken by program is : " << fixed
             << time_taken << setprecision(5);
        cout << " sec " << endl;
        return 0;
    }
    ```

    **Output:**

    ```cpp
    Time taken by program is : 0.000000 sec

    ```