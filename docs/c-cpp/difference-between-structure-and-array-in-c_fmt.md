# C 中结构和数组的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-structure-and-array-in-c/](https://www.geeksforgeeks.org/difference-between-structure-and-array-in-c/)

## [C 中的数组](https://www.geeksforgeeks.org/arrays-in-c-cpp/)

[数组](https://www.geeksforgeeks.org/arrays-in-c-cpp/)是存储在连续存储位置的项目集合。

![arrays](img/13b7429b646a58c1b6e67867ce0dab9c.png)

## [结构在 C](https://www.geeksforgeeks.org/structures-c/)

[结构](https://www.geeksforgeeks.org/structures-c/)是 C/C++ 中用户自定义的数据类型。结构创建的数据类型可用于将可能不同类型的项组合成单一类型。

![](img/a6704d86c3eb342c495c08554c6774d4.png)

**结构与数组的区别**

| 排列 | 结构 |
| --- | --- |
| `ARRAY` refers to a collection of elements of homogeneous data type. | `Structure` refers to a collection of elements of heterogeneous data types. |
| Use array subscript or `[]` (square brackets) for element access. | Use the structure `.`(dot operator) to access elements. |
| The array is a pointer to the first element of the collection. | Not a structure pointer. |
| Instantiation of an array is impossible. | Instantiation of the structure is possible. |
| The array size is fixed, which is basically the number of elements multiplied by the size of one element. | The size of the structure is not fixed, because each element of the structure can have different types and sizes. |
| Bit fields are not possible in arrays. | Bit fields are possible in the structure. |
| Array declaration is simply done by using `[]` instead of any keyword. | Complete the structure declaration with the help of `struct` keyword. |
| Array is non-primitive data type. | Structure is a user-defined data type. |
| Array traversal and search are simple and quick. | Traversing and searching are complex and slow. |
| `data_type array_name[size];` | `struct struct_name { data_type1 ele1; data_type2 ele2 };` |
| Elements are stored in contiguous memory locations. | Elements may or may not be stored in consecutive storage units. |
| The array is accessed by its index number through subscripts. | Structure elements are accessed by name by using dot operators. |