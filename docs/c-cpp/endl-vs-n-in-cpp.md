# c++ 中 endl vs \ n

> 原文:[https://www.geeksforgeeks.org/endl-vs-n-in-cpp/](https://www.geeksforgeeks.org/endl-vs-n-in-cpp/)

endl 和/n 似乎都在做同样的事情，但它们之间有细微的区别。

**cout < < endl** 插入新行并刷新流(输出缓冲区)，而**cout<<“\ n”**只是插入新行。

因此，**cout<<endl；**可以说相当于 **cout < < '\n' < <同花顺；**

**endl 和\n 的其他一些区别是:**

<figure class="table">

| 

endl

 | 

\ n

 |
| --- | --- |
| It is a manipulator. | It's a character. |
| It doesn't take up any memory. | Because it is a character, it takes up 1 byte of memory. |
| It is a keyword that does not specify any meaning when stored in a string. | It can be stored in a string and still convey its specific newline meaning. |
| We can't write' endl' between double quotes. | We can write "\ n" between double quotes like cout < |
| Only supported by C++. | Both C and C++ are supported. |
| It constantly refreshes the queue in the output buffer during the whole process. | It only refreshes the output buffer once at the end of the program. |

</figure>

> **注:cout<<“\ n”**似乎性能方面要优于**cout<<endl；**除非需要冲洗水流。
> 
> T63】

本文由 **Akshat Saxena** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org/)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。