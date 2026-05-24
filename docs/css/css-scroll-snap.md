# CSS |滚动捕捉

> 原文:[https://www.geeksforgeeks.org/css-scroll-snap/](https://www.geeksforgeeks.org/css-scroll-snap/)

**CSS 滚动捕捉**是一个内置模块。它将滚动快照位置引入 web 技术。当滚动操作完成时，滚动容器的滚动端口工作。这个模块在 HTML 5 中是新的，在此之前有一个类似的模块叫做**滚动捕捉点**，它已经被这个**滚动捕捉**模块移除和替换了。

“滚动快照”模块中有两种类型的属性，一种用于容器，另一种用于这些容器的子级。

**容器上的 CSS 属性:**

| attribute | describe |
| Scroll-snap type | This property defines how strict it is to force snap points on the scroll container. |
| Scroll-capture-stop | This property defines whether the scroll container is allowed to "pass over" possible snap positions. |
| [Scroll-Fill] | This attribute defines all scroll-fill-* |
| Scroll-Fill-Top | The abbreviated property of. This property defines the offset of the top of the best viewing area of the scroll port. |
| [Scroll-Fill-Right] | This property defines the offset to the right of the best viewing area of the scrolling window. |
| Scroll-Fill-Bottom | This property defines the offset at the bottom of the scroll bar's best viewing area. |
| [Scroll-Fill-Left] | This property defines the offset to the left of the best viewing area of the scrolling window. |
| Scroll-Fill-Inline | This attribute is a short attribute, which is used to set the roll-fill long axis of the inline dimension. |
| Scroll-Fill-Inline-Start | This property defines the offset of the starting edge in the inline dimension of the best viewing area of the scrolling window. |
| Scroll-Fill-Inline-End | This property defines the offset of the end edge in the inline size of the best viewing area of the scrolling window. |
| Rolling filling block | This attribute is a short attribute, which is used to set the long axis of rolling filling of block dimension. |
| Scroll-Fill-Block-Start | This property defines the offset of the starting edge in the block dimension of the best viewing area of the scrolling window. |
| Scroll-Fill-Block-End | This property defines the offset of the end edge in the block size of the best viewing area of the scrolling window. |

**子对象上的 CSS 属性:**

| attribute | describe |
| Scroll-snap-align | This property defines the snap position of the box as the alignment of its snap area. |
| Rolling boundary | This attribute is a shorthand attribute that defines all rolling boundaries. |
| [Scroll-Margin-Top] | This property defines the top margin of the scrolling alignment area used to align this box with the alignment port. |
| [Scroll-Margin-Right] | This property defines the right margin of the scrolling alignment area, which is used to align the box to the alignment port. |
| [Scroll-Margin-Bottom] | This property defines the bottom margin of the scrolling alignment area used to align this box with the alignment port. |
| Scroll-Margin-Left | This property defines the left margin of the scrolling alignment area, which is used to align this box to the alignment port. |
| [Rolling Margin-Inline] | This property is a shorthand property, which is used to set the scroll margin of inline dimension. |
| Scroll-Margin-Inline-Start | This property defines the margin of the rolling snap area at the beginning of the inline dimension. |
| Scroll-Margin-Inline-End | This property defines the margin of the rolling snap area at the end of the inline dimension. |
| Scroll margins-blocks | This attribute is a shorthand attribute, which is used to set the scrolling margin of the block dimension. |
| Scroll-Margin-Block-Start | This property defines the margin of the scrolling snap area at the beginning of the block size. |
| Scroll-Margin-End of Block | This property defines the margin of the scrolling snap area at the end of the block size. |

**支持的浏览器:****滚动快照模块**支持的浏览器如下: