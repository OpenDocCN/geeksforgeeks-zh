# C++ :竞争性编程中代码缩短的方法

> 原文:[https://www . geeksforgeeks . org/c-竞争编程中的代码缩短方法/](https://www.geeksforgeeks.org/c-methods-of-code-shortening-in-competitive-programming/)

Shortcode 在竞争性编程中是理想的，因为程序应该尽可能快地编写。因此，有竞争力的程序员通常会为数据类型和代码的其他部分定义较短的名称。
这里具体讨论 C++ 中代码缩短的方法。
**键入名称**
使用命令 *typedef* 可以给数据类型取一个较短的名称。
比如名称 long long 就是 long，那么我们可以定义一个更短的名称 ll:
typedef long long ll；
此后，代码

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
long long a = 123456789;
long long b = 987654321;
cout << a * b << "\n";
```

可以短路如下:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
ll a = 123456789;
ll b = 987654321;
cout << a * b << "\n";
```

命令 typedef 也可以用于更复杂的类型。例如，下面的代码给出了整数向量的名称 vi 和包含两个整数的对的名称 pi，

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
typedef vector<int> vi;
typedef pair<int, int> pi;
```

**宏**
另一种缩短代码的方法是定义**宏**。宏意味着代码中的某些字符串将在编译前被更改。在 C++ 中，宏是使用#define 关键字定义的。
比如我们可以定义如下宏:
#定义 F 第一
#定义 S 第二
#定义 PB push _ back
#定义 MP make_pair
之后，代码
v.push_back(make_pair(y1，x1))；
v.push_back(make_pair(y2，x2))；
int d = v[i]。first+v[i]。第二；
可短路如下
v.PB(MP(y1，x1))；
v.PB(MP(y2，x2))；
int d = v[i]。F+v[i]。s；
宏也可以有参数，这使得缩短循环和其他结构成为可能。比如我们可以定义如下宏:
#定义 REP(i，a，b)为(int I = a；I<= b；i++)
之后，代码
为(int I = 1；I<= n；i++){
搜索(I)；
}
可以缩短为:
REP(i，1，n){
search(I)；
}
**下面给出的模板的一个版本**
这可以在竞争性编程中使用，以实现更快的编码。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <bits/stdc++.h> // Include every standard library
using namespace std;

typedef long long LL;
typedef pair<int, int> pii;
typedef pair<LL, LL> pll;
typedef pair<string, string> pss;
typedef vector<int> vi;
typedef vector<vi> vvi;
typedef vector<pii> vii;
typedef vector<LL> vl;
typedef vector<vl> vvl;

double EPS = 1e-9;
int INF = 1000000005;
long long INFF = 1000000000000000005LL;
double PI = acos(-1);
int dirx[8] = { -1, 0, 0, 1, -1, -1, 1, 1 };
int diry[8] = { 0, 1, -1, 0, -1, 1, -1, 1 };

#ifdef TESTING
#define DEBUG fprintf(stderr, "====TESTING====\n")
#define VALUE(x) cerr << "The value of " << #x << " is " << x << endl
#define debug(...) fprintf(stderr, __VA_ARGS__)
#else
#define DEBUG
#define VALUE(x)
#define debug(...)
#endif

#define FOR(a, b, c) for (int(a) = (b); (a) < (c); ++(a))
#define FORN(a, b, c) for (int(a) = (b); (a) <= (c); ++(a))
#define FORD(a, b, c) for (int(a) = (b); (a) >= (c); --(a))
#define FORSQ(a, b, c) for (int(a) = (b); (a) * (a) <= (c); ++(a))
#define FORC(a, b, c) for (char(a) = (b); (a) <= (c); ++(a))
#define FOREACH(a, b) for (auto&(a) : (b))
#define REP(i, n) FOR(i, 0, n)
#define REPN(i, n) FORN(i, 1, n)
#define MAX(a, b) a = max(a, b)
#define MIN(a, b) a = min(a, b)
#define SQR(x) ((LL)(x) * (x))
#define RESET(a, b) memset(a, b, sizeof(a))
#define fi first
#define se second
#define mp make_pair
#define pb push_back
#define ALL(v) v.begin(), v.end()
#define ALLA(arr, sz) arr, arr + sz
#define SIZE(v) (int)v.size()
#define SORT(v) sort(ALL(v))
#define REVERSE(v) reverse(ALL(v))
#define SORTA(arr, sz) sort(ALLA(arr, sz))
#define REVERSEA(arr, sz) reverse(ALLA(arr, sz))
#define PERMUTE next_permutation
#define TC(t) while (t--)

inline string IntToString(LL a)
{
    char x[100];
    sprintf(x, "%lld", a);
    string s = x;
    return s;
}

inline LL StringToInt(string a)
{
    char x[100];
    LL res;
    strcpy(x, a.c_str());
    sscanf(x, "%lld", &res);
    return res;
}

inline string GetString(void)
{
    char x[1000005];
    scanf("%s", x);
    string s = x;
    return s;
}

inline string uppercase(string s)
{
    int n = SIZE(s);
    REP(i, n)
    if (s[i] >= 'a' && s[i] <= 'z')
        s[i] = s[i] - 'a' + 'A';
    return s;
}

inline string lowercase(string s)
{
    int n = SIZE(s);
    REP(i, n)
    if (s[i] >= 'A' && s[i] <= 'Z')
        s[i] = s[i] - 'A' + 'a';
    return s;
}

inline void OPEN(string s)
{
#ifndef TESTING
    freopen((s + ".in").c_str(), "r", stdin);
    freopen((s + ".out").c_str(), "w", stdout);
#endif
}

// end of Sektor_jr template v2.0.3 (BETA)

int main()
{
    freopen("A.in", "r", stdin);
    freopen("output.txt", "w", stdout);

    int a, b;
    fin >> a >> b;
    fout << a + b << endl;
    return 0;
}
```