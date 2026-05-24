# 如何为 SASS 混合创建可选参数？

> 原文:[https://www . geeksforgeeks . org/如何创建可选参数-for-a-sass-mixin/](https://www.geeksforgeeks.org/how-to-create-optional-arguments-for-a-sass-mixin/)

要为 SASS @mixin 创建可选参数，必须传递声明的 mixin，并且应该包含它。

**下面的做法会解释清楚。**
**语法:**

```html
@mixin function-name($var1, $x:val){

/* stylesheet properties */
}
@include function-name(value, 0);

```

**方法:在@mixin 中赋值 Null 包括**

*   我们可以通过定义 mixin 的默认值来使它成为可选参数，该参数不通过@include 传递。
*   传递 null 或 0，或者不传递由 mixin 的@include 传递的参数，都会导致可选参数。
*   可选参数的变量名后跟冒号、和一个 SassScript 表达式

**示例 1:** 以下示例说明了上述方法。
T3】SASS 文件:style.scss

```html
/* Here $x:5px Optional Arguments*/
@mixin shadowbox($hoff, $voff, $blur, $spread, $color, $x:5px){
    -webkit-box-shadow: $hoff $voff $blur $spread $color;
    -moz-box-shadow: $hoff $voff $blur $spread $color;
    box-shadow: $hoff $voff $blur $spread $color;
    border: $x solid $color;
/* null is passed in mixin @include*/    
    div{
    @include shadowbox(0, 8px, 6px, -6px, black, null);
        display: block;
    }
```

**编译后的 CSS 文件:style.css**

```html
div{
    -webkit-box-shadow: 0 8px 6px -6px black;
    box-shadow: 0 8px 6px -6px black;
    border: 5px solid black;
    display: block;
  }
```

**示例 2:** 以下示例说明了上述方法。
T3】SASS 文件:style.scss

```html
/* Here $attach:fixed Optional Arguments*/
@mixin backgroundstretch( $bgsize, $attach:fixed ){
        background-attachment: $attach;
        background-position: center;
        -webkit-background-size: $bgsize;
        -moz-background-size: $bgsize;
        -o-background-size: $bgsize;
        background-size: $bgsize;
}
body {
        color:$grey;
    font-family: Helvetica, sans-serif;
    background-image: url('/img/backimg.jpg');
    background-repeat: no-repeat;
    /* 0 is passed in mixin @include*/    
    @include backgroundstretch(cover, 0);

}
```

**编译后的 CSS 文件:style.css**

```html
body {
  color: #919191;
  font-family: Helvetica, sans-serif;
  background-image: url("/img/backimg.jpg");
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
  background-size: cover;
}
```

**参考:**[https://sass-lang . com/documentation/at-rules/mixin #可选参数](https://sass-lang.com/documentation/at-rules/mixin#optional-arguments)