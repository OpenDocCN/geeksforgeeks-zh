# PHP SPL 数据结构完整参考

> Original: [https://www.geeksforgeeks.org/php-spl-data-structures-complete-reference/](https://www.geeksforgeeks.org/php-spl-data-structures-complete-reference/)

标准 PHP 库 (SPL) 提供了标准数据结构的集合。SPL 数据结构根据其实现对内容进行分组。双向链表的内容包括：
* `SplDoublyLinkedList`
* `SplStack`
* `SplQueue`
* `SplHeap`
* `SplMaxHeap`
* `SplMinHeap`
* `SplObjectStorage`

## SplDoublyLinkedList 函数
* [`SplDoublyLinkedList`](https://www.geeksforgeeks.org/spldoublylinkedlist-in-php/)
* [`SplDoublyLinkedList::add()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-add-function/)
* [`SplDoublyLinkedList::bottom()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-bottom-function/)
* [`SplDoublyLinkedList::current()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-current-function/)
* [`SplDoublyLinkedList::isEmpty()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-isempty-function/)
* [`SplDoublyLinkedList::key()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-key-function/)
* [`SplDoublyLinkedList::next()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-next-function/)
* [`SplDoublyLinkedList::offsetGet()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-offsetget-function/)
* [`SplDoublyLinkedList::offsetSet()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-offsetset-function/)
* [`SplDoublyLinkedList::offsetUnset()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-offsetunset-function/)
* [`SplDoublyLinkedList::prev()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-prev-function/)
* [`SplDoublyLinkedList::push()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-push-function/)
* [`SplDoublyLinkedList::rewind()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-rewind-function/)
* [`SplDoublyLinkedList::shift()`](https://www.geeksforgeeks.org/php-spldoublylinkedlist-shift-function/)

## SplFixedArray 函数
* [`SplFixedArray::count()`](https://www.geeksforgeeks.org/php-splfixedarray-count-function/)
* [`SplFixedArray::current()`](https://www.geeksforgeeks.org/php-splfixedarray-current-function/)
* [`SplFixedArray::getSize()`](https://www.geeksforgeeks.org/php-splfixedarray-getsize-function/)
* [`SplFixedArray::next()`](https://www.geeksforgeeks.org/php-splfixedarray-next-function/)
* [`SplFixedArray::offsetExists()`](https://www.geeksforgeeks.org/php-splfixedarray-offsetexists-function/)
* [`SplFixedArray::offsetGet()`](https://www.geeksforgeeks.org/php-splfixedarray-offsetget-function/)
* [`SplFixedArray::offsetSet()`](https://www.geeksforgeeks.org/php-splfixedarray-offsetset-function/)
* [`SplFixedArray::offsetUnset()`](https://www.geeksforgeeks.org/php-splfixedarray-offsetunset-function/)
* [`SplFixedArray::rewind()`](https://www.geeksforgeeks.org/php-splfixedarray-rewind-function/)
* [`SplFixedArray::setSize()`](https://www.geeksforgeeks.org/php-splfixedarray-setsize-function/)
* [`SplFixedArray::toArray()`](https://www.geeksforgeeks.org/php-splfixedarray-toarray-function/)
* [`SplFixedArray::valid()`](https://www.geeksforgeeks.org/php-splfixedarray-valid-function/)

## SplObjectStorage 函数
* [`SplObjectStorage::addAll()`](https://www.geeksforgeeks.org/php-splobjectstorage-addall-function/)
* [`SplObjectStorage::attach()`](https://www.geeksforgeeks.org/php-splobjectstorage-attach-function/)
* [`SplObjectStorage::contains()`](https://www.geeksforgeeks.org/php-splobjectstorage-contains-function/)
* [`SplObjectStorage::current()`](https://www.geeksforgeeks.org/php-splobjectstorage-current-function/)
* [`SplObjectStorage::detach()`](https://www.geeksforgeeks.org/php-splobjectstorage-detach-function/)
* [`SplObjectStorage::getInfo()`](https://www.geeksforgeeks.org/php-splobjectstorage-getinfo-function/)
* [`SplObjectStorage::key()`](https://www.geeksforgeeks.org/php-splobjectstorage-key-function/)
* [`SplObjectStorage::offsetExists()`](https://www.geeksforgeeks.org/php-splobjectstorage-offsetexists-function/)
* [`SplObjectStorage::offsetGet()`](https://www.geeksforgeeks.org/php-splobjectstorage-offsetget-function/)
* [`SplObjectStorage::offsetSet()`](https://www.geeksforgeeks.org/php-splobjectstorage-offsetset-function/)
* [`SplObjectStorage::removeAll()`](https://www.geeksforgeeks.org/php-splobjectstorage-removeall-function/)
* [`SplObjectStorage::removeAllExcept()`](https://www.geeksforgeeks.org/php-splobjectstorage-removeallexcept-function/)
* [`SplObjectStorage::rewind()`](https://www.geeksforgeeks.org/php-splobjectstorage-rewind-function/)
* [`SplObjectStorage::serialize()`](https://www.geeksforgeeks.org/php-splobjectstorage-serialize-function/)
* [`SplObjectStorage::unserialize()`](https://www.geeksforgeeks.org/php-splobjectstorage-unserialize-function/)
* [`SplObjectStorage::valid()`](https://www.geeksforgeeks.org/php-splobjectstorage-valid-function/)

## SplQueue 函数
* [`SplQueue::__construct()`](https://www.geeksforgeeks.org/php-splqueue__construct-function/)
* [`SplQueue::dequeue()`](https://www.geeksforgeeks.org/php-splqueue-dequeue-function/)
* [`SplQueue::enqueue()`](https://www.geeksforgeeks.org/php-splqueue-enqueue-function/)