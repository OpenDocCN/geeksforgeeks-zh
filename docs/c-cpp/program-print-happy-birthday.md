# 程序打印生日快乐

> 原文:[https://www.geeksforgeeks.org/program-print-happy-birthday/](https://www.geeksforgeeks.org/program-print-happy-birthday/)

做了很多编程算法之后，轮到祝程序员朋友了。把这个代码发给你的程序员朋友，在他/她的**生日**的时候给他/她一个惊喜！。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to print Happy Birthday
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // Print first row
    char ch = '@';
    for(int i=1; i<=34; i++)
    {
        if (i==5||i==7||i==10||i==11||i==14||i==15||
           i==16||i==18||i==19||i==20||i==22||i==24)
            cout << ch ;
        else cout << " " ;

    }

    // Print second row
    cout << endl;
    for(int i=1; i<=34; i++)
    {
        if(i==5||i==7||i==9||i==12||i==14||i==16
                ||i==18||i==20||i==22||i==24)
            cout << ch ;
        else cout << " " ;

    }

    // Print third row
    cout << endl;
    for (int i=1; i<=34; i++)
    {
        if (i==5||i==6||i==7||i==9||i==10||i==11||i==12||
            i==14||i==15||i==16||i==18||i==19||i==20||
            i==22||i==23||i==24)
            cout << ch ;
        else cout << " " ;

    }

    // Print fourth row
    cout << endl;
    for (int i=1; i<=34; i++)
    {
        if (i==5||i==7||i==9||i==12||i==14||i==18||i==23)
            cout << ch ;
        else cout << " " ;

    }

    // Print fifth row
    cout << endl;
    for (int i=1; i<=34; i++)
    {
        if (i==5||i==7||i==9||i==12||i==14||i==18||i==23)
            cout << ch ;
        else cout << " " ;

    }

    // Happy is printed, now print
    //  birthday row by row
    cout << endl;
    cout << endl;
    cout << endl;
    for (int i=1; i<=34; i++)
    {
        if (i==2||i==3||i==4||i==6||i==7||i==8||i==10||
            i==11||i==14||i==15||i==16||i==18||i==20||
            i==22||i==23||i==27||i==28||i==31||i==33)
            cout << ch ;
        else cout << " " ;
    }
    cout << endl;
    for(int i=1; i<=34; i++)
    {
        if (i==2||i==4||i==7||i==10||i==12||
            i==15||i==18||i==20||i==22||i==24||
            i==26||i==29||i==31||i==33)
            cout << ch ;
        else cout << " " ;
    }
    cout << endl;
    for (int i=1; i<=34; i++)
    {
        if (i==2||i==3||i==4||i==7||i==10||i==11||
            i==15||i==18||i==19||i==20||i==22||
            i==24||i==26||i==27||i==28||i==29||i==31
            ||i==32||i==33)
            cout << ch ;
        else cout << " " ;
    }
    cout << endl;
    for (int i=1; i<=34; i++)
    {
        if (i==2||i==4||i==7||i==10||i==12||
            i==15||i==18||i==20||i==22||
            i==24||i==26||i==29||i==32)
            cout << ch ;
        else cout << " " ;
    }
    cout << endl;
    for (int i=1; i<=34; i++)
    {
        if (i==2||i==3||i==4||i==6||i==7||i==8||
            i==10||i==12||i==15||i==18||i==20||
            i==23||i==22||i==26||i==29||i==32)
            cout << ch ;
        else cout << " " ;
    }
    cout << endl;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to print
// Happy Birthday

class GFG
{
public static void main(String arg[])
{
    // Print first row
    char ch = '@';
    for(int i=1; i<=34; i++)
    {
        if (i==5||i==7||i==10||
            i==11||i==14||i==15||
            i==16||i==18||i==19||
            i==20||i==22||i==24)
            System.out.print(ch);
        else System.out.print(" ");

    }

    // Print second row
    System.out.println();
    for(int i=1; i<=34; i++)
    {
        if(i==5||i==7||i==9||i==12||i==14||i==16
                ||i==18||i==20||i==22||i==24)
            System.out.print(ch);
        else System.out.print(" ");

    }

    // Print third row
    System.out.println();
    for (int i=1; i<=34; i++)
    {
        if (i==5||i==6||i==7||i==9||
            i==10||i==11||i==12||
            i==14||i==15||i==16||
            i==18||i==19||i==20||
            i==22||i==23||i==24)
            System.out.print(ch) ;
        else System.out.print(" ");

    }

    // Print fourth row
    System.out.println();
    for (int i=1; i<=34; i++)
    {
        if (i==5||i==7||i==9||i==12||
            i==14||i==18||i==23)
            System.out.print(ch);
        else System.out.print(" ");

    }

    // Print fifth row
    System.out.println();
    for (int i=1; i<=34; i++)
    {
        if (i==5||i==7||i==9||i==12||
            i==14||i==18||i==23)
            System.out.print(ch);
        else System.out.print(" ");

    }

    // Happy is printed, now print
    // birthday row by row
    System.out.println();
    System.out.println();
    System.out.println();
    for (int i=1; i<=34; i++)
    {
        if (i==2||i==3||i==4||i==6||
            i==7||i==8||i==10||
            i==11||i==14||i==15||
            i==16||i==18||i==20||
            i==22||i==23||i==27||
            i==28||i==31||i==33)
            System.out.print(ch);
        else System.out.print(" ");
    }

    System.out.println();
    for(int i=1; i<=34; i++)
    {
        if (i==2||i==4||i==7||i==10||i==12||
            i==15||i==18||i==20||i==22||i==24||
            i==26||i==29||i==31||i==33)
            System.out.print(ch);
        else System.out.print(" ");
    }

    System.out.println();
    for (int i=1; i<=34; i++)
    {
        if (i==2||i==3||i==4||i==7||
            i==10||i==11||
            i==15||i==18||i==19||
            i==20||i==22||
            i==24||i==26||i==27||
            i==28||i==29||i==31
            ||i==32||i==33)
            System.out.print(ch);
        else System.out.print(" ");
    }

    System.out.println();
    for (int i=1; i<=34; i++)
    {
        if (i==2||i==4||i==7||i==10||i==12||
            i==15||i==18||i==20||i==22||
            i==24||i==26||i==29||i==32)
            System.out.print(ch);
        else System.out.print(" ");
    }

    System.out.println();
    for (int i=1; i<=34; i++)
    {
        if (i==2||i==3||i==4||i==6||i==7||i==8||
            i==10||i==12||i==15||i==18||i==20||
            i==23||i==22||i==26||i==29||i==32)
            System.out.print(ch);
        else System.out.print(" ");
    }

    System.out.println();
}
}

// This code is contributed
// by Anant Agarwal.
```

## 蟒蛇 3

```cpp
# Python program to 
# print Happy Birthday
# Print first row

ch = '@'
for i in range(1,(34+1)):

    if (i==5 or i==7 or i==10 or
        i==11 or i==14 or i==15 or
        i==16 or i==18 or i==19 or
        i==20 or i==22 or i==24):
        print(ch,end="")
    else:
        print(" ", end="")

# Print second row
print()
for i in range(1,(34+1)):

    if(i==5 or i==7 or i==9 or
       i==12 or i==14 or i==16
        or i==18 or i==20 or
       i==22 or i==24):
        print(ch,end="")
    else:
        print(" ", end="")

# Print third row
print()
for i in range(1,(34+1)):

    if (i==5 or i==6 or i==7 or
        i==9 or i==10 or i==11 or i==12 or
        i==14 or i==15 or i==16 or
        i==18 or i==19 or i==20 or
        i==22 or i==23 or i==24):
        print(ch,end="")
    else:
        print(" ", end="")

# Print fourth row
print()
for i in range(1,(34+1)):

    if (i==5 or i==7 or i==9 or i==12
        or i==14 or i==18 or i==23):
        print(ch,end="")
    else:
        print(" ", end="")

# Print fifth row
print()
for i in range(1,(34+1)):

    if (i==5 or i==7 or i==9 or
        i==12 or i==14 or i==18 or i==23):
        print(ch,end="")
    else:
        print(" ",end="")

# Happy is printed, 
# now print birthday row by row
print()
print()
print()
for i in range(1,(34+1)):

    if (i==2 or i==3 or i==4 or
        i==6 or i==7 or i==8 or i==10 or
        i==11 or i==14 or i==15 or
        i==16 or i==18 or i==20 or
        i==22 or i==23 or i==27 or
        i==28 or i==31 or i==33):
        print(ch,end="")
    else:
        print(" ",end="")

print()
for i in range(1,(34+1)):

    if (i==2 or i==4 or i==7 or i==10 or i==12 or
        i==15 or i==18 or i==20 or i==22 or i==24 or
        i==26 or i==29 or i==31 or i==33):
        print(ch,end="")
    else:
        print(" ",end="")

print()
for i in range(1,(34+1)):

    if (i==2 or i==3 or i==4 or
        i==7 or i==10 or i==11 or
        i==15 or i==18 or i==19 or
        i==20 or i==22 or
        i==24 or i==26 or i==27 or
        i==28 or i==29 or i==31
         or i==32 or i==33):
        print(ch,end="")
    else:
        print(" ",end="")

print()
for i in range(1,(34+1)):

    if (i==2 or i==4 or i==7 or i==10 or i==12 or
        i==15 or i==18 or i==20 or i==22 or
        i==24 or i==26 or i==29 or i==32):
        print(ch,end="")
    else:
        print(" ", end="")

print()
for i in range(1,(34+1)):

    if (i==2 or i==3 or i==4 or
        i==6 or i==7 or i==8 or
        i==10 or i==12 or i==15 or
        i==18 or i==20 or
        i==23 or i==22 or i==26 or
        i==29 or i==32):
        print(ch,end="")
    else:
        print(" ", end="")

print()

# This code is contributed 
# by Anant Agarwal.
```

## C#

```cpp
// C# program to print Happy Birthday
using System; 

class GFG 
{ 
    // Print first row 
    public static void Main()
    {
        char ch = '@'; 
        for(int i=1; i<=34; i++) 
        { 
            if (i==5||i==7||i==10||i==11||i==14||i==15|| 
               i==16||i==18||i==19||i==20||i==22||i==24) 
                Console.Write(ch) ; 
            else Console.Write(" ") ; 

        } 

        // Print second row 
        Console.Write("\n"); 
        for(int i=1; i<=34; i++) 
        { 
            if(i==5||i==7||i==9||i==12||i==14||i==16 
                    ||i==18||i==20||i==22||i==24) 
                Console.Write(ch) ; 
            else Console.Write(" ") ; 

        } 

        // Print third row 
        Console.Write("\n"); 
        for (int i=1; i<=34; i++) 
        { 
            if (i==5||i==6||i==7||i==9||i==10||i==11||i==12|| 
                i==14||i==15||i==16||i==18||i==19||i==20|| 
                i==22||i==23||i==24) 
                Console.Write(ch) ; 
            else Console.Write(" ") ; 

        } 

        // Print fourth row 
        Console.Write("\n"); 
        for (int i=1; i<=34; i++) 
        { 
            if (i==5||i==7||i==9||i==12||i==14||i==18||i==23) 
                Console.Write(ch) ; 
            else Console.Write(" ") ; 

        } 

        // Print fifth row 
        Console.Write("\n"); 
        for (int i=1; i<=34; i++) 
        { 
            if (i==5||i==7||i==9||i==12||i==14||i==18||i==23) 
                Console.Write(ch) ; 
            else Console.Write(" ") ; 

        } 

        // Happy is printed, now print 
        //  birthday row by row 
        Console.Write("\n"); 
        Console.Write("\n"); 
        Console.Write("\n"); 
        for (int i=1; i<=34; i++) 
        { 
            if (i==2||i==3||i==4||i==6||i==7||i==8||i==10|| 
                i==11||i==14||i==15||i==16||i==18||i==20|| 
                i==22||i==23||i==27||i==28||i==31||i==33) 
                Console.Write(ch) ; 
            else Console.Write(" ") ; 
        } 
        Console.Write("\n"); 
        for(int i=1; i<=34; i++) 
        { 
            if (i==2||i==4||i==7||i==10||i==12|| 
                i==15||i==18||i==20||i==22||i==24|| 
                i==26||i==29||i==31||i==33) 
                Console.Write(ch) ; 
            else Console.Write(" ") ; 
        } 
        Console.Write("\n"); 
        for (int i=1; i<=34; i++) 
        { 
            if (i==2||i==3||i==4||i==7||i==10||i==11|| 
                i==15||i==18||i==19||i==20||i==22|| 
                i==24||i==26||i==27||i==28||i==29||i==31 
                ||i==32||i==33) 
                Console.Write(ch) ; 
            else Console.Write(" "); 
        } 
        Console.Write("\n"); 
        for (int i=1; i<=34; i++) 
        { 
            if (i==2||i==4||i==7||i==10||i==12|| 
                i==15||i==18||i==20||i==22|| 
                i==24||i==26||i==29||i==32) 
                Console.Write(ch) ; 
            else Console.Write(" ") ; 
        } 
        Console.Write("\n"); 
        for (int i=1; i<=34; i++) 
        { 
            if (i==2||i==3||i==4||i==6||i==7||i==8|| 
                i==10||i==12||i==15||i==18||i==20|| 
                i==23||i==22||i==26||i==29||i==32) 
                Console.Write(ch) ; 
            else Console.Write(" ") ; 
        } 
        Console.Write("\n");
    }
    //This code is contributed by DrRoot_
}
```

Output :

```cpp
    @ @  @@  @@@ @@@ @ @          
    @ @ @  @ @ @ @ @ @ @          
    @@@ @@@@ @@@ @@@ @@@          
    @ @ @  @ @   @    @           
    @ @ @  @ @   @    @           

 @@@ @@@ @@  @@@ @ @ @@   @@  @ @ 
 @ @  @  @ @  @  @ @ @ @ @  @ @ @ 
 @@@  @  @@   @  @@@ @ @ @@@@ @@@ 
 @ @  @  @ @  @  @ @ @ @ @  @  @  
 @@@ @@@ @ @  @  @ @ @@  @  @  @  

```

本文由曼吉特·辛格(HBD)供稿。N20) 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。