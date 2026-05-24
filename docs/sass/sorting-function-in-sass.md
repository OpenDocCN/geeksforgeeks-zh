# SASS 中的排序功能

> 原文:[https://www.geeksforgeeks.org/sorting-function-in-sass/](https://www.geeksforgeeks.org/sorting-function-in-sass/)

任何排序函数的主要功能是能够比较两个字符串，并检查两个字符串中的哪一个必须在另一个之前。几乎每种编程语言都有一些内置的排序函数，但是要在 Sass 中做到这一点，您需要创建自己的字符串比较函数。第一步，我们需要教 Sass，根据每个字符串包含的字符对字符串进行排序的正确顺序。我们用一个变量来实现。

```html
$sort-order: a b c d e f g h i j k l m n o p 
             q r s t u v w x y z !default;
```

这将用于声明以 **a** 开头的字符串应该出现在以 **b 或 c** 开头的字符串之前，以此类推。您还可以添加其他值，如数字、大写字母或符号。
现在，你需要一个比较功能。在比较函数中，我们基本上遍历每个字符串中的字符，并在 Sass **index()** 函数的帮助下，在排序列表中查找它们的顺序。它会给我们两个可以比较的值，其中一个在另一个之前。如果值相同，我们将循环下一组字符，以此类推。
如果$string-a 在$string-b 之前，则 **str-compare()** 函数返回 true，否则返回 false。

```html
@function compare($string-a, $string-b, $sort-order) {
  $string-a: to-lower-case($string-a + unquote(""));
  $string-b: to-lower-case($string-b + unquote(""));      

  @for $i from 1 through min(
          str-length($string-a), str-length($string-b)) {

    $char-a: str-slice($string-a, $i, $i);
    $char-b: str-slice($string-b, $i, $i);

    @if $char-a and $char-b and index(
           $order, $char-a) != index($sort-order, $char-b) {
      @return index(
           $sort-order, $char-a) < index($sort-order, $char-b);
    }
  }

  @return str-length($string-a) < str-length($string-b);
}
```

这里，我们将使用**冒泡排序**算法进行排序，因为这是最基本和最简单的方法。由于[冒泡排序](https://www.geeksforgeeks.org/bubble-sort/)是基于交换数组或列表中的两个值，我们还需要一个**交换()**函数。
swap()函数将一个列表和两个索引值作为输入。需要在列表中交换索引值。
我们将使用 **set-nth()** 函数，因为它只是更新列表，而不是创建新列表。

```html
@function swap($list, $index-a, $index-b) {
  @if abs($index-a) > length($list) or
               abs($index-b) > length($list) {
    @return $list;
  }
  $temp: nth($list, $index-a);
  $list: set-nth($list, $index-a, nth($list, $index-b));
  $list: set-nth($list, $index-b, $temp);
  @return $list;
}
```

现在，我们有了一个 **compare()** 函数和一个 **swap()** 函数，这意味着我们已经准备好创建我们的 **sort()** 函数。该函数只是循环遍历列表，相互比较项目，并将它们交换一次，直到列表完全排序。

```html
@function sort($list, $sort-order) {
  @for $i from 1 through length($list) {
  @for $j from $i * -1 through -1 {
      $j: abs($j);
      @if $j > 1 and compare(nth($list, $j),
                  nth($list, $j - 1), $sort-order) {
        $list: swap($list, $j, $j - 1);
      }
    }
  }
  @return $list;
}
```

最后，我们需要传递字符串值并返回 sort()函数。

```html
$list: internships placements classes geeksforgeeks courses;
$sort: sort($list);
```

输出:

```html
classes courses geeksforgeeks internships placements

```