# 使用 JavaScript 在 HTML 中创建一个范围滑块

> 原文:[https://www . geesforgeks . org/creating-range-slider-html-using-JavaScript/](https://www.geeksforgeeks.org/creating-range-slider-html-using-javascript/)

范围滑块用于网页，允许用户指定一个数值，该数值必须不小于一个给定值，并且不大于另一个给定值。也就是说，它允许从表示为滑块的范围中选择值。
范围滑块通常使用滑块或拨号盘控件来表示，而不是像“数字”输入类型那样的文本输入框。当不需要输入精确的数值时使用。例如，flipkart.com 产品列表的“过滤器”菜单中的价格滑块

**创建范围滑块**

我们可以通过以下步骤使用简单的 HTML 和 JavaScript 创建一个范围滑块:

**步骤 1:** 创建一个 HTML 元素。
在此步骤中，使用“div”元素定义滑块元素，该元素下是一个输入字段，其范围定义在 1 到 100 之间。

```html
<div class="rangeslider">
  <input type="range" min="1" max="100" value="10"
                 class="myslider" id="sliderRange">
</div>
```

**第二步:**给滑块元素添加 CSS。

1.  Define the width of the outside container.

    ```html
    .rangeslider{
        width: 50%;
        }

    ```

2.  定义滑块的 CSS，如滑块的高度、宽度、背景、不透明度等。

    ```html
    .myslider {
        -webkit-appearance: none;
        background: #FCF3CF  ;
        width: 50%;
        height: 20px;
        opacity: 2;
       }

    ```

3.  添加鼠标悬停效果。

    ```html
    .myslider:hover {
        opacity: 1;
    }

    ```

4.  为浏览器添加 WebKit 以更改范围滑块的默认外观。

    ```html
    .myslider::-webkit-slider-thumb {
        -webkit-appearance: none;
        cursor: pointer;
        background: #34495E  ;
        width: 5%;
        height: 20px;
    }

    ```

**步骤 3:** 向滑块元素添加 JavaScript。
添加下面的 JavaScript 代码来显示默认的滑块值。

```html
var rangeslider = document.getElementById("sliderRange");
var output = document.getElementById("demo");
output.innerHTML = rangeslider.value;

rangeslider.oninput = function() {
  output.innerHTML = this.value;
}

```

**第四步:结合以上要素。**

```html
<!DOCTYPE html>
<html>
<style>

.rangeslider{
    width: 50%;
}

.myslider {
    -webkit-appearance: none;
    background: #FCF3CF  ;
    width: 50%;
    height: 20px;
    opacity: 2;
   }

.myslider::-webkit-slider-thumb {
    -webkit-appearance: none;
    cursor: pointer;
    background: #34495E  ;
    width: 5%;
    height: 20px;
}

.myslider:hover {
    opacity: 1;
}

</style>
<body>

<h1>Example of Range Slider Using Javascript</h1>
<p>Use the slider to increment or decrement value.</p>

<div class="rangeslider">
  <input type="range" min="1" max="100" value="10"
                  class="myslider" id="sliderRange">
  <p>Value: <span id="demo"></span></p>
</div>

<script>
var rangeslider = document.getElementById("sliderRange");
var output = document.getElementById("demo");
output.innerHTML = rangeslider.value;

rangeslider.oninput = function() {
  output.innerHTML = this.value;
}
</script>

</body>
</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-169427-1" width="608" height="246" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/slidernew.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/slidernew.mp4](https://media.geeksforgeeks.org/wp-content/uploads/slidernew.mp4)</video>