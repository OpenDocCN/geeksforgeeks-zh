# C 区铁路预约系统

> 原文:[https://www . geesforgeks . org/railway-reservation-system-in-c/](https://www.geeksforgeeks.org/railway-reservation-system-in-c/)

铁路客票订票系统由 [C 编程](https://www.geeksforgeeks.org/c/)实现。就像我们去网上订票时看到的一样。在此软件中预订火车票时，遵循以下一系列步骤-

1.  第一步是提供乘客总数，并提交乘客的所有必要细节。
2.  下一步是输入源和目标。
3.  将出现一个可用列车列表。其中，用户要选择一个。
4.  将评估票据价值。系统将要求通过显示座位矩阵来输入座位选择。最后，屏幕上会生成一张收据。

**进场:**

*   第一步是实现一个[结构](https://www.geeksforgeeks.org/structures-c/)，用于记录乘客的详细信息，如姓名、性别和年龄。
*   五个[函数](https://www.geeksforgeeks.org/functions-in-c/)被定义为 void details(int)、void add_node(char，char，int)、int seat(int)、int cal(int，int)、void bill(int，int)才能顺利工作。
*   结构中有三个元素，如两个字符串，一个用于记录乘客姓名和性别，一个用于记录乘客年龄的整数。此外，将使用结构指针来帮助链接另一个乘客的下一个节点。类似于[链表](https://www.geeksforgeeks.org/data-structures/linked-list/)。
*   字符[数组](https://www.geeksforgeeks.org/arrays-in-c-cpp/)被定义，一些整数数组被全局定义。
*   以乘客人数为输入，这些详细信息被发送到**详细信息()功能**。
*   执行 for 循环，记录每个乘客的详细信息。用户输入的详细信息将被发送到 add_node()函数。
*   在 add_node 函数中，每个细节将存储在每个乘客的一个节点中。这些节点将相互链接。这是基于链表的概念。
*   输入出发地、目的地，它将提供一些可用的列车选择。基于此，用户必须做出选择。然后调用 **cal()函数**。
*   在 **cal()功能**中，用户必须给出卧铺或空调等级的选择。如果用户选择 a.c .类，将打开另外三个选项，用户必须根据系统将在该金额上添加 18%的商品及服务税并计算总金额来给出另一个选择。
*   调用**座位()功能**，在这里会给用户一个座位矩阵，用户必须选择一个与乘客数量相同的座位。
*   最后，调用**账单()功能**，显示账单总金额及所有必要的详细信息。

下面是上述方法的实现:

## C

```cpp
// C program for the above approach
#include <conio.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Defining Structure
typedef struct mynode {
    char name[20];
    char gen[6];
    int age;
    struct mynode* link;
} Node;

Node* start = NULL;

void details(int);
int seat(int);
int cal(int, int, int);
void bill(int, int);

// Global variables
char source[20], des[20], train[40];
char station[40], cla[40];
int time1, time2, a[55];

// Driver Code
void main()
{
    int i, j, a1, a2, b, c, int x = 0, d, e, r;
    char o;
    printf("Enter Number Of Passengers: ");
    fflush(stdin);
    scanf("%d", &j);

    // Calling details() function with
    // argument number of passenger
    details(j);
    printf("Enter The Source Place: ");
    fflush(stdin);
    gets(source);
    printf("Enter The Destination Place: ");
    gets(des);
    printf("\t\tThe Following Trains "
           "Are Available.....\n");
    printf("\t\t1\. Rajdhani Express.."
           ".......10:00 "
           "a.m........Sealdah Station\n");
    printf("\t\t2\. Satabdi Express..."
           ".......05:00 "
           "p.m........Howrah Station\n");
    printf("\t\t3\. Humsafar Express..."
           ".......11:00 "
           "p.m........Kolkata Chitpur"
           " Station\n");
    printf("\t\t4\. Garib-Rath Express"
           ".........05:00 "
           "p.m........Sealdah Station\n");
    printf("\t\t5\. Duronto Express..."
           ".........07:00 "
           "a.m.........Santraganchi"
           "Station\n");
    scanf("%d", &i);
    do {
        switch (i) {
        case 1: {
            strcpy(train,
                   "Rajdhani Express");
            strcpy(station,
                   "Sealdah Station");
            time1 = 10;
            time2 = 00;
            a1 = 2099;
            a2 = 1560;

            // Calling cal() function
            // with the three argument
            // and return value
            d = cal(a1, a2, j);
            printf("Total Bill Amount:"
                   " %d\n",
                   d);
        }; break;
        case 2: {
            strcpy(train,
                   "Satabdi Express");
            strcpy(station,
                   "Howrah Station");
            time1 = 05;
            time2 = 00;
            a1 = 1801;
            a2 = 981;

            // Calling cal() function with
            // three argument & return value
            d = cal(a1, a2, j);
            printf("Total Bill Amount:"
                   "%d\n",
                   d);
        }; break;
        case 3: {
            strcpy(train,
                   "Humsafar Express");
            strcpy(station,
                   "Kolkata Chitpur Express");
            time1 = 11;
            time2 = 00;
            a1 = 2199;
            a2 = 1780;

            // Calling cal() function with
            // three argument & return value
            d = cal(a1, a2, j);
            printf("Total Bill Amount: %d\n", d);
        }; break;
        case 4: {
            strcpy(train, "Garib-Rath Express");
            strcpy(station, "Sealdah Station");
            time1 = 05;
            time2 = 00;
            a1 = 1759;
            a2 = 1200;

            // Calling cal() function with
            // three argument & return value
            d = cal(a1, a2, j);
            printf("Total Bill Amount: %d\n", d);
        }; break;
        case 5: {
            strcpy(train, "Duronto Express");
            strcpy(station, "Santraganchi Station");
            time1 = 07;
            time2 = 00;
            a1 = 2205;
            a2 = 1905;

            // Calling cal() function with
            // three argument & return value
            d = cal(a1, a2, j);
            printf("Total Bill Amount: %d\n", d);
        }; break;
        default:
            printf("Enter Correct choice.....\n");
            x = 1;
            break;
        }
    } while (x);
    printf("Now Book Your Seats......\n");

    // Calling seat() function with number
    // of passenger
    seat(j);

    // Calling bill() function with
    // the number of passenger
    // and amount argument
    bill(d, j);
}

// Function for calculation of amount
int cal(int y1, int y2, int h)
{
    int b, c, i, t, r, n;
    printf("\t\tEnter Your Choice......\n");
    printf("\t\t1\. Slepper Class....\n");
    printf("\t\t2\. A.C Class.......\n");
    scanf("%d", &i);
    switch (i) {
    case 1: {
        strcpy(cla, "Slepper Class");
        b = y2 * h;
        c = b + (b * 0.18);
    } break;
    case 2: {
        printf("\t\tEnter Your Choice....\n");
        printf("\t\t1\. 3A Class....\n");
        printf("\t\t2\. 2A Class....\n");
        printf("\t\t3\. 1st Class A.C.....\n");
        scanf("%d", &n);
        switch (n) {
        case 1: {
            strcpy(cla, "3A Class");
            b = y1 * h;
            c = b + (b * 0.18);
        } break;
        case 2: {
            strcpy(cla, "2A Class");
            b = (y1 + 1000) * h;
            c = b + (b * 0.18);
        } break;
        case 3: {
            strcpy(cla, "1st Class A.C.");
            b = (y1 + 5000) * h;
            c = b + (b * 0.18);
        } break;
        default: {
            printf("\t\tEnter Right Choice......\n");
        }
        }
    } break;
    default: {
        printf("\t\tEnter Right Choice......\n");
    }
    }
    return c;
}

// Function for taking details
// of passengers
void details(int k)
{
    int i, a;
    char val[20], gen[6];
    for (i = 1; i <= k; i++) {
        printf("Enter The %dth Passenger Name: ", i);
        fflush(stdin);
        gets(val);
        printf("Enter The %dth Passenger Gender: ", i);
        fflush(stdin);
        gets(gen);
        printf("Enter The %dth Passenger Age: ", i);
        fflush(stdin);
        scanf("%d", &a);

        // Calling add_node() function
        add_node(val, gen, a);
    }
}

// Function to add details in node
// for each passengers
void add_node(char lol[20], char der[6], int b)
{
    Node *newptr = NULL, *ptr;
    newptr = (Node*)malloc(sizeof(Node));
    strcpy(newptr->name, lol);
    strcpy(newptr->gen, der);
    newptr->age = b;
    newptr->link = NULL;
    if (start == NULL)
        start = newptr;
    else {
        ptr = start;
        while (ptr->link != NULL)
            ptr = ptr->link;
        ptr->link = newptr;
    }
}

// Function for chosing seats
int seat(int p)
{
    int i;
    printf("\t           -:SEAT MATRIX:-        \n");
    printf("\t(U)    (M)        (L)    (L)    "
           "    (U)\n\n");
    printf("\t01    02        03\t04        "
           "05\n\n");
    printf("\t06    07        08\t09        "
           "10\n");
    printf("\t11    12        13\t14        "
           "15\n\n");
    printf("\t16    17        18\t19        "
           "20\n");
    printf("\t21    22        23\t24        "
           "25\n\n");
    printf("\t26    27        28\t29        "
           "30\n");
    printf("\t31    32        33\t34        "
           "35\n\n");
    printf("\t36    37        38\t39        "
           "40\n");
    printf("\t41    42        43\t44        "
           "45\n\n");
    printf("\t46    47        48\t49        "
           "50\n");
    printf("\t51    52        53\t54        "
           "55\n\n");
    printf("\t56    57        58\t59        "
           "60\n");
    printf("\tEnter Seat Numbers: \n");
    for (i = 0; i < p; i++)
        scanf("%d", &a[i]);
}

// Function for printing receipt
void bill(int y, int j)
{
    int i;
    Node* ptr = start;
    for (i = 1; i <= j; i++) {
        printf("\t\t\%dst Passenger Name: ", i);
        puts(ptr->name);
        printf("\t\t%dst Passenger Gender: ", i);
        puts(ptr->gen);
        printf("\t\t%dst Passenger Age: %d\n\n", i,
               ptr->age);
        ptr = ptr->link;
    }
    printf("\t\tSource Place: ");
    puts(source);
    printf("\t\tDestination Place: ");
    puts(des);
    printf("\t\tThe Boarding Station: ");
    puts(station);
    printf("\t\tTrain Is: ");
    puts(train);
    printf("\t\tAllocated Class: ");
    puts(cla);
    printf("\t\tBoarding Time: %d:%d\n", time1, time2);
    printf("\t\tTotal Bill Amount: %d\n", y);
    printf("\t\tAllocated Seats Are: \n");
    for (i = 0; i < j; i++) {
        printf("\t\t%d ", a[i]);
    }
    printf("\n");
    printf("\t\t\t\tThank You......\n");
}
```

**输出:**

<video class="wp-video-shortcode" id="video-653921-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210730100702/NEW_RAILWAYS.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210730100702/NEW_RAILWAYS.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210730100702/NEW_RAILWAYS.mp4)</video>