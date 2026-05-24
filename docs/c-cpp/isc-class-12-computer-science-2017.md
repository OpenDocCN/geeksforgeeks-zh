# ISC-12 级计算机科学 2017

> 原文:[https://www . geesforgeks . org/isc-class-12-computer-science-2017/](https://www.geeksforgeeks.org/isc-class-12-computer-science-2017/)

**计算机科学(试卷 1:理论)**

**(最高分:70 分)
(允许时间:三小时)**

(考生只允许额外 15 分钟阅读试卷。在此期间，他们不得开始写作。)

回答第一部分(必修)的所有问题和第二部分的六个问题，从 A 部分选择两个问题，从 B 部分选择两个问题，从 C 部分选择两个问题。所有的工作，包括粗活，都应该和答案的其余部分在同一张纸上完成。括号[ ]中给出了问题或部分问题的预期标记。

**第一部分(20 分)**

回答所有问题。
在回答本部分的问题时，在需要的地方简要说明你的工作和推理。

**1(a)陈述以下命题所代表的定律，借助真值表证明:P V P = P [1]**
定律:[幂等定律](https://www.geeksforgeeks.org/mathematics-properties-boolean-algebra/)。它指出 P = P。

```cpp
P   P   P V P
0   0     0
1   1     1

```

**(b)陈述二元性原则。[1]**
对偶原理指出，对于每个布尔方程，存在另一个与原始方程对偶的方程。为了实现这一点，AND 的(。)被转换成 OR 的(+)和反过来，0 的转换成 l 的，反过来，但是补语保持不变。

**(c)用德·摩根定律求下列布尔表达式的补码:F(a，b，c) = (b' + c) + a [1]**
补码:F(a，b，c ) =(b' + c ) + a
= (b' + c】。a'
= b。c。a' = b.c '。a′

**(d)绘制 2 输入 [XNOR 门的逻辑图和真值表。](https://www.geeksforgeeks.org/xnor-two-numbers/)【1】**

```cpp
A    B      X
0    0      1
0    1      0
1    0      0
1    1      1
```

**(e) If (P' = > Q)然后写出其:【1】**
a .逆:(P = > Q) OR P' + Q'
b .逆:(Q = > P) OR Q' + P '

**2(a)什么是接口？和一个班有什么不同？【2】**
(a)接口是一种非原语数据类型，有静态和最终数据成员以及函数原型(即函数未定义)
**接口和类的区别:**接口支持多重继承，而一个类不支持多重继承。

**(b)将以下中缀表达式转换为后缀形式:P * Q / R + (S + T) [2]**

```cpp
(b) Infix to postfix : 
    P*Q/R+(S+T)
  = P*Q/R+ ST+
  = PQ* /R + ST+
  = PQ*R/ + ST+
  = PQ*R/ST++
```

**(c)矩阵 P[15][10]被存储，每个元素需要 8 字节的存储。如果 P[0][0]的基址是 1400，当矩阵存储在行主方向时，确定 P[10][7]的地址。[2]**
(c)行大智慧:P[I][j]= BA+W[(I-lr)*列+(j-LC]
= 1400+8[(10-0)* 10+(7-0)]
= 1400+856
P[10][7]= 2256

**(d) (i)以下代码段的最坏情况复杂度是多少:[2]**

```cpp
for (int x = 1; x <= a; x++) {
    statements;
}
for (int y = 1; y <= b; y++) {
    for (int z = 1; z <= c; z++) {
        statements;
    }
}
```

= O(a) + O(b x c)
= O(a + bc)

**(ii)如果三个循环都去了 N 而不是 a、b、c，复杂度会如何变化？**
= O(N)+O(N<sup>2</sup>)
= O(N<sup>2</sup>，取优势项。

**(e)区分类的构造函数和方法。[2]**
(e)构造函数与类同名，而方法与类同名。在构造函数中没有返回类型，甚至没有 void，因为在方法中它可以返回值

**3。下面的函数 magicfun()是某个类的一部分。当 n=7 和 n=10 时，magicfun()函数将返回什么？显示试运行/工作状态:[5]**

```cpp
int magicfun(int n)
{
    if (n = = 0)
        return 0;
    else
        return magicfun(n / 2) * 10 + (n % 2);
}
```

**(i)当 n = 7 时**

```cpp
OUTPUT : magicfun(7)
            magicfun(3) * 10 + 1
               magicfun(1) *10 + 1
                  magic fun(0) *10 + 1  = 111
```

**(ii)当 n = 10 时**

```cpp
OUTPUT : magicfun(10)
           magicfun(5) * 10 + 0
               magicfun(2) *10 + 1
                  magicfun(1) *10 + 0
                     magicfun(0) *10 + 1  = 1010
```

**第二部分(50 分)**

回答六个问题，从 A 部分选择两个问题，从 B 部分选择两个问题，从 c 部分选择两个问题。

**A 节**(回答任意两个问题)

**4(a)给定布尔函数 F(A，B，C，D) = R (2，3，4，5，6，7，8，10，11)。
(i)使用 4 变量[卡诺图](https://www.geeksforgeeks.org/k-mapkarnaugh-map/)缩小上述表达式，显示各种组(即八进制、四进制和成对)。[4]**

Quad 1: (M2+ M3+ M10，m11x)= b ' c
quad 2:(M4，M5，M6，M7 ) = A'B
Quad 3: (M8，M10)= ab ' de ' T2 '，然后 F(A，b，c，D) = B'C + A'B + AB '

**(ii)画出简化表达式的逻辑门图。假设变量及其补数可作为输入。[1]**
**(b)给定布尔函数 F(P，Q，R，S) = R (0，1，2，4，5，6，8，10)。**

四元 1 : (M0、M1、M4、M5) = Q + S
四元 2 : (M0、M2、M4、M6) = P + S
四元 3 : (M0、M2、M8、M10) = P + R
因此 F(P、Q、R、S) = (P + R)。(P + S)。(Q + S)

**(i)通过使用 4 变量卡诺图减少上述表达式，显示各种组(即八进制、四进制和成对)。【4】**
**(二)画出简化表达式的逻辑门图。假设变量及其补数可作为输入。[1]**

**5(a)一所学校打算根据以下标准选择校际征文比赛的候选人:
该学生参加过较早的比赛，非常有创造力。
或
学生很有创造力，一般意识很好，但之前没有参加过任何比赛。
或
该学生具有出色的一般意识，并在内部竞赛中获奖。
输入为:
INPUTS
A 之前参加过一次比赛
B 很有创意
C 在一次内部比赛中获奖
D 具有出色的一般意识**

**输出:X【1 表示是，0 表示不是所有情况】
绘制上面给出的输入和输出的真值表，写出 X 的 POS 表达式(A，B，C，D)。【5】**

```cpp
A   B    C   D    X (OUTPUT)
0   0    0   0    0
0   0    0   1    0
0   0    1   0    0
0   0    1   1    1
0   1    0   0    0
0   1    0   1    1
0   1    1   0    0
0   1    1   1    1
1   0    0   0    0
1   0    0   1    0
1   0    1   0    0
1   0    1   1    1
1   1    0   0    1
1   1    0   1    1
1   1    1   0    1
1   1    1   1    1

```

POS 表达式:X (A，B，C，D) = R (0，1，2，4，6，8，9，10)

**(b)说明[半加法器](https://www.geeksforgeeks.org/digital-electronics-half-adder/)的应用。画出半加法器的真值表和电路图。[3]
半加法器的应用是执行两位的部分相加。
半加法器真值表:**

```cpp
A   B    Sum  CARRY
0   0    0      0
0   1    1      0
1   0    1      0
1   1    0      1
```

**(c)将以下布尔表达式转换为其[规范 POS 形式](https://www.geeksforgeeks.org/digital-logic-canonical-standard-form/) : F(A，B，C)=(b+ C’)(A’+B)[2]**

转换为规范形式:F(A，B，C)
=(b+ C’)。(A'+ B)
= (B + C'+ 0)。(A'+ B + O)
= (B+C'+(A.A ')。(A '+b+(C . C ')[xx ' = 0]
=(A+b+ C ')。(A'+B+C ')。(A'+B+C)

**6(a)什么是[复用器](https://www.geeksforgeeks.org/multiplexers-digital-electronics/)？与[解码器](https://www.geeksforgeeks.org/digital-logic-binary-decoder/)有何不同？绘制 8:1 多路复用器的电路图。[5]**
(a)多路复用器是输入并行数据并输出一个串行数据的组合电路，其中解码器是输入 n 条线并输出 2n 条或更少的线的组合电路。
8:1 多路复用器的电路图:

**(b)用布尔定律证明布尔表达式。此外，提及每一步使用的法律。F =(x '+z)+[(y '+z)[(x '+y)]' = 1[3]**
F =(x '+z)+[(y '+z)。(x '+y)]= 1
=(x '+z)+(y '+z)'+(x '+y)'**(德摩根定律)**
= x '+z+y . z '+xy '
=(x '+x)(x '+y ')+(z+z ')(z+y)= x '+y '+z+y(分配律)
= 1 **(as y+y'=1)(恒等式定律)**

**(c)定义最大术语和最小术语。求最大项和最小项当:P = 0，Q = 1，R = 1 和 S = 0 [2]**
最大项:它是它所有文字的和。
Minterms:它是它所有文字的乘积。
当 P=0，Q=1，R=1，S=0 时
最大项= P + Q' + R' + S
最小项= P' Q R S '

**B 节**
回答任意两个问题。每个程序的编写都应该清楚地描述问题的逻辑。这可以通过在程序中使用助记符名称和注释来实现。(流程图和算法不是必需的。)程序必须用 Java 编写。

**7。定义了一个类佩林来检查正数是否是回文数。
原数与其反数相同时，数字‘N’为回文。
该类的部分成员如下所示:【10】
类名:佩林
数据成员/实例变量:
num:存储数字的整数
revnum:存储数字反转的整数
方法/成员函数:
P a l i n():用
合法初始值初始化数据成员的构造函数
void accept():接受数字
int reverse(int y) :使用递归技术反转参数化参数“y”并将其存储在“revnum”中
void check():通过调用函数 reverse()检查该数字是否为回文，并使用适当的消息显示结果
指定给出构造函数详细信息的类 Palin()，void accept()，int reverse()和 void check()。 定义 main()函数来创建对象，并相应地调用函数来启用任务。**

```cpp
import java.util.*;
public class Palin {
    int num, revnum;
    static Scanner x = new Scanner(System.in);
    Palin()
        num = 0;
    revnum = 0;
}
void accept()
    System.out.println("Enter a number");
num = x.nextlntO;
}
int reverse(int y)
{
    if (y > 0)
        revnum = revnum * 10 + y % 10;
    return reverse(y / 10);
}
else return revnum;
}
void check()
{
    int p = num;
    if (num == reverse(p))
        System.out.println("palindrome");
    else
        System.out.println("not a palindrome");
}
static void main()
{
    Palin obj = new Palin();
    obj.accept();
    obj.check();
}
```

**8。已经定义了一个类加法器来添加任意两个可接受的时间。[10]
示例:时间 A–6 小时 35 分钟
时间 B–7 小时 45 分钟
它们的总和为–14 小时 20 分钟(其中 60 分钟= 1 小时)
该类成员的详细信息如下:
类名:加法器
数据成员/实例变量:
a[ ]:保存两个元素的整数数组(小时和
分钟)
成员函数/方法:
加法器( ) :将 0 赋给数组元素的构造函数
void readtime():输入数组元素
void addtime(加法器 X，加法器 Y):将两个参数化对象 X 和 Y 的时间相加，并将总和存储在当前调用对象中
void disptime():用适当的消息显示数组元素(即小时=和分钟= )
指定给出构造函数详细信息的类 Adder()、void readtime()、void addtime(加法器)和 void disptime()。 定义 main()函数来创建对象，并相应地调用函数来启用任务。**

```cpp
import java.util.*;
public class Adder {
    int a[] = new int[2];
    static Scanner x = new Scanner(System.in);
    Adder()
    {
        a[0] = 0;
        a[1] = 0;
    }
    void readtime()
        System.out.println("Enter hours and minutes");
    a[0] = x.nextInt();
    a[1] = x.nextInt();
    void disptime()
    {
        System.out.println("Hours=" + a[0]);
        System.out.println("Minutes=" + a[1]);
    }
    void addtime(Adder X, Adder Y)
    {
        a[1] = X.a[1] + Y.a[1];
        a[0] = a[1] / 60;
        a[1] = a[1] % 60;
        a[0] += X.a[0] + Y.a[0];
    }
    static void main()
    {
        Adder a = new Adder();
        Adder b = new Adder();
        Adder c = new Adder();
        a.readtimeO;
        b.readtimeO;
        c.addtime(a, b);
        c.disptime();
```

**9。定义了一个类 SwapSort 来对单词输入执行与字符串相关的操作。[10]
类的一些成员如下:**

**类名:SwapSort
数据成员/实例变量:
wrd:存储一个单词
len:整数存储单词
的长度 swapwrd:存储交换的单词
sortwrd:存储排序后的单词
成员函数/方法:
SwapSort():默认构造函数用合法的初始值初始化数据成员
void readword() :在 UPPER CASE 中接受一个单词
void swapchar( ):在‘wrd’中交换/交换单词的第一个和最后一个字符，并将新单词存储在‘swapwrd’
void sortword():按字母顺序对原始单词的字符进行排序，并将其存储在‘sort wrd’
void display():显示原始单词、交换的单词和排序的单词
指定类别 SwapSort，给出构造函数的详细信息()、void readword()、void swapchar()、void sort word()和 void 定义 main()函数来创建对象，并相应地调用函数来启用任务。**

```cpp
import java.util.*;
public class SwapSort {
    String wrd, swapwrd, sortwrd;
    int len;
    static Scanner x = new Scanner(System.in);
    SwapSort()
    {
        swapvvrd = "";
        sortwrd = "";
    }
    void readword()
    {

        System.out.println("Enter word in Upper case");
        wrd = x.nextO;
        len = wrd.lengthO;
    }
    void swapchar()
        swapwrd = wrd.charAt(len - 1) + wrd.sub strin g(1, len - 1)
                  + wrd.charAt(0);
}
void sortword()
{
    char c;
    for (int i = 65; i <= 90; i++)
        for (int j = 0; j < len; j++)
            c = wrd.charAt(j);
    if (c == i)
        sortwrd += c;
}
}
}
void display()
{
    System.out.println("Original word = " + wrd);
    System.out.println("Swapped word = " + swapwrd);
    System.out.println(" Sorted word = " + sortwrd);
}
static void main()
    SwapSort x = new SwapSort();
x.readwordO;
x.swapchar();
x.sortword();
x.display();
}
```

**C 区**
回答任意两个问题。

每个程序的编写都应该清楚地描述问题的逻辑。这可以通过使用程序中的注释和算法的助记名或伪代码来实现。程序必须用 Java 编写，算法必须用通用/标准形式编写，无论在哪里需要/指定。(不需要流程图。)

**10。超级产品被定义为存储批发商向零售商销售的产品的详细信息。定义一个子类“销售额”，以计算零售商支付的总额，包括或不包括罚款和服务税。[5]
两个类的部分成员给出如下:
类名:Product
数据成员/实例变量:
名称:存储产品名称
代码:整数存储产品代码
金额:存储产品销售总额(以小数表示)
成员函数/方法:
产品(String n，int c，double p):参数化构造函数分配数据成员名称=n， code=c 和 amount = p
void show():显示数据成员的详细信息
类名称:Sales
数据成员/实例变量:
day:存储支付销售金额
tax 所用的天数:存储服务税(以小数表示)
total:存储总金额(以小数表示)
成员函数/方法:
Sales(…):参数化构造函数为两个类的数据成员赋值
void compute() :计算服务税@实际销售金额的 12 4%仅当零售商支付给批发商的金额超过 30 天时才计算罚款@实际销售金额的 2 5%计算零售商支付的总金额为(实际销售金额+服务税+罚款)
void show():显示超级类的数据成员和总金额
假设超级类产品已经定义。 使用继承的概念，指定 Sales 类，给出构造函数(…)、void compute()和 void show()的细节。
超级类、主函数、算法不用写。**

```cpp
public class Sales extends Product {
    int day;
    double tax, totamt;
    Sales(String n, int a, double b, int d)
    {
        super(n, a, b);
        day = d;
    }
    void compute()
    {
        double f = 0.0;
        tax = (12.4 / 100) * amount;
        if (day > 27)
            f = (2.5 / 100) * amount;
        totamt = amount + tax + f;
        void show()
        {
            super.show();
            System.out.println("No of days=" + day);
            System.out.println("Sales Tax=" + tax);
            System.out.println("Total Amount=" + totamt);
```

**11 时。队列是一个最多可以容纳 100 个整数的实体。队列允许用户从后面添加整数，从前面移除整数。用以下细节定义一个类 Queue:[5]
类名:Queue
数据成员/实例变量:
Que[ ]:保存整数元素的数组
大小:存储数组的大小
前置:指向前置的索引
后置:指向后置的索引
成员函数:
Queue (int mm)构造函数初始化数据
大小= mm，前置= 0， rear = 0
void addele(int v):如果可能，从后面添加整数
否则显示消息“Overflow”
int delele():如果存在，从前面返回元素，否则显示消息“Underflow”并返回-9999
void display():显示数组元素
指定类 Queue，仅给出函数 void addele(int)和 int delele()的详细信息。 假设已经定义了其他函数。主要功能和算法不需要写。**

```cpp
public class Queue {
    int Quen = new int[100];
    int max, f, r;
    void addele(int v) if (r < max - 1)
        Que[+ - Fr]
        = v;
    else System.out.println("Overflow");
}
int delele() if (f != r) return Que[++ f];
else return -9999;
```

**12(a)链表由 Node 类的对象组成。
节点的类结构如下:
类节点
{
int num；
下一个节点；
}
编写一个算法或方法，对现有链表中只包含奇数的节点进行计数，并返回计数。方法声明如下:
int count odd(Node startPtr)[2]**

(a) **算法:**
步骤 1。开始
第二步。将临时指针设置到第一个节点
步骤 3。重复步骤 4 和 5，直到指针到达 null。返回计数步骤 4。检查奇数并增加计数器。
第五步。将指针移动到下一个节点
步骤 6。结束
**方法**:

```cpp
int CountOdd(Node startPtr)
{
    int c = 0;
    Node temp = new Node(startPtr);
    while (temp != null) {
        if (temp.num % 2 != 0)
            c++ ;
        temp = temp.next;
        return c;
```

**(b)从下面给出的[二叉树](https://www.geeksforgeeks.org/binary-tree-set-1-introduction/)的图中回答以下问题:
(i)写出上述树结构的后序遍历。[1]**
WFYNRZDGM
**(ii)如果根处于 0(零)级别，则说明节点 N 和 R 的级别号。【1】**
N = 1 的级别和 R = 3 的级别
**(三)列出右子树的内部节点。[1]**
G 和 Z