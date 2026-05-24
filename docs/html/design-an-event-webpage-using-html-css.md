# 使用 HTML & CSS

设计一个事件网页

> 原文:[https://www . geesforgeks . org/design-an-event-网页-use-html-CSS/](https://www.geeksforgeeks.org/design-an-event-webpage-using-html-css/)

活动网页在活动的宣传和预订中起着至关重要的作用。在本文中，我们将构建一个活动页面，它将包含活动的详细信息，如日期、预订选项和查看更多详细信息按钮。我们将使用 HTML 给出基本布局，如标题，细节，按钮等。CSS 会给我们的布局一个漂亮的设计，像文本装饰，文本颜色，背景颜色，文本对齐，边距，填充，框浮动等。

**进场:**

*   我们将为左边的内容创建两个 div(它将包含事件的细节)，右边的一个将有 3 个包含事件摘要的框(如日期，查看更多按钮等)。).
*   包含设计的左侧部分有一个使用**<【h1】>**和 **< p >** 标签创建的标题和文本。右侧部分有 3 个框，包含–查看使用按钮创建的更多内容，使用 span 标签创建的时间。它还包含标题和段落。
*   在 CSS 部分，我们将使用(框大小)为左右部分创建框设计，使用过渡效果提供背景颜色、文本对齐、文本装饰和悬停效果。我们还将为悬停效果赋予不同的背景颜色

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <style>

        /* Styling the body */
        body {
            margin: 0;
            padding: 0;
        }

        /* Styling section, giving background
            image and dimensions */
        section {
            width: 100%;
            height: 100vh;
            background: 
 url('https://media.geeksforgeeks.org/wp-content/uploads/20210408155049/gfg9.png');
            background-size: cover;
        }

        /* Styling the left floatig section */
        section .leftBox {
            width: 50%;
            height: 100%;
            float: left;
            padding: 50px;
            box-sizing: border-box;
        }

        /* Styling the background of 
            left floatig section */
        section .leftBox .content {
            color: #fff;
            background: rgba(0, 0, 0, 0.5);
            padding: 40px;
            transition: .5s;
        }

        /* Styling the hover effect  
            of left floatig section */
        section .leftBox .content:hover {
            background: #e91e63;
        }

        /* Styling the header of left 
            floating section */
        section .leftBox .content h1 {
            margin: 0;
            padding: 0;
            font-size: 50px;
            text-transform: uppercase;
        }

        /* Styling the paragraph of 
            left floating section */
        section .leftBox .content p {
            margin: 10px 0 0;
            padding: 0;
        }

        /* Styling the three events section */
        section .events {
            position: relative;
            width: 50%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            float: right;
            box-sizing: border-box;
        }

        /* Styling the links of 
        the events section */
        section .events ul {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            margin: 0;
            padding: 40px;
            box-sizing: border-box;
        }

        /* Styling the lists of the event section */
        section .events ul li {
            list-style: none;
            background: #fff;
            box-sizing: border-box;
            height: 200px;
            margin: 15px 0;
        }

        /* Styling the time class of events section */
        section .events ul li .time {
            position: relative;
            padding: 20px;
            background: #262626;
            box-sizing: border-box;
            width: 30%;
            height: 100%;
            float: left;
            text-align: center;
            transition: .5s;
        }

        /* Styling the hover effect
            of events section */
        section .events ul li:hover .time {
            background: #e91e63;
        }

        /* Styling the header of time 
            class of events section */
        section .events ul li .time h2 {
            position: absolute;
            margin: 0;
            padding: 0;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: #fff;
            font-size: 60px;
            line-height: 30px;
        }

        /* Styling the texts of time 
        class of events section */
        section .events ul li .time h2 span {
            font-size: 30px;
        }

        /* Styling the details 
        class of events section */
        section .events ul li .details {
            padding: 20px;
            background: #fff;
            box-sizing: border-box;
            width: 70%;
            height: 100%;
            float: left;
        }

        /* Styling the header of the 
        details class of events section */
        section .events ul li .details h3 {
            position: relative;
            margin: 0;
            padding: 0;
            font-size: 22px;
        }

        /* Styling the lists of details 
        class of events section */
        section .events ul li .details p {
            position: relative;
            margin: 10px 0 0;
            padding: 0;
            font-size: 16px;
        }

        /* Styling the links of details
        class of events section */
        section .events ul li .details a {
            display: inline-block;
            text-decoration: none;
            padding: 10px 15px;
            border: 1.5px solid #262626;
            margin-top: 8px;
            font-size: 18px;
            transition: .5s;
        }

        /* Styling the details class's hover effect */
        section .events ul li .details a:hover {
            background: #e91e63;
            color: #fff;
            border-color: #e91e63;
        }
    </style>
</head>

<body>
    <section>
        <div class="leftBox">
            <div class="content">
                <h1>
                    Events and Shows
                </h1>
                <p>
                    With the idea of imparting programming 
                    knowledge, Mr. Sandeep Jain, an IIT 
                    Roorkee alumnus started a dream, 
                    GeeksforGeeks. Whether programming 
                    excites you or you feel stifled, 
                    wondering how to prepare for 
                    interview questions or
                    how to ace data structures and 
                    algorithms, GeeksforGeeks is a 
                    one-stop solution. With every 
                    tick of time, we are adding arrows 
                    in our quiver. From articles on 
                    various computer science subjects 
                    to programming problems for practice,
                    from basic to premium courses, from 
                    technologies to entrance examinations, 
                    we have been building ample content 
                    with superior quality. In a short 
                    span, we have built a community of 
                    1 Million+ Geeks around the world, 20,000+
                    Contributors and 500+ Campus Ambassadors 
                    in various colleges across the nation. 
                    Our success stories include a lot of 
                    students who benefitted in their 
                    placements and landed jobs at tech 
                    giants. Our vision is to build a gigantic
                    network of geeks and we are only a 
                    fraction of it yet.
                </p>
            </div>
        </div>

        <div class="events">
            <ul>
                <li>
                    <div class="time">
                        <h2>
                            15 <br><span>March</span>
                        </h2>
                    </div>
                    <div class="details">
                        <h3>
                            Where is the event happening?
                        </h3>
                        <p> 
                            With the idea of imparting programming 
                            knowledge, Mr. Sandeep Jain, an IIT 
                            Roorkee alumnus started a dream, 
                            GeeksforGeeks. Whether programming 
                            excites you or you feel stifled, 
                            how to ace data structures and 
                            algorithms, GeeksforGeeks is a 
                            one-stop solution.
                        </p>

                        <a href="#">View Details</a>
                    </div>
                    <div style="clear: both;"></div>
                </li>

                <li>
                    <div class="time">
                        <h2>
                            27 <br><span>May</span>
                        </h2>
                    </div>
                    <div class="details">
                        <h3>
                            Where is the event happening?
                        </h3>
                        <p>
                            With the idea of imparting programming 
                            knowledge, Mr. Sandeep Jain, an IIT 
                            Roorkee alumnus started a dream, 
                            GeeksforGeeks. Whether programming 
                            excites you or you feel stifled, 
                            how to ace data structures and 
                            algorithms, GeeksforGeeks is a 
                            one-stop solution.
                        </p>
                        <a href="#">View Details</a>
                    </div>
                    <div style="clear:both;"></div>
                </li>

                <li>
                    <div class="time">
                        <h2>
                            12 <br><span>August</span>
                        </h2>
                    </div>
                    <div class="details">
                        <h3>
                            Where is the event happening?
                        </h3>
                        <p>
                            With the idea of imparting programming 
                            knowledge, Mr. Sandeep Jain, an IIT 
                            Roorkee alumnus started a dream, 
                            GeeksforGeeks. Whether programming 
                            excites you or you feel stifled, 
                            how to ace data structures and 
                            algorithms, GeeksforGeeks is a 
                            one-stop solution.
                        </p>

                        <a href="#">View Details</a>
                    </div>
                    <div style="clear:both;"></div>
                </li>
            </ul>
        </div>
    </section>
</body>

</html>
```

**输出:**

![](img/ce1b9a6c256bdece22875b146c0a2560.png)