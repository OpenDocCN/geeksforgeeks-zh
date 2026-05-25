
# JS 转义序列| HTML 实体

> 原文: [https://www.geeksforgeeks.org/js-escape-sequence-html-entity/](https://www.geeksforgeeks.org/js-escape-sequence-html-entity/)

HTML 中的某些符号似乎总是会破坏你的程序。这些包括数学、货币、希腊字母符号等。要么它们在你的键盘或浏览器中不可用，以不同于你想要的方式解释它们。这里列出了不同符号的 HTML 代码和相同的 JavaScript 转义序列。

## 特殊符号:

<figure class="table">
| 【char】 | [html code] | 【js 转义序列】 |
| --- | --- | --- |
| 33 | &amp;#33; | \u0021 |
| 34 | &amp;#34; | \u0022 |
| 35 | &amp;#35; | \u0023 |
| 36 | &amp;#36; | \u0024 |
| % | &amp;#37; | \u0025 |
| & | &amp;#38; | \u0026 |
| 39 | &amp;#39; | \u0027 |
| （ | &amp;#40; | \u0028 |
| ） | &amp;#41; | \u0029 |
| < | \u003c |
| > | \u003e |
</figure>

## 大写字母:

所有从 A 开始到 Z 结束的字母都有专门的 HTML 代码和 JS 转义序列。在 HTML 中，它们以 A 开始，以 Z 结束，在 JavaScript 中，它们从 A 增加到 I，分别为\u0041 到\u0048，然后从 J 到 O 表示变为\u004A 到\u004F。然后从 P 到 Y，数值从\u0055 增加到\u0059。最后，对于 Z，我们有\u005A。

<figure class="table">
| 茶 | HTML code | JS escape sequence |
| --- | --- | --- |
| A | 65 | \u0041 |
| B | 66 | \u0042 |
| C | 67 | \u0043 |
| D | 68 | \u0044 |
| E | 69 | \u0045 |
| F | 70 | \u0046 |
| G | 71 | \u0047 |
| H | 72 | \u0048 |
| I | 73 | \u0049 |
| J | 74 | \u004A |
| K | 75 | \u004B |
| L | 76 | \u004C |
| M | 77 | \u004D |
| N | 78 | \u004E |
| O | 79 | \u004F |
| P | 80 | \u0050 |
| Q | 81 | \u0051 |
| R | 82 | \u0052 |
| S | 83 | \u0053 |
| T | 84 | \u0054 |
| U | 85 | \u0055 |
| V | 86 | \u0056 |
| W | 87 | \u0057 |
| X | 88 | \u0058 |
| Y | 89 | \u0059 |
| Z | 90 | \u005A |
</figure>

## 数字:

所有从 0 开始到 9 结束的数字都有特殊的 HTML 代码和 JavaScript 转义序列。在 HTML 中，它们以 0 开始，以 &amp;#57 结束；在 JavaScript 中，它们从 0030 开始，到 0039 结束。

<figure class="table">
| 茶 | HTML code | JS escape sequence |
| --- | --- | --- |
| Zero | 48 | \u0030 |
| one | 49 | \u0031 |
| Two | 50 | \u0032 |
| three | 51 | \u0033 |
| four | 52 | \u0034 |
| five | 53 | \u0035 |
| six | 54 | \u0036 |
| seven | 55 | \u0037 |
| eight | 56 | \u0038 |
| nine | 57 | \u0039 |
</figure>

## 小字母:

所有以“a”开头，以“z”结尾的字母都有专门的 HTML 代码和 JavaScript 转义序列。在 HTML 中，它们以 a 开头，以 z 结尾，在 JavaScript 中，它们分别从“a”增加到“I”，从\u0061 增加到\u0069，然后从“j”增加到“o”，表示形式变为\u006A 到\u006F。然后从“p”到“y”，数值从\u0070 增加到\u0079。最后，对于 z，我们有\u007A。

<figure class="table">
| 茶 | HTML code | JS escape sequence |
| --- | --- | --- |
| a | 97 | \u0061 |
| b | 98 | \u0062 |
| c | 99 | \u0063 |
| d | 100 | \u0064 |
| e | 101 | \u0065 |
| f | 102 | \u0066 |
| g | 103 | \u0067 |
| h | 104 | \u0068 |
| i | 105 | \u0069 |
| j | 106 | \u006A |
| k | 107 | \u006B |
| l | 108 | \u006C |
| m | 109 | \u006D |
| n | 110 | \u006E |
| o | 111 | \u006F |
| p | 112 | \u0070 |
| q | 113 | \u0071 |
| r | 114 | \u0072 |
| s | 115 | \u0073 |
| t | 116 | \u0074 |
| u | 117 | \u0075 |
| v | 118 | \u0076 |
| w | 119 | \u0077 |
| x | 120 | \u0078 |
| y | 121 | \u0079 |
| z | 122 | \u007A |
</figure>

## 数学符号

<figure class="table">
|  | degree | &amp;#176; |
|  | [infinity] | &amp;#8734; |
|  | 【per-1000】 | &amp;#215; |
|  | &amp;#8745; | &amp;#8745; |
|  | [plus-minus] | &amp;#177; |
|  | [Hermione field] | &amp;#8800; |
| —— |  | &amp;#8722; |
|  |  | &amp;#8730; |
|  | [Micro (mu)] | &amp;#956; |
|  | [falsum] | &amp;#8743; |
|  | [Parallel] | &amp;#8741; |
</figure>
