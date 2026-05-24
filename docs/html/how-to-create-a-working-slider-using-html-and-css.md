# 如何使用 HTML 和 CSS 创建工作滑块？

> 原文:[https://www . geeksforgeeks . org/如何使用 html 和 css 创建工作滑块/](https://www.geeksforgeeks.org/how-to-create-a-working-slider-using-html-and-css/)

滑块是序列中可以分别遍历的一组帧。本文展示了仅使用 HTML 和 CSS 构建幻灯片的方法。

首先，输入基本的 HTML 代码，然后使用 type 作为单选按钮为框架添加单选按钮。然后，按顺序实现帧的设计。在左边距的帮助下，可以使用单选按钮和控件标签来调整和遍历框架。在框架中，也可以包含图像而不是文本。这样，浏览器消耗更少的内存和计算能力。

给定一个 HTML 和 CSS 文档来创建一个滑块。

**第一部分:**该部分包含页面的 HTML 部分。必须显示的幻灯片用相应的文本定义。

**HTML 代码:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <div id="frame">
        <input type="radio" name="frame" id="frame1" checked />
        <input type="radio" name="frame" id="frame2" />
        <input type="radio" name="frame" id="frame3" />
        <input type="radio" name="frame" id="frame4" />
        <div id="slides">
            <div id="overflow">
                <div class="inner">
                    <div class="frame frame_1">
                        <div class="frame-content">
                            <h2>Slide 1</h2>
                        </div>
                    </div>
                    <div class="frame frame_2">
                        <div class="frame-content">
                            <h2>Slide 2</h2>
                        </div>
                    </div>
                    <div class="frame frame_3">
                        <div class="frame-content">
                            <h2>Slide 3</h2>
                        </div>
                    </div>
                    <div class="frame frame_4">
                        <div class="frame-content">
                            <h2>Slide 4</h2>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div id="controls">
            <label for="frame1"></label>
            <label for="frame2"></label>
            <label for="frame3"></label>
            <label for="frame4"></label>
        </div>
        <div id="bullets">
            <label for="frame1"></label>
            <label for="frame2"></label>
            <label for="frame3"></label>
            <label for="frame4"></label>
        </div>
    </div>
</body>

</html>
```

**第二部分:**该部分包括所有用于制作幻灯片的样式。用于移动每张幻灯片的动画是通过设置每张幻灯片所需的左边距属性来定义的。这使它看起来像是在每张幻灯片之间平滑过渡。

**CSS 代码:**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
#frame {
    margin: 0 auto;
    width: 800px;
    max-width: 100%;
    text-align: center;
}

#frame input[type=radio] {
    display: none;
}

#frame label {
    cursor: pointer;
    text-decoration: none;
}

#slides {
    padding: 10px;
    border: 5px solid #0F0;
    background: #00F;
    position: relative;
    z-index: 1;
}

#overflow {
    width: 100%;
    overflow: hidden;
}

#frame1:checked~#slides .inner {
    margin-left: 0;
}

#frame2:checked~#slides .inner {
    margin-left: -100%;
}

#frame3:checked~#slides .inner {
    margin-left: -200%;
}

#frame4:checked~#slides .inner {
    margin-left: -300%;
}

#slides .inner {
    transition: margin-left 800ms 
        cubic-bezier(0.770, 0.000, 0.175, 1.000);
    width: 400%;
    line-height: 0;
    height: 300px;
}

#slides .frame {
    width: 25%;
    float: left;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    color: #FFF;
}

#slides .frame_1 {
    background: #90C;
}

#slides .frame_2 {
    background: #F90;
}

#slides .frame_3 {
    background: #606;
}

#slides .frame_4 {
    background: #C00;
}

#controls {
    margin: -180px 0 0 0;
    width: 100%;
    height: 50px;
    z-index: 3;
    position: relative;
}

#controls label {
    transition: opacity 0.2s ease-out;
    display: none;
    width: 50px;
    height: 50px;
    opacity: .4;
}

#controls label:hover {
    opacity: 1;
}

#frame1:checked~#controls label:nth-child(2),
#frame2:checked~#controls label:nth-child(3),
#frame3:checked~#controls label:nth-child(4),
#frame4:checked~#controls label:nth-child(1) {
    background: 
url(https://image.flaticon.com/icons/svg/130/130884.svg) no-repeat;
    float: right;
    margin: 0 -50px 0 0;
    display: block;
}

#frame1:checked~#controls label:nth-last-child(2),
#frame2:checked~#controls label:nth-last-child(3),
#frame3:checked~#controls label:nth-last-child(4),
#frame4:checked~#controls label:nth-last-child(1) {
    background: 
url(https://image.flaticon.com/icons/svg/130/130882.svg) no-repeat;
    float: left;
    margin: 0 0 0 -50px;
    display: block;
}

#bullets {
    margin: 150px 0 0;
    text-align: center;
}

#bullets label {
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 100%;
    background: #ccc;
    margin: 0 10px;
}

#frame1:checked~#bullets label:nth-child(1),
#frame2:checked~#bullets label:nth-child(2),
#frame3:checked~#bullets label:nth-child(3),
#frame4:checked~#bullets label:nth-child(4) {
    background: #444;
}

@media screen and (max-width: 900px) {
    #frame1:checked~#controls label:nth-child(2),
    #frame2:checked~#controls label:nth-child(3),
    #frame3:checked~#controls label:nth-child(4),
    #frame4:checked~#controls label:nth-child(1),
    #frame1:checked~#controls label:nth-last-child(2),
    #frame2:checked~#controls label:nth-last-child(3),
    #frame3:checked~#controls label:nth-last-child(4),
    #frame4:checked~#controls label:nth-last-child(1) {
        margin: 0;
    }
    #slides {
        max-width: calc(100% - 140px);
        margin: 0 auto;
    }
}
```

**完成代码:**这里我们将以上两个部分合并为一个，完成上述任务。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <style>
        #frame {
            margin: 0 auto;
            width: 800px;
            max-width: 100%;
            text-align: center;
        }

        #frame input[type=radio] {
            display: none;
        }

        #frame label {
            cursor: pointer;
            text-decoration: none;
        }

        #slides {
            padding: 10px;
            border: 5px solid #0F0;
            background: #00F;
            position: relative;
            z-index: 1;
        }

        #overflow {
            width: 100%;
            overflow: hidden;
        }

        #frame1:checked~#slides .inner {
            margin-left: 0;
        }

        #frame2:checked~#slides .inner {
            margin-left: -100%;
        }

        #frame3:checked~#slides .inner {
            margin-left: -200%;
        }

        #frame4:checked~#slides .inner {
            margin-left: -300%;
        }

        #slides .inner {
            transition: margin-left 800ms 
                cubic-bezier(0.770, 0.000, 0.175, 1.000);
            width: 400%;
            line-height: 0;
            height: 300px;
        }

        #slides .frame {
            width: 25%;
            float: left;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100%;
            color: #FFF;
        }

        #slides .frame_1 {
            background: #90C;
        }

        #slides .frame_2 {
            background: #F90;
        }

        #slides .frame_3 {
            background: #606;
        }

        #slides .frame_4 {
            background: #C00;
        }

        #controls {
            margin: -180px 0 0 0;
            width: 100%;
            height: 50px;
            z-index: 3;
            position: relative;
        }

        #controls label {
            transition: opacity 0.2s ease-out;
            display: none;
            width: 50px;
            height: 50px;
            opacity: .4;
        }

        #controls label:hover {
            opacity: 1;
        }

        #frame1:checked~#controls label:nth-child(2),
        #frame2:checked~#controls label:nth-child(3),
        #frame3:checked~#controls label:nth-child(4),
        #frame4:checked~#controls label:nth-child(1) {
            background: 
url(https://image.flaticon.com/icons/svg/130/130884.svg) no-repeat;
            float: right;
            margin: 0 -50px 0 0;
            display: block;
        }

        #frame1:checked~#controls label:nth-last-child(2),
        #frame2:checked~#controls label:nth-last-child(3),
        #frame3:checked~#controls label:nth-last-child(4),
        #frame4:checked~#controls label:nth-last-child(1) {
            background: 
url(https://image.flaticon.com/icons/svg/130/130882.svg) no-repeat;
            float: left;
            margin: 0 0 0 -50px;
            display: block;
        }

        #bullets {
            margin: 150px 0 0;
            text-align: center;
        }

        #bullets label {
            display: inline-block;
            width: 10px;
            height: 10px;
            border-radius: 100%;
            background: #ccc;
            margin: 0 10px;
        }

        #frame1:checked~#bullets label:nth-child(1),
        #frame2:checked~#bullets label:nth-child(2),
        #frame3:checked~#bullets label:nth-child(3),
        #frame4:checked~#bullets label:nth-child(4) {
            background: #444;
        }

        @media screen and (max-width: 900px) {

            #frame1:checked~#controls label:nth-child(2),
            #frame2:checked~#controls label:nth-child(3),
            #frame3:checked~#controls label:nth-child(4),
            #frame4:checked~#controls label:nth-child(1),
            #frame1:checked~#controls label:nth-last-child(2),
            #frame2:checked~#controls label:nth-last-child(3),
            #frame3:checked~#controls label:nth-last-child(4),
            #frame4:checked~#controls label:nth-last-child(1) {
                margin: 0;
            }

            #slides {
                max-width: calc(100% - 140px);
                margin: 0 auto;
            }
        }
    </style>
</head>

<body>
    <div id="frame">
        <input type="radio" name="frame" id="frame1" checked />
        <input type="radio" name="frame" id="frame2" />
        <input type="radio" name="frame" id="frame3" />
        <input type="radio" name="frame" id="frame4" />
        <div id="slides">
            <div id="overflow">
                <div class="inner">
                    <div class="frame frame_1">
                        <div class="frame-content">
                            <h2>Slide 1</h2>
                        </div>
                    </div>
                    <div class="frame frame_2">
                        <div class="frame-content">
                            <h2>Slide 2</h2>
                        </div>
                    </div>
                    <div class="frame frame_3">
                        <div class="frame-content">
                            <h2>Slide 3</h2>
                        </div>
                    </div>
                    <div class="frame frame_4">
                        <div class="frame-content">
                            <h2>Slide 4</h2>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div id="controls">
            <label for="frame1"></label>
            <label for="frame2"></label>
            <label for="frame3"></label>
            <label for="frame4"></label>
        </div>
        <div id="bullets">
            <label for="frame1"></label>
            <label for="frame2"></label>
            <label for="frame3"></label>
            <label for="frame4"></label>
        </div>
    </div>
</body>

</html>
```

**输出:**

<video class="wp-video-shortcode" id="video-521007-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201118224052/geeks_original.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201118224052/geeks_original.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201118224052/geeks_original.mp4)</video>