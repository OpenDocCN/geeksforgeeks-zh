# Perl | sleep()函数

> 原文:[https://www.geeksforgeeks.org/perl-sleep-function/](https://www.geeksforgeeks.org/perl-sleep-function/)

[Perl](https://www.geeksforgeeks.org/introduction-to-perl/) 中的 `sleep()` 函数是一个内置函数，用于将当前脚本的执行延迟指定的秒数，如果没有指定参数，则永远延迟。`sleep()` 函数接受 `秒` 作为参数，并在成功时返回相同的值。

> **语法:** `sleep(秒)`
> 
> **返回:** 传递给它的 `秒` 参数，成功后

**例 1:**

```perl
#!/usr/bin/perl -w

# Using localtime() function
# to print the time
print scalar localtime();

# calling the sleep function
sleep(5);

print "\n";

print scalar localtime();
```

**输出:**

```perl
Thu Mar 28 06:02:21 2019
Thu Mar 28 06:02:26 2019
```

**例 2:**

```perl
#!/usr/bin/perl -w

# Using localtime() function
# to print the time
print scalar localtime();

# Using rand() to generate random delay
sleep(rand(7));

print "\n";

print scalar localtime();
```

**输出:**

```perl
Thu Mar 28 06:02:26 2019
Thu Mar 28 06:02:27 2019
```