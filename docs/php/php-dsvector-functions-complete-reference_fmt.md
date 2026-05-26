# PHP `ds\Vector` 函数完整参考

> Original: [https://www.geeksforgeeks.org/php-dsvector-functions-complete-reference/](https://www.geeksforgeeks.org/php-dsvector-functions-complete-reference/)

矢量数据结构用于将值序列存储在连续的内存缓冲区中，该缓冲区会自动增长和缩小。向量数据结构将索引值映射到其索引缓冲区，并且增长因子没有绑定到特定的倍数或指数。

它是 PHP7 中的高效数据结构，可以替代数组。

## 要求
扩展和兼容性 PolyFill 都需要 PHP 7。

## 安装
使用 PECL 扩展安装数据结构的最简单方法。
```php
pecl install ds
```

数据结构 `ds\Vector` 的完整列表如下：

*   [php|`ds\Vector::allocate()`函数](https://www.geeksforgeeks.org/php-dsvector-allocate-function/)
*   [php|`ds\Vector::apply()`函数](https://www.geeksforgeeks.org/php-dsvector-apply-function/)
*   [php|`ds\Vector::capacity()`函数](https://www.geeksforgeeks.org/php-dsvector-capacity-function/)
*   [php|`ds\Vector::clear()`函数](https://www.geeksforgeeks.org/php-dsvector-clear-function/)
*   [php|`ds\Vector::__construct()`函数](https://www.geeksforgeeks.org/php-dsvector-__construct-function/)
*   [php|`ds\Vector::contains()`函数](https://www.geeksforgeeks.org/php-dsvector-contains-function/)
*   [php|`ds\Vector::copy()`函数](https://www.geeksforgeeks.org/php-dsvector-copy-function/)
*   [php|`ds\Vector::count()`函数](https://www.geeksforgeeks.org/php-dsvector-count-function/)
*   [php|`ds\Vector::filter()`函数](https://www.geeksforgeeks.org/php-dsvector-filter-function/)
*   [php|`ds\Vector::find()`函数](https://www.geeksforgeeks.org/php-dsvector-find-function/)
*   [php|`ds\Vector::first()`函数](https://www.geeksforgeeks.org/php-dsvector-first-function/)
*   [php|`ds\Vector::get()`函数](https://www.geeksforgeeks.org/php-dsvector-get-function/)
*   [php|`ds\Vector::insert()`函数](https://www.geeksforgeeks.org/php-dsvector-insert-function/)
*   [php|`ds\Vector::isEmpty()`函数](https://www.geeksforgeeks.org/php-dsvector-isempty-function/)
*   [php|`ds\Vector::join()`函数](https://www.geeksforgeeks.org/php-dsvector-join-function/)
*   [php|`ds\Vector::jsonSerialize()`函数](https://www.geeksforgeeks.org/php-dsvector-jsonserialize-function/)
*   [php|`ds\Vector::last()`函数](https://www.geeksforgeeks.org/php-dsvector-last-function/)
*   [php|`ds\Vector::map()`函数](https://www.geeksforgeeks.org/php-dsvector-map-function/)
*   [php|`ds\Vector::merge()`函数](https://www.geeksforgeeks.org/php-dsvector-merge-function/)
*   [php|`ds\Vector::pop()`函数](https://www.geeksforgeeks.org/php-dsvector-pop-function/)
*   [php|`ds\Vector::push()`函数](https://www.geeksforgeeks.org/php-dsvector-push-function/)
*   [php|`ds\Vector::reduce()`函数](https://www.geeksforgeeks.org/php-dsvector-reduce-function/)
*   [php|`ds\Vector::remove()`函数](https://www.geeksforgeeks.org/php-dsvector-remove-function/)
*   [php|`ds\Vector::reverse()`函数](https://www.geeksforgeeks.org/php-dsvector-reverse-function/)
*   [php|`ds\Vector::rotate()`函数](https://www.geeksforgeeks.org/php-dsvector-rotate-function/)
*   [php|`ds\Vector::set()`函数](https://www.geeksforgeeks.org/php-dsvector-set-function/)
*   [php|`ds\Vector::shift()`函数](https://www.geeksforgeeks.org/php-dsvector-shift-function/)
*   [php|`ds\Vector::slice()`函数](https://www.geeksforgeeks.org/php-dsvector-slice-function/)
*   [php|`ds\Vector::sort()`函数](https://www.geeksforgeeks.org/php-dsvector-sort-function/)
*   [php|`ds\Vector::sorted()`函数](https://www.geeksforgeeks.org/php-dsvector-sorted-function/)
*   [php|`ds\Vector::sum()`函数](https://www.geeksforgeeks.org/php-dsvector-sum-function/)
*   [php|`ds\Vector::toArray()`函数](https://www.geeksforgeeks.org/php-dsvector-toarray-function/)
*   [php|`ds\Vector::unshift()`函数](https://www.geeksforgeeks.org/php-dsvector-unshift-function/)