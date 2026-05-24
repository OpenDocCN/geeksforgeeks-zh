# C 中 dos.h 标头，带示例

> 原文:[https://www . geesforgeks . org/dos-h-header-in-c-with-examples/](https://www.geeksforgeeks.org/dos-h-header-in-c-with-examples/)

**dos.h** 是 [C 语言](https://www.geeksforgeeks.org/c-programming-language/)的头文件。该库具有用于处理[中断](https://www.geeksforgeeks.org/interrupts/)的功能，产生声音、日期和时间功能等。它是 Borland 特有的，在像 **Turbo C 编译器**这样的编译器中工作。
以下是该库支持的功能:

1.  **delay():** The **delay()** function in C is used to stop the execution of the program for some period of time.
    **Syntax:**

    ```cpp
    delay(unsigned int)

    ```

    **参数:**它接受一个**时间**以毫秒为单位停止程序执行到那个时间段。

    以下是说明**延迟()**的程序:

    ```cpp
    // C program to implement delay()
    #include <dos.h>
    #include <stdio.h>
    #include <stdlib.h>

    // Driver Code
    int main()
    {
        printf("Takes 10 sec and exit.\n");

        // Delay the program execution
        // for 1 second
        delay(10000);

        return 0;
    }
    ```

2.  **sleep():** The **sleep()** function in C is used to delay the execution of the program for some period of time.
    **Syntax:**

    ```cpp
    sleep(unsigned seconds)

    ```

    **参数:**接受以秒为单位的时间，将程序的执行延迟到该时间段。

    下面是说明**睡眠()**的程序:

    ```cpp
    // C program to implement sleep()
    #include <dos.h>
    #include <stdio.h>
    #include <stdlib.h>

    // Driver Code
    int main()
    {
        printf("Wait 2 sec and exit.\n");

        // Delay the program execution
        // for by 2 seconds
        sleep(2);

        return 0;
    }
    ```

3.  **getdate():** The **getdate()** function in C is used to get the current Date of the system.

    **语法:**

    ```cpp
    getdate(struct date d)

    ```

    **参数:**它接受在 **dos.h** 库中定义的结构日期。使用功能 **da_day()** 、 **da_mon()** 和 **da_year()** 打印日期。

    下面是说明 **getdate()** 的程序:

    ```cpp
    // C program to implement getdate()
    #include <dos.h>
    #include <stdio.h>
    #include <stdlib.h>

    // Driver Code
    int main()
    {
        // Structure of date
        struct date a;

        // Function call to get the date
        // of the system
        getdate(&a);

        // Print the date, month and year
        printf("The Date is: %d/%d/%d\n", a.da_day,
               a.da_mon,
               a.da_year);

        return 0;
    }
    ```

4.  **gettime():** The **gettime()** function in C is used to get the Time shown by the System.

    **语法:**

    ```cpp
    gettime(struct time t)

    ```

    **参数:**它接受在 **dos.h** 库中定义的结构时间。使用功能 **ti_hour()** 、 **ti_min()** 和 **ti_sec()** 打印日期。

    下面是说明 **gettime()** 的程序:

    ```cpp
    // C program to implement gettime()
    #include <dos.h>
    #include <stdio.h>
    #include <stdlib.h>

    // Driver Code
    int main()
    {
        // Structure of time
        struct time t;

        // Function call to get the time
        // of the system
        getdate(&t);

        // Print the hour, minutes and second
        printf("The time is: %d : %d : %d\n", x.ti_hour,
               x.ti_min,
               x.ti_sec);

        return 0;
    }
    ```

5.  **sound():** The **sound()** function in C is used to play different sound on different frequency on our system.

    **语法:**

    ```cpp
    sound(int frequency)

    ```

    **参数:**它接受一个频率，并在我们的系统中播放该频率的声音。

    下面是说明**音()**的程序:

    ```cpp
    // C program to implement sound()
    #include <dos.h>
    #include <stdio.h>
    #include <stdlib.h>

    // Driver Code
    int main()
    {
        // Initialise frequency
        int x = 200;

        // Loop for playing sound of
        // increasing frequency
        for (; x < 1000; x++) {

            // Function to play sound
            sound(x);

            delay(25);
        }

        // To stop the frequency
        nosound();
        return 0;
    }
    ```

6.  **nosound():** The **nosound()** function in C is used to stop the sound played by souns() function.

    **语法:**

    ```cpp
    nosound()

    ```

    **参数:**不接受任何参数。

    下面是说明 **nosound()** 的程序:

    ```cpp
    // C program to implement nosound()
    #include <dos.h>
    #include <stdio.h>
    #include <stdlib.h>

    // Driver Code
    int main()
    {
        // Initialise frequency
        int x = 200;

        // Function call to play sound
        // with frequency 200htz
        sound(x);

        // Delay sound for 1 sec
        delay(1000);

        // To stop the sound
        nosound();
        return 0;
    }
    ```