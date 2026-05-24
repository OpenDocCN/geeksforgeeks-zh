# C++ STL 中的库

> 原文: [https://www.geeksforgeeks.org/algorithms-library-c-stl/](https://www.geeksforgeeks.org/algorithms-library-c-stl/)

## 非修改顺序操作

1.  [`std::all_of`](https://www.geeksforgeeks.org/stdall_of-in-cpp/): 测试范围内所有元素的条件
2.  [`std::any_of`](https://www.geeksforgeeks.org/useful-array-algorithms-in-c-stl/): 测试范围内的任何元素是否满足条件
3.  [`std::none_of`](https://www.geeksforgeeks.org/stdnone_of-in-c/): 测试是否没有元素满足条件
4.  [`std::for_each`](https://www.geeksforgeeks.org/for_each-loop-c/): 将功能应用于范围
5.  [`std::find`](https://www.geeksforgeeks.org/stdfind-in-c/): 在范围内查找值
6.  [`std::find_if`](https://www.geeksforgeeks.org/stdfind_if-stdfind_if_not-in-c/): 查找范围内的元素
7.  [`std::find_if_not`](https://www.geeksforgeeks.org/stdfind_if-stdfind_if_not-in-c/): 查找范围内的元素(负条件)
8.  [`std::find_end`](https://www.geeksforgeeks.org/stdfind_end-in-cpp/): 查找范围内的最后一个子序列
9.  [`std::find_first_of`](https://www.geeksforgeeks.org/stdfind_first_of-in-cpp/): 在范围内从集合中查找元素
10. [`std::adjacent_find`](https://www.geeksforgeeks.org/stdadjacent_find-in-c/): 查找范围内相等的相邻元素
11. [`std::count`](https://www.geeksforgeeks.org/std-count-cpp-stl/): 统计范围内有价值的外观
12. [`std::count_if`](https://www.geeksforgeeks.org/count_if-in-c/): 返回满足条件的范围内的元素数量
13. [`std::mismatch`](https://www.geeksforgeeks.org/stdmismatch-examples-c/): 返回两个范围不同的第一个位置
14. [`std::equal`](https://www.geeksforgeeks.org/stdequal-in-cpp/): 测试两个范围内的元素是否相等
15. [`std::is_permutation`](https://www.geeksforgeeks.org/stdis_permutation-c-stl/): 测试范围是否是另一个的排列
16. [`std::search`](https://www.geeksforgeeks.org/stdsearch-in-c/): 子序列的搜索范围
17. [`std::search_n`](https://www.geeksforgeeks.org/stdsearch_n-with-example-in-cpp/): 元素的搜索范围

## 修改顺序操作

1.  [`std::copy`](https://www.geeksforgeeks.org/different-methods-copy-c-stl-stdcopy-copy_n-copy_if-copy_backwards/): 复制元素范围
2.  [`std::copy_n`](https://www.geeksforgeeks.org/different-methods-copy-c-stl-stdcopy-copy_n-copy_if-copy_backwards/): 复制元素
3.  [`std::copy_if`](https://www.geeksforgeeks.org/different-methods-copy-c-stl-stdcopy-copy_n-copy_if-copy_backwards/): 复制范围内的某些元素
4.  [`std::copy_backward`](https://www.geeksforgeeks.org/different-methods-copy-c-stl-stdcopy-copy_n-copy_if-copy_backwards/): 向后复制元素范围
5.  [`std::move`](https://www.geeksforgeeks.org/stdmove-in-c/): 移动元素范围
6.  [`std::move_backward`](https://www.geeksforgeeks.org/stdmove_backward-in-c/): 向后移动元素范围
7.  [`std::swap`](https://www.geeksforgeeks.org/swap-in-cpp/): 交换两个对象的值
8.  [`std::swap_ranges`](https://www.geeksforgeeks.org/stdswap_ranges-in-c/): 交换两个范围的值
9.  [`std::iter_swap`](https://www.geeksforgeeks.org/stditer_swap-in-cpp/): 交换两个迭代器指向的对象的值
10. [`std::transform`](https://www.geeksforgeeks.org/transform-c-stl-perform-operation-elements/): 变换范围
11. [`std::replace`](https://www.geeksforgeeks.org/stdreplace-stdreplace_if-c/): 替换范围内的值
12. [`std::replace_if`](https://www.geeksforgeeks.org/stdreplace-stdreplace_if-c/): 替换范围内的值
13. [`std::replace_copy`](https://www.geeksforgeeks.org/stdstringreplace_copy-stdstringreplace_copy_if-cpp/): 复制范围替换值
14. [`std::replace_copy_if`](https://www.geeksforgeeks.org/stdstringreplace_copy-stdstringreplace_copy_if-cpp/): 复制范围替换值
15. [`std::fill`](https://www.geeksforgeeks.org/populating-vector-c-using-fill-fill_n/): 用值填充范围
16. [`std::fill_n`](https://www.geeksforgeeks.org/populating-vector-c-using-fill-fill_n/): 用值填充序列
17. [`std::generate`](https://www.geeksforgeeks.org/stdgenerate-in-c/): 使用函数生成范围值
18. [`std::generate_n`](https://www.geeksforgeeks.org/stdgenerate_n-in-cpp/): 使用函数为序列生成值
19. [`std::remove`](https://www.geeksforgeeks.org/stdremove-stdremove_if-c/): 从范围中移除值
20. [`std::remove_if`](https://www.geeksforgeeks.org/stdremove-stdremove_if-c/): 从范围中移除元素
21. [`std::remove_copy`](https://www.geeksforgeeks.org/std-string-remove_copy-std-string-remove_copy_if-c/): 复制范围移除值
22. [`std::remove_copy_if`](https://www.geeksforgeeks.org/std-string-remove_copy-std-string-remove_copy_if-c/): 复制范围移除值
23. [`std::unique`](https://www.geeksforgeeks.org/stdunique-in-cpp/): 删除范围内的连续重复项
24. [`std::unique_copy`](https://www.geeksforgeeks.org/stdunique_copy-in-c/): 复制范围删除重复项
25. [`std::reverse`](https://www.geeksforgeeks.org/stdreverse-in-c/): 反转范围
26. [`std::reverse_copy`](https://www.geeksforgeeks.org/std-reverse_copy-in-c-stl/): 复制范围反转
27. [`std::rotate`](https://www.geeksforgeeks.org/rotate-in-cpp-stl/): 向左旋转范围内的元素
28. [`std::rotate_copy`](https://www.geeksforgeeks.org/stdrotate-vs-stdrotate_copy-c-stl/): 复制范围向左旋转
29. [`std::random_shuffle`](https://www.geeksforgeeks.org/shuffle-an-array-using-stl-in-c/): 随机重排范围内的元素
30. [`std::shuffle`](https://www.geeksforgeeks.org/shuffle-an-array-using-stl-in-c/): 使用生成器随机重排范围内的元素

### 分区操作

1.  [`std::is_partitioned`](https://www.geeksforgeeks.org/stdis_partitioned-in-c/): 测试范围是否分区
2.  [`std::partition`](https://www.geeksforgeeks.org/stdpartition-in-c-stl/): 分区范围一分为二
3.  [`std::stable_partition`](https://www.geeksforgeeks.org/stdstable_partition-in-c/): 分区范围一分为二——稳定排序
4.  [`std::partition_copy`](https://www.geeksforgeeks.org/stdpartition-in-c-stl/): 分区范围分为两个
5.  [`std::partition_point`](https://www.geeksforgeeks.org/stdpartition-in-c-stl/): 获取分区点

### 排序

## 排序算法

1.  [`std::sort`](https://www.geeksforgeeks.org/sort-c-stl/)：对范围内的元素进行排序。
2.  [`std::stable_sort`](https://www.geeksforgeeks.org/stable_sort-c-stl/)：对保持等价顺序的元素进行排序。
3.  [`std::partial_sort`](https://www.geeksforgeeks.org/stdpartial_sort-in-cpp/)：对范围内的元素进行部分排序。
4.  [`std::partial_sort_copy`](https://www.geeksforgeeks.org/stdpartial_sort_copy-in-cpp/)：复制和部分排序范围。
5.  [`std::is_sorted`](https://www.geeksforgeeks.org/stdis_sorted-in-cpp/)：检查范围是否排序。
6.  [`std::is_sorted_until`](https://www.geeksforgeeks.org/stdis_sorted_until-in-cpp/)：查找范围内第一个未排序的元素。
7.  [`std::nth_element`](https://www.geeksforgeeks.org/stdnth_element-in-cpp/)：排序范围内的元素。

## 二分搜索法（在分区/分类范围内运行）

1.  [`std::lower_bound`](https://www.geeksforgeeks.org/stdlower_bound-in-c/)：将迭代器返回下界。
2.  [`std::upper_bound`](https://www.geeksforgeeks.org/upper_bound-and-lower_bound-for-vector-in-cpp-stl/)：将迭代器返回上限。
3.  [`std::equal_range`](https://www.geeksforgeeks.org/stdequal_range-in-cpp/)：获取相等元素的子范围。
4.  [`std::binary_search`](https://www.geeksforgeeks.org/binary-search-algorithms-the-c-standard-template-library-stl/)：测试排序后的序列中是否存在值。

## 合并（在排序范围内操作）

1.  [`std::merge`](https://www.geeksforgeeks.org/stdmerge-c-stl/)：合并排序范围。
2.  [`std::inplace_merge`](https://www.geeksforgeeks.org/stdmerge-c-stl/)：合并连续排序的范围。
3.  [`std::includes`](https://www.geeksforgeeks.org/stdmerge-c-stl/)：测试排序范围是否包含另一个排序范围。
4.  [`std::set_union`](https://www.geeksforgeeks.org/stdmerge-c-stl/)：两个排序范围的并集。
5.  [`std::set_intersection`](https://www.geeksforgeeks.org/stdmerge-c-stl/)：两个排序范围的交集。
6.  [`std::set_difference`](https://www.geeksforgeeks.org/stdmerge-c-stl/)：两个排序范围的差异。
7.  [`std::set_symmetric_difference`](https://www.geeksforgeeks.org/stdmerge-c-stl/)：两个排序范围的对称差。

## 堆操作

1.  [`std::push_heap`](https://www.geeksforgeeks.org/heap-using-stl-c/)：将元素推入堆范围。
2.  [`std::pop_heap`](https://www.geeksforgeeks.org/heap-using-stl-c/)：Pop 元素从堆范围。
3.  [`std::make_heap`](https://www.geeksforgeeks.org/stdmake_heap-c-stl/)：Make heap from range。
4.  [`std::sort_heap`](https://www.geeksforgeeks.org/stdsort_heap-in-cpp/)：堆的排序元素。
5.  [`std::is_heap`](https://www.geeksforgeeks.org/heap-using-stl-c/)：测试范围是否为 heap。
6.  [`std::is_heap_until`](https://www.geeksforgeeks.org/heap-using-stl-c/)：找到第一个没有按堆顺序排列的元素。
7.  [`std::max`](https://www.geeksforgeeks.org/stdmax-in-cpp/)：返程最大。
8.  [`std::minmax`](https://www.geeksforgeeks.org/stdminmax-stdminmax_element-c-stl/)：返回最小和最大元素。
9.  [`std::min_element`](https://www.geeksforgeeks.org/stdmin_element-in-cpp/)：返回范围内最小的元素。
10. [`std::max_element`](https://www.geeksforgeeks.org/stdmax_element-in-cpp/)：返回范围内最大的元素。
11. [`std::minmax_element`](https://www.geeksforgeeks.org/stdminmax-stdminmax_element-c-stl/)：返回范围内最小和最大的元素。

## 其他操作

1.  [`std::lexicographical_compare`](https://www.geeksforgeeks.org/stdlexicographical_compare-in-cpp/)：辞书小于比较。
2.  [`std::next_permutation`](https://www.geeksforgeeks.org/stdnext_permutation-prev_permutation-c/)：将范围转换为下一个排列。
3.  [`std::prev_permutation`](https://www.geeksforgeeks.org/stdnext_permutation-prev_permutation-c/)：将范围转换为前一个排列。

[C++ 的所有 STL 文章](https://www.geeksforgeeks.org/tag/stl/)