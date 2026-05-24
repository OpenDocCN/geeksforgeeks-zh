# C 中银行账户系统使用文件处理

> 原文:[https://www . geesforgeks . org/bank-account-system-in-c-use-file-handling/](https://www.geeksforgeeks.org/bank-account-system-in-c-using-file-handling/)

本文重点介绍如何使用 [C 语言](https://www.geeksforgeeks.org/c-language-set-1-introduction/)和[在 C](https://www.geeksforgeeks.org/basics-file-handling-c/) 中进行文件处理来创建银行账户系统。

**进场:**
我们来详细讨论一下进场，涵盖所有功能及其详细讲解-

1.  在主功能中创建一个菜单，为菜单创建不同的[功能](https://www.geeksforgeeks.org/functions-in-c/)，使用[开关案例语句](https://www.geeksforgeeks.org/switch-statement-cc/)调用。有四种不同的功能-
    1.  **账户()-** 该功能用于新建账户。
    2.  **转账()-** 该功能用于向账户转账
    3.  **检查余额()-** 该功能用于检查账户中的余额。
    4.  **登录()-** 该功能用于登录账号。
2.  首先，通过调用 account()函数创建我们用户的账户，在创建账户后，使用文件处理函数将所有数据存储到[文件](https://www.geeksforgeeks.org/file-handling-c-classes/)中。
3.  然后用户可以将金额转移给其他用户，为此调用 transfermoney()函数，并在帐户中检查当前余额时调用 checkbalance()函数。

文件处理的概念将用于存储用户的数据，然后从该特定文件中读取所有数据，将结构存储在文件中，因为它们易于[写入和读取](https://www.geeksforgeeks.org/readwrite-structure-file-c/)。

**实现:**
我们来看看程序每个模块的 C 实现，最后把所有模块整合在一起，创建一个完整的工作程序。

**1。创建一个银行账户-**
从用户那里获取所有输入，并为其建立一个结构，将数据存储在一个文件中。

```cpp
// Function to create accounts 
// of users
void account(void)
{
 char password[20];
 int passwordlength, i, seek = 0;
 char ch;
 FILE *fp, *fu;
 struct pass u1;
 struct userpass p1;

 struct userpass u2;

 // Opening file to  
 // write data of a user
 fp = fopen("username.txt", "ab");

 // Inputs
 system("cls");
 printf("\n\n!!!!!CREATE ACCOUNT!!!!!");

 printf("\n\nFIRST NAME..");
 scanf("%s", &u1.fname);

 printf("\n\n\nLAST NAME..");
 scanf("%s", &u1.lname);

 printf("\n\nFATHER's NAME..");
 scanf("%s", &u1.fathname);

 printf("\n\nMOTHER's NAME..");
 scanf("%s", &u1.mothname);

 printf("\n\nADDRESS..");
 scanf("%s", &u1.address);

 printf("\n\nACCOUNT TYPE");
 scanf("%s", &u1.typeaccount);

 printf("\n\nDATE OF BIRTH..");
 printf("\nDATE-");
 scanf("%d", &u1.date);
 printf("\nMONTH-");
 scanf("%d", &u1.month);
 printf("\nYEAR-");
 scanf("%d", &u1.year);

 printf("\n\nADHAR NUMBER");
 scanf("%s", u1.adharnum);

 printf("\n\nPHONE NUMBER");
 scanf("%s", u1.pnumber);

 printf("\n\nUSERNAME.. ");
 scanf("%s", &u1.username);

 printf("\n\nPASSWORD..");

 // Taking password in the  
 // form of stars
 for (i = 0; i < 50; i++)  
 {
   ch = getch();
   if (ch != 13)  
   {
     password[i] = ch;
     ch = '*';
     printf("%c", ch);
   }
   else
     break;
 }

 // Writing to the file
 fwrite(&u1, sizeof(u1), 1, fp);

 // Closing file
 fclose(fp);

 // Calling another function  
 // after successful creation
 // of account
 accountcreated();
}
```

**2。转账-**
取我们要转账的另一个用户的用户名，在文件中打开他的记录，将金额写入文件。

```cpp
// Function to transfer
// money from one user to
// another
void transfermoney(void)
{
 int i, j;
 FILE *fm, *fp;
 struct pass u1;
 struct money m1;
 char usernamet[20];
 char usernamep[20];
 system("cls");

 // Opening file in read mode to  
 // read user's username
 fp = fopen("username.txt", "rb");

 // Creating a another file  
 // to write amount along with
 // username to which amount  
 // is going to be transfered
 fm = fopen("mon.txt", "ab");

 gotoxy(33, 4);
 printf("---- TRANSFER MONEY ----");
 gotoxy(33, 5);
 printf("========================");

 gotoxy(33, 11);
 printf("FROM (your username).. ");
 scanf("%s", &usernamet);

 gotoxy(33, 13);
 printf(" TO (username of person)..");
 scanf("%s", &usernamep);

 // Checking for username if it  
 // is present in file or not
 while (fread(&u1, sizeof(u1), 1, fp))

 {
   if (strcmp(usernamep,
              u1.username) == 0)  
   {
     strcpy(m1.usernameto,
            u1.username);
     strcpy(m1.userpersonfrom,  
            usernamet);
   }
 }
 gotoxy(33, 16);

 // Taking amount input
 printf("ENTER THE AMOUNT TO BE TRANSFERED..");
 scanf("%d", &m1.money1);

 // Writing to the file
 fwrite(&m1, sizeof(m1), 1, fm);

 gotoxy(0, 26);
 printf(
   "--------------------------------------------------"
   "--------------------------------------------");

 gotoxy(0, 28);
 printf(
   "--------------------------------------------------"
   "--------------------------------------------");

 gotoxy(0, 29);
 printf("transfering amount, Please wait..");

 gotoxy(10, 27);
 for (i = 0; i < 70; i++)
 {
   for (j = 0; j < 1200000; j++)  
   {
     j++ ;
     j--;
   }
   printf("*");
 }

 gotoxy(33, 40);
 printf("AMOUNT SUCCESSFULLY TRANSFERED....");
 getch();

 // Close the files
 fclose(fp);
 fclose(fm);

 // Function to return  
 // to the home screen
 display(usernamet);
}
```

**3。检查余额-**
[打开一个文件](https://www.geeksforgeeks.org/basics-file-handling-c/)，其中所有的转账记录都被一一写入和读取，并与函数中传递的用户名匹配，以获取正确的转账记录。

```cpp
// Function to check balance
// in users account
void checkbalance(char username2[])
{
 system("cls");
 FILE* fm;
 struct money m1;
 char ch;
 int i = 1, summoney = 0;

 // Opening amount file record
 fm = fopen("mon.txt", "rb");

 int k = 5, l = 10;
 int m = 30, n = 10;
 int u = 60, v = 10;

 gotoxy(30, 2);
 printf("==== BALANCE DASHBOARD ====");
 gotoxy(30, 3);
 printf("***************************");
 gotoxy(k, l);
 printf("S no.");
 gotoxy(m, n);
 printf("TRANSACTION ID");
 gotoxy(u, v);
 printf("AMOUNT");

 // Reading username to
 // fetch the correct record
 while (fread(&m1, sizeof(m1), 1, fm))  
 {
   if (strcmp(username2,  
              m1.usernameto) == 0)  
   {
     gotoxy(k, ++ l);
     printf("%d", i);
     i++ ;
     gotoxy(m, ++ n);
     printf("%s", m1.userpersonfrom);

     gotoxy(u, ++ v);
     printf("%d", m1.money1);
     // adding and
     // finding total money
     summoney = summoney + m1.money1;
   }
 }

 gotoxy(80, 10);
 printf("TOTAL AMOUNT");

 gotoxy(80, 12);
 printf("%d", summoney);

 getch();

 // Closing file after  
 // reading it
 fclose(fm);
 display(username2);
}
```

**4。登录功能-**
要添加登录功能，我们正在打开文件并匹配用户在注册时提供的用户名，如果用户名正确并与我们文件中的记录匹配，则登录到他。

```cpp
// Login function to check
// the username of the user
void login(void)
{
 system("cls");

 char username[50];
 char password[50];

 int i, j, k;
 char ch;
 FILE *fp, *fu;
 struct pass u1;
 struct userpass u2;

 // Opening file of
 // user data
 fp = fopen("username.txt", "rb");

 if (fp == NULL)  
 {
   printf("ERROR IN OPENING FILE");
 }

 gotoxy(34, 2);
 printf(" ACCOUNT LOGIN ");
 gotoxy(7, 5);
 printf("***********************************************"
        "********************************");

 gotoxy(35, 10);
 printf("==== LOG IN ====");

 // Take input
 gotoxy(35, 12);
 printf("USERNAME.. ");
 scanf("%s", &username);

 gotoxy(35, 14);
 printf("PASSWORD..");
 // Input the password
 for (i = 0; i < 50; i++)  
 {
   ch = getch();
   if (ch != 13)
   {
     password[i] = ch;
     ch = '*';
     printf("%c", ch);
   }

   else
     break;
 }

 // Checking if username
 // exists in the file or not
 while (fread(&u1,  
              sizeof(u1), 1, fp))  
 {
   if (strcmp(username,  
              u1.username) == 0)  
   {
     loginsu();
     display(username);
   }
 }

 // Closing the file
 fclose(fp);
}

// Screen is shown after  
// successful login
void loginsu(void)
{
 int i;
 FILE* fp;
 struct pass u1;
 system("cls");
 printf("Fetching account details.....\n");
 for (i = 0; i < 20000; i++)  
 {
   i++ ;
   i--;
 }
 gotoxy(30, 10);
 printf("LOGIN SUCCESSFUL....");
 gotoxy(0, 20);
 printf("Press enter to continue");

 getch();
}
```

**完整程序-**
以下是银行系统使用文件处理概念的完整 C 程序-

## C

```cpp
// C program to implement
// the above approach
#include <conio.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <windows.h>

// Declaring all the functions
void checkbalance(char*);
void transfermoney(void);
void display(char*);
void person(char*);
void login(void);
void loginsu(void);
void account(void);
void accountcreated(void);
void afterlogin(void);
void logout(void);

// Declaring gotoxy
// function for setting
// cursor position
void gotoxy(int x, int y)
{
    COORD c;
    c.X = x;
    c.Y = y;

    SetConsoleCursorPosition(
        GetStdHandle(STD_OUTPUT_HANDLE), c);
}

// Creating a structure to store
// data of the user
struct pass {
    char username[50];
    int date, month, year;
    char pnumber[15];
    char adharnum[20];
    char fname[20];
    char lname[20];
    char fathname[20];
    char mothname[20];
    char address[50];
    char typeaccount[20];
};

// Structure to keep track
// of amount transfer
struct money {
    char usernameto[50];
    char userpersonfrom[50];
    long int money1;
};

struct userpass {
    char password[50];
};

// Driver Code
int main()
{
    int i, a, b, choice;
    int passwordlength;

    gotoxy(20, 3);

    // Creating a Main
    // menu for the user
    printf("WELCOME TO BANK ACCOUNT SYSTEM\n\n");
    gotoxy(18, 5);

    printf("**********************************");
    gotoxy(25, 7);

    printf("DEVELOPER-Naman kumar");

    gotoxy(20, 10);
    printf("1.... CREATE A BANK ACCOUNT");

    gotoxy(20, 12);
    printf("2.... ALREADY A USER? SIGN IN");
    gotoxy(20, 14);
    printf("3.... EXIT\n\n");

    printf("\n\nENTER YOUR CHOICE..");

    scanf("%d", &choice);

    switch (choice) {
    case 1:
        system("cls");
        printf("\n\n UESERNAME 50 CHARACTERS MAX!!");
        printf("\n\n PASSWORD 50 CHARACTERS MAX!!");
        account();
        break;

    case 2:
        login();
        break;

    case 3:
        exit(0);
        break;

        getch();
    }
}

// Function to create accounts
// of users
void account(void)
{
    char password[20];
    int passwordlength, i, seek = 0;
    char ch;
    FILE *fp, *fu;
    struct pass u1;
    struct userpass p1;

    struct userpass u2;

    // Opening file to
    // write data of a user
    fp = fopen("username.txt", "ab");

    // Inputs
    system("cls");
    printf("\n\n!!!!!CREATE ACCOUNT!!!!!");

    printf("\n\nFIRST NAME..");
    scanf("%s", &u1.fname);

    printf("\n\n\nLAST NAME..");
    scanf("%s", &u1.lname);

    printf("\n\nFATHER's NAME..");
    scanf("%s", &u1.fathname);

    printf("\n\nMOTHER's NAME..");
    scanf("%s", &u1.mothname);

    printf("\n\nADDRESS..");
    scanf("%s", &u1.address);

    printf("\n\nACCOUNT TYPE");
    scanf("%s", &u1.typeaccount);

    printf("\n\nDATE OF BIRTH..");
    printf("\nDATE-");
    scanf("%d", &u1.date);
    printf("\nMONTH-");
    scanf("%d", &u1.month);
    printf("\nYEAR-");
    scanf("%d", &u1.year);

    printf("\n\nADHAR NUMBER");
    scanf("%s", u1.adharnum);

    printf("\n\nPHONE NUMBER");
    scanf("%s", u1.pnumber);

    printf("\n\nUSERNAME.. ");
    scanf("%s", &u1.username);

    printf("\n\nPASSWORD..");

    // Taking password in the form of
    // stars
    for (i = 0; i < 50; i++) {
        ch = getch();
        if (ch != 13) {
            password[i] = ch;
            ch = '*';
            printf("%c", ch);
        }
        else
            break;
    }

    // Writing to the file
    fwrite(&u1, sizeof(u1),
           1, fp);

    // Closing file
    fclose(fp);

    // Calling another function
    // after successful creation
    // of account
    accountcreated();
}

// Successful account creation
void accountcreated(void)
{
    int i;
    char ch;
    system("cls");
    printf(
        "PLEASE WAIT....\n\nYOUR DATA IS PROCESSING....");
    for (i = 0; i < 200000000; i++) {
        i++ ;
        i--;
    }

    gotoxy(30, 10);

    printf("ACCOUNT CREATED SUCCESSFULLY....");
    gotoxy(0, 20);

    printf("Press enter to login");

    getch();
    login();
}

// Login function to check
// the username of the user
void login(void)
{
    system("cls");

    char username[50];
    char password[50];

    int i, j, k;
    char ch;
    FILE *fp, *fu;
    struct pass u1;
    struct userpass u2;

    // Opening file of
    // user data
    fp = fopen("username.txt",
               "rb");

    if (fp == NULL) {
        printf("ERROR IN OPENING FILE");
    }
    gotoxy(34, 2);
    printf(" ACCOUNT LOGIN ");
    gotoxy(7, 5);
    printf("***********************************************"
           "********************************");

    gotoxy(35, 10);
    printf("==== LOG IN ====");

    // Take input
    gotoxy(35, 12);
    printf("USERNAME.. ");
    scanf("%s", &username);

    gotoxy(35, 14);
    printf("PASSWORD..");

    // Input the password
    for (i = 0; i < 50; i++) {
        ch = getch();
        if (ch != 13) {
            password[i] = ch;
            ch = '*';
            printf("%c", ch);
        }

        else
            break;
    }

    // Checking if username
    // exists in the file or not
    while (fread(&u1, sizeof(u1),
                 1, fp)) {
        if (strcmp(username,
                   u1.username)
            == 0) {
            loginsu();
            display(username);
        }
    }

    // Closing the file
    fclose(fp);
}

// Redirect after
// successful login
void loginsu(void)
{
    int i;
    FILE* fp;
    struct pass u1;
    system("cls");
    printf("Fetching account details.....\n");
    for (i = 0; i < 20000; i++) {
        i++ ;
        i--;
    }

    gotoxy(30, 10);
    printf("LOGIN SUCCESSFUL....");
    gotoxy(0, 20);
    printf("Press enter to continue");

    getch();
}

// Display function to show the
// data of the user on screen
void display(char username1[])
{
    system("cls");
    FILE* fp;
    int choice, i;
    fp = fopen("username.txt", "rb");
    struct pass u1;

    if (fp == NULL) {
        printf("error in opening file");
    }

    while (fread(&u1, sizeof(u1),
                 1, fp)) {
        if (strcmp(username1,
                   u1.username)
            == 0) {
            gotoxy(30, 1);
            printf("WELCOME, %s %s",
                   u1.fname, u1.lname);
            gotoxy(28, 2);
            printf("..........................");
            gotoxy(55, 6);
            printf("==== YOUR ACCOUNT INFO ====");
            gotoxy(55, 8);
            printf("***************************");
            gotoxy(55, 10);
            printf("NAME..%s %s", u1.fname,
                   u1.lname);

            gotoxy(55, 12);
            printf("FATHER's NAME..%s %s",
                   u1.fathname,
                   u1.lname);

            gotoxy(55, 14);
            printf("MOTHER's NAME..%s",
                   u1.mothname);

            gotoxy(55, 16);
            printf("ADHAR CARD NUMBER..%s",
                   u1.adharnum);

            gotoxy(55, 18);
            printf("MOBILE NUMBER..%s",
                   u1.pnumber);

            gotoxy(55, 20);
            printf("DATE OF BIRTH.. %d-%d-%d",
                   u1.date, u1.month, u1.year);

            gotoxy(55, 22);
            printf("ADDRESS..%s", u1.address);

            gotoxy(55, 24);
            printf("ACCOUNT TYPE..%s",
                   u1.typeaccount);
        }
    }

    fclose(fp);

    gotoxy(0, 6);

    // Menu to perform different
    // actions by user
    printf(" HOME ");
    gotoxy(0, 7);
    printf("******");
    gotoxy(0, 9);
    printf(" 1....CHECK BALANCE");
    gotoxy(0, 11);
    printf(" 2....TRANSFER MONEY");
    gotoxy(0, 13);
    printf(" 3....LOG OUT\n\n");
    gotoxy(0, 15);
    printf(" 4....EXIT\n\n");

    printf(" ENTER YOUR CHOICES..");
    scanf("%d", &choice);

    switch (choice) {
    case 1:
        checkbalance(username1);
        break;

    case 2:
        transfermoney();
        break;

    case 3:
        logout();
        login();
        break;

    case 4:
        exit(0);
        break;
    }
}

// Function to transfer
// money from one user to
// another
void transfermoney(void)
{
    int i, j;
    FILE *fm, *fp;
    struct pass u1;
    struct money m1;
    char usernamet[20];
    char usernamep[20];
    system("cls");

    // Opening file in read mode to
    // read user's username
    fp = fopen("username.txt", "rb");

    // Creating a another file
    // to write amount along with
    // username to which amount
    // is going to be transfered
    fm = fopen("mon.txt", "ab");

    gotoxy(33, 4);
    printf("---- TRANSFER MONEY ----");
    gotoxy(33, 5);
    printf("========================");

    gotoxy(33, 11);
    printf("FROM (your username).. ");
    scanf("%s", &usernamet);

    gotoxy(33, 13);
    printf(" TO (username of person)..");
    scanf("%s", &usernamep);

    // Checking for username if it
    // is present in file or not
    while (fread(&u1, sizeof(u1),
                 1, fp))

    {
        if (strcmp(usernamep,
                   u1.username)
            == 0) {
            strcpy(m1.usernameto,
                   u1.username);
            strcpy(m1.userpersonfrom,
                   usernamet);
        }
    }
    gotoxy(33, 16);

    // Taking amount input
    printf("ENTER THE AMOUNT TO BE TRANSFERED..");
    scanf("%d", &m1.money1);

    // Writing to the file
    fwrite(&m1, sizeof(m1),
           1, fm);

    gotoxy(0, 26);
    printf(
        "--------------------------------------------------"
        "--------------------------------------------");

    gotoxy(0, 28);
    printf(
        "--------------------------------------------------"
        "--------------------------------------------");

    gotoxy(0, 29);
    printf("transfering amount, Please wait..");

    gotoxy(10, 27);
    for (i = 0; i < 70; i++) {
        for (j = 0; j < 1200000; j++) {
            j++ ;
            j--;
        }
        printf("*");
    }

    gotoxy(33, 40);
    printf("AMOUNT SUCCESSFULLY TRANSFERED....");
    getch();

    // Close the files
    fclose(fp);
    fclose(fm);

    // Function to return
    // to the home screen
    display(usernamet);
}

// Function to check balance
// in users account
void checkbalance(char username2[])
{
    system("cls");
    FILE* fm;
    struct money m1;
    char ch;
    int i = 1, summoney = 0;

    // Opening amount file record
    fm = fopen("mon.txt", "rb");

    int k = 5, l = 10;
    int m = 30, n = 10;
    int u = 60, v = 10;

    gotoxy(30, 2);
    printf("==== BALANCE DASHBOARD ====");
    gotoxy(30, 3);
    printf("***************************");
    gotoxy(k, l);
    printf("S no.");
    gotoxy(m, n);
    printf("TRANSACTION ID");
    gotoxy(u, v);
    printf("AMOUNT");

    // Reading username to
    // fetch the correct record
    while (fread(&m1, sizeof(m1),
                 1, fm)) {
        if (strcmp(username2,
                   m1.usernameto)
            == 0) {
            gotoxy(k, ++ l);
            printf("%d", i);
            i++ ;
            gotoxy(m, ++ n);
            printf("%s", m1.userpersonfrom);

            gotoxy(u, ++ v);
            printf("%d", m1.money1);
            // Adding and
            // finding total money
            summoney = summoney + m1.money1;
        }
    }

    gotoxy(80, 10);
    printf("TOTAL AMOUNT");

    gotoxy(80, 12);
    printf("%d", summoney);

    getch();

    // Closing file after
    // reading it
    fclose(fm);
    display(username2);
}

// Logout function to bring
// user to the login screen
void logout(void)
{
    int i, j;
    system("cls");
    printf("please wait, logging out");

    for (i = 0; i < 10; i++) {
        for (j = 0; j < 25000000; j++) {
            i++ ;
            i--;
        }
        printf(".");
    }

    gotoxy(30, 10);
    printf("Sign out successfully..\n");

    gotoxy(0, 20);
    printf("press any key to continue..");

    getch();
}
```

**输出**

![](img/4e82c49519f74781021d70a3ee57b4b1.png)

程序的输出