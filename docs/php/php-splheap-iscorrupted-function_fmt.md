# PHP SplHeap isCorrupted()函数

> Original: [https://www.geeksforgeeks.org/php-splheap-iscorrupted-function/](https://www.geeksforgeeks.org/php-splheap-iscorrupted-function/)

`SplHeap::isCorrupted()`函数是 PHP 中的一个内置函数，用于判断堆是否处于损坏状态。

通常，堆数据结构有两种类型：

*   `max-heap`：在最大堆中，根节点上出现的键必须是其所有子节点上出现的所有键中最大的。对于二叉树中的所有子树，此属性必须递归成立。
*   `Min-Heap`：在最小堆中，根节点上出现的键必须是其所有子节点上出现的键中最小的。对于二叉树中的所有子树，此属性必须递归成立。

**语法：**

```php
bool SplHeap::isCorrupted()
```

**参数：** 此函数不接受任何参数。

**返回值：** 如果堆损坏，此函数返回 `TRUE`，否则返回 `FALSE`。

下面的程序演示了 PHP 中的 `SplHeap::isCorrupted()`函数：

### 示例 1

```php
<?php

// Create a new empty Mix Heap 
$heap = new SplMinHeap();

// Insert elements in min heap
$heap->insert('System'); 
$heap->insert('GFG'); 
$heap->insert('ALGO'); 
$heap->insert('C');
$heap->insert('Geeks'); 
$heap->insert('GeeksforGeeks');

// Check heap is in a corrupted
// state or not
var_dump($heap->isCorrupted());

?>
```

发帖主题：Re：Колибри0.7.8.0

### 示例 2

```php
<?php

// Create a new empty Max Heap 
$heap = new SplMaxHeap();

// Insert elements in max heap
$heap->insert('System'); 
$heap->insert('GFG'); 
$heap->insert('ALGO'); 
$heap->insert('C');
$heap->insert('Geeks'); 
$heap->insert('GeeksforGeeks');

// Check heap is in a corrupted
// state or not
var_dump($heap->isCorrupted());

?>
```

发帖主题：Re：Колибри0.7.8.0

**引用：** [https://www.php.net/manual/en/splheap.iscorrupted.php](https://www.php.net/manual/en/splheap.iscorrupted.php)