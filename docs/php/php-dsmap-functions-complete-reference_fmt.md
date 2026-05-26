# PHP `Ds\Map` 函数完整参考

> Original: [https://www.geeksforgeeks.org/php-dsmap-functions-complete-reference/](https://www.geeksforgeeks.org/php-dsmap-functions-complete-reference/)

## 简介

映射是键-值对的顺序集合，非常类似于数组。映射的关键字可以是任何类型，并且是唯一的。如果将任何值添加到映射中的同一键，则将替换该映射值。

它是 PHP7 中的高效数据结构，可以替代数组。

**要求：** 扩展和兼容性 PolyFill 都需要 PHP 7。

**安装：** 使用 PECL 扩展安装数据结构的最简单方法。

```php
pecl install ds
```

## 函数列表

数据结构 `Ds\Map` 的完整列表如下所示：

*   [`Ds\Map::allocate()`](https://www.geeksforgeeks.org/php-dsmap-allocate-function/)
*   [`Ds\Map::apply()`](https://www.geeksforgeeks.org/php-dsmap-apply-function/)
*   [`Ds\Map::capacity()`](https://www.geeksforgeeks.org/php-dsmap-capacity-function/)
*   [`Ds\Map::clear()`](https://www.geeksforgeeks.org/php-dsmap-clear-function/)
*   [`Ds\Map::__construct()`](https://www.geeksforgeeks.org/php-dsmap-__construct-function/)
*   [`Ds\Map::copy()`](https://www.geeksforgeeks.org/php-dsmap-copy-function/)
*   [`Ds\Map::count()`](https://www.geeksforgeeks.org/php-dsmap-count-function/)
*   [`Ds\Map::diff()`](https://www.geeksforgeeks.org/php-dsmap-diff-function/)
*   [`Ds\Map::filter()`](https://www.geeksforgeeks.org/php-dsmap-filter-function/)
*   [`Ds\Map::first()`](https://www.geeksforgeeks.org/php-dsmap-first-function/)
*   [`Ds\Map::get()`](https://www.geeksforgeeks.org/php-dsmap-get-function/)
*   [`Ds\Map::hasKey()`](https://www.geeksforgeeks.org/php-dsmap-haskey-function/)
*   [`Ds\Map::hasValue()`](https://www.geeksforgeeks.org/php-dsmap-hasvalue-function/)
*   [`Ds\Map::intersect()`](https://www.geeksforgeeks.org/php-dsmap-intersect-function/)
*   [`Ds\Map::isEmpty()`](https://www.geeksforgeeks.org/php-dsmap-isempty-function/)
*   [`Ds\Map::keys()`](https://www.geeksforgeeks.org/php-dsmap-keys-function/)
*   [`Ds\Map::ksort()`](https://www.geeksforgeeks.org/php-dsmapksort-function/)
*   [`Ds\Map::ksorted()`](https://www.geeksforgeeks.org/php-dsmap-ksorted-function/)
*   [`Ds\Map::last()`](https://www.geeksforgeeks.org/php-dsmap-last-function/)
*   [`Ds\Map::merge()`](https://www.geeksforgeeks.org/php-dsmap-merge-function/)
*   [`Ds\Map::pairs()`](https://www.geeksforgeeks.org/php-dsmap-pairs-function/)
*   [`Ds\Map::putAll()`](https://www.geeksforgeeks.org/php-dsmap-putall-function/)
*   [`Ds\Map::reduce()`](https://www.geeksforgeeks.org/php-dsmap-reduce-function/)
*   [`Ds\Map::reverse()`](https://www.geeksforgeeks.org/php-dsmap-reverse-function/)
*   [`Ds\Map::reversed()`](https://www.geeksforgeeks.org/php-dsmap-reversed-function/)
*   [`Ds\Map::skip()`](https://www.geeksforgeeks.org/php-dsmap-skip-function/)
*   [`Ds\Map::slice()`](https://www.geeksforgeeks.org/php-dsmap-slice-function/)
*   [`Ds\Map::sort()`](https://www.geeksforgeeks.org/php-dsmap-sort-function/)
*   [`Ds\Map::sorted()`](https://www.geeksforgeeks.org/php-dsmap-sorted-function/)
*   [`Ds\Map::sum()`](https://www.geeksforgeeks.org/php-dsmap-sum-function/)
*   [`Ds\Map::toArray()`](https://www.geeksforgeeks.org/php-dsmap-toarray-function/)
*   [`Ds\Map::union()`](https://www.geeksforgeeks.org/php-dsmap-union-function/)
*   [`Ds\Map::values()`](https://www.geeksforgeeks.org/php-dsmap-values-function/)
*   [`Ds\Map::xor()`](https://www.geeksforgeeks.org/php-dsmap-xor-function/)