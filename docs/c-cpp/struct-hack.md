# 结构黑客

> 原文:[https://www.geeksforgeeks.org/struct-hack/](https://www.geeksforgeeks.org/struct-hack/)

下面的结构会有多大？

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
struct employee
{
    int     emp_id;
    int     name_len;
    char    name[0];
};
```

4 + 4 + 0 = 8 字节。
那么“名称[0]”的大小呢？在 gcc 中，当我们创建零长度的数组时，它被认为是不完整类型的数组，这就是为什么 gcc 将其大小报告为“0”字节。这种技术被称为“结构黑客”。当我们在结构内部创建长度为零的数组时，它必须是(也是唯一的)结构的最后一个成员。很快我们将看到如何使用它。
“结构黑客”技术用于在结构中创建可变长度成员。在上面的结构中，“name”的字符串长度不是固定的，所以我们可以使用“name”作为变长数组。
下面我们来看看内存分配。

```cpp
struct employee *e = malloc(sizeof(*e) + sizeof(char) * 128); 
```

相当于

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
struct employee
{
    int     emp_id;
    int        name_len;
    char    name[128]; /* character array of size 128 */
};
```

低于内存分配

```cpp
struct employee *e = malloc(sizeof(*e) + sizeof(char) * 1024); 
```

相当于

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
struct employee
{
    int        emp_id;
    int        name_len;
    char    name[1024]; /* character array of size 1024 */
};
```

注意:因为名字是字符数组，所以在 malloc 中不用“sizeof(char) * 128”，我们可以直接用“128”。sizeof 用于避免混淆。
现在我们可以用和指针一样的“名字”了。例如

```cpp
e->emp_id     = 100;
e->name_len    = strlen("Geeks For Geeks");
strncpy(e->name, "Geeks For Geeks", e->name_len);
```

当我们按照上面给出的方法分配内存时，编译器会分配内存来存储“emp_id”和“name_len”，再加上连续内存来存储“name”。当我们使用这种技术时，gcc 保证“name”将获得连续的内存。
显然还有其他解决问题的方法，一是我们可以使用字符指针。但是不能保证字符指针会获得连续内存，我们可以利用这种连续内存。例如，通过使用这种技术，我们可以通过使用单个 malloc 和 free call 来分配和释放内存(因为内存是会传染的)。这样做的另一个好处是，假设如果我们想写数据，我们可以通过使用单个“write()”调用来写整个数据。例如

```cpp
write(fd, e, sizeof(*e) + name_len); /* write emp_id + name_len + name */ 
```

如果我们使用字符指针，那么我们需要 2 个写调用来写数据。例如

```cpp
write(fd, e, sizeof(*e));         /* write emp_id + name_len */
write(fd, e->name, e->name_len);    /* write name */
```

注:C99 中有一个叫“灵活数组成员”的功能，工作原理和
的“Struct Hack”一样，本文由**纳伦德拉·康拉尔卡尔**编译。如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息