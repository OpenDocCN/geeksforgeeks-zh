# PHP Ds\Sequence 函数完整参考

> Original: [https://www.geeksforgeeks.org/php-dssequence-functions-complete-reference/](https://www.geeksforgeeks.org/php-dssequence-functions-complete-reference/)

序列用于以单一和线性维度的方式排列值。在某些语言中，序列指的是列表。该序列与用作增量整数键的数组类似，如下所示：

*   序列的索引值为 `[0, 1, 2, …., size-1]`，其中 `size` 表示数组的大小。
*   序列元素通过索引值访问，因此它允许通过索引访问 `[0, size-1]` 范围内的值。
*   `Ds\Sequence` 是 PHP 7 中的一种高效数据结构。它是数组的一种替代方案。

**要求：** 扩展和兼容性 PolyFill 都需要 PHP 7。

**安装：** 使用 PECL 扩展安装数据结构的最简单方法。

```bash
pecl install ds
```

数据结构 `Ds\Sequence` 完整列表如下：

## 基础操作函数

*   [`php|ds\Sequence::allocate()` 函数](https://www.geeksforgeeks.org/php-dssequence-allocate-function/)
*   [`php|ds\Sequence::apply()` 函数](https://www.geeksforgeeks.org/php-dssequence-apply-function/)
*   [`php|ds\Sequence::capacity()` 函数](https://www.geeksforgeeks.org/php-dssequence-capacity-function/)
*   [`php|ds\Sequence::contains()` 函数](https://www.geeksforgeeks.org/php-dssequence-contains-function/)
*   [`php|ds\Sequence::copy()` 函数](https://www.geeksforgeeks.org/php-dssequence-contains-function/)
*   [`php|ds\Sequence::count()` 函数](https://www.geeksforgeeks.org/php-dssequence-contains-function/)

## 元素访问与查找函数

*   [`php|ds\Sequence::filter()` 函数](https://www.geeksforgeeks.org/php-dssequence-filter-function/)
*   [`php|ds\Sequence::find()` 函数](https://www.geeksforgeeks.org/php-dssequence-find-function/)
*   [`php|ds\Sequence::first()` 函数](https://www.geeksforgeeks.org/php-dssequence-first-function/)
*   [`php|ds\Sequence::get()` 函数](https://www.geeksforgeeks.org/php-dssequence-get-function/)

## 元素增删与修改函数

*   [`php|ds\Sequence::insert()` 函数](https://www.geeksforgeeks.org/php-dssequence-insert-function/)
*   [`php|ds\Sequence::pop()` 函数](https://www.geeksforgeeks.org/php-dssequence-pop-function/)
*   [`php|ds\Sequence::push()` 函数](https://www.geeksforgeeks.org/php-dssequence-push-function/)
*   [`php|ds\Sequence::remove()` 函数](https://www.geeksforgeeks.org/php-dssequence-remove-function/)
*   [`php|ds\Sequence::set()` 函数](https://www.geeksforgeeks.org/php-dssequence-set-function/)
*   [`php|ds\Sequence::shift()` 函数](https://www.geeksforgeeks.org/php-dssequence-shift-function/)
*   [`php|ds\Sequence::unshift()` 函数](https://www.geeksforgeeks.org/php-dssequence-unshift-function/)

## 序列变换与计算函数

*   [`php|ds\Sequence::join()` 函数](https://www.geeksforgeeks.org/php-dssequence-join-function/)
*   [`php|ds\Sequence::last()` 函数](https://www.geeksforgeeks.org/php-dssequence-last-function/)
*   [`php|ds\Sequence::map()` 函数](https://www.geeksforgeeks.org/php-dssequence-map-function/)
*   [`php|ds\Sequence::merge()` 函数](https://www.geeksforgeeks.org/php-dssequence-merge-function/)
*   [`php|ds\Sequence::reduce()` 函数](https://www.geeksforgeeks.org/php-dssequence-reduce-function/)
*   [`php|ds\Sequence::reverse()` 函数](https://www.geeksforgeeks.org/php-dssequence-reverse-function/)
*   [`php|ds\Sequence::rotate()` 函数](https://www.geeksforgeeks.org/php-dssequence-rotate-function/)
*   [`php|ds\Sequence::slice()` 函数](https://www.geeksforgeeks.org/php-dssequence-slice-function/)
*   [`php|ds\Sequence::sorted()` 函数](https://www.geeksforgeeks.org/php-dssequence-sorted-function/)
*   [`php|ds\Sequence::sum()` 函数](https://www.geeksforgeeks.org/php-dssequence-sum-function/)