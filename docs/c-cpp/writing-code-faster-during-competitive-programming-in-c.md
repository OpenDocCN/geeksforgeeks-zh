# 在 C++ 中进行竞争性编程时更快地编写代码

> 原文:[https://www . geesforgeks . org/writing-code-fast-in-competition-c/](https://www.geeksforgeeks.org/writing-code-faster-during-competitive-programming-in-c/)

本文重点介绍如何实现您的解决方案，并在进行竞争性编程时快速实现它们。

**设置**请参考[设置 C++ 竞争性编程环境](https://www.geeksforgeeks.org/setting-up-a-c-competitive-programming-environment/)

**Snippet**Snippet 是一个可重复使用的小部分源代码的编程术语。许多现代文本编辑器，如崇高，提供了一种功能，只需写一个关键词，就可以自动编写预定义的片段。人们可以通过使用 Snippets 来加速它们的实现。因此，如果你需要做一个 BFS 或 DFS(或任何其他代码)，你只需要按“关键字+标签”来获得它的代码。

**如何添加片段**在崇高文本中添加片段非常简单。只需导航到工具>开发人员>新片段。

> <snippet><内容> <！[CDATA[</snippet>
> 
> //在此输入您的代码
> 
> ]]>
> < tabTrigger >在此输入关键字</tab trigger>
> </摘录>

将它用作代码段的基础模板，并通过替换注释和触发器关键字来粘贴要在代码段中使用的代码。

**宏**
它们是一种给通常写起来较长的东西分配较短符号的方法。
可以使用#define 轻松编写。

**示例 1:**
使用宏之前:

```cpp
long long int a;
vector<long long int> v;
map<long long int, long long int> mp;
```

使用宏后:

```cpp
// ll can be used instead of typing long long int
#define ll long long int

ll a;
vector<ll> v;
map<ll, ll> mp;
```

**示例 2:**
使用宏之前:

```cpp
for (int i = 0; i < N; i++)
    cin >> a[i];

for (int i = 0; i < N; i++) {
    for (int j = 0; j < M; j++) {
        cout << m[i][j] << endl;
    }
}
```

使用宏后:

```cpp
// Use this macro instead of typing the whole
// for-loop syntax
#define FOR(a, c) for (int(a) = 0; (a) < (c); (a)++)

FOR(i, N)
cin >> a[i];

FOR(i, N)
{
    FOR(j, M)
    {
        cout << m[i][j] << endl;
    }
}
```

**例 3:**

```cpp
vector v;

for (int i = 0; i < N; i++) {
    cin >> x >> y;
    v.push_back(make_pair(x, y));
}
```

**在**之后:

```cpp
#define ll long long int
#define MP make_pair
#define pb push_back

vector<ll, ll> v;

for (int i = 0; i < N; i++) {
    cin >> x >> y;
    v.pb(MP(x, y));
}
```

**注意:**在代码的开头写下你的宏(参考下面给出的模板)。

**使用模板**
使用模板是加速实现的最好方法之一。准备好你的模板，里面已经写好了宏。这有助于减少大量的时间，否则这些时间将用于从头开始编写整个代码。
我用下面的模板，你可以用一个适合你的。

```cpp
#include "bits/stdc++.h"
using namespace std;
#define max(a, b) (a < b ? b : a)
#define min(a, b) ((a > b) ? b : a)
#define mod 1e9 + 7
#define FOR(a, c) for (int(a) = 0; (a) < (c); (a)++)
#define FORL(a, b, c) for (int(a) = (b); (a) <= (c); (a)++)
#define FORR(a, b, c) for (int(a) = (b); (a) >= (c); (a)--)
#define INF 1000000000000000003
typedef long long int ll;
typedef vector<int> vi;
typedef pair<int, int> pi;
#define F first
#define S second
#define PB push_back
#define POB pop_back
#define MP make_pair
int main()
{
    ios::sync_with_stdio(0);
    cin.tie(0);
    int T;
    cin >> T;
    while (T--) {
        int N;
        cin >> N;
        ll a[N];
        FOR(i, N)
        cin >> a[i];
    }
    return 0;
}
```

感谢您的阅读，如果您有任何可能的改进或补充，请告诉我。