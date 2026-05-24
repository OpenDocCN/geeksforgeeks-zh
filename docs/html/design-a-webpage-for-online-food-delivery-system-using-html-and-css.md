# 使用 HTML 和 CSS 设计在线送餐系统的网页

> 原文:[https://www . geesforgeks . org/design-a-web-for-online-food-delivery-system-use-html-and-CSS/](https://www.geeksforgeeks.org/design-a-webpage-for-online-food-delivery-system-using-html-and-css/)

在本文中，我们将学习如何使用 HTML 和 CSS 为在线食品配送系统制作一个完全响应的网页。

**使用的文件:**

*   index.html
*   contact.html
*   style.css

**index.html:** 下面的 html 代码描述了网页的结构。首先，它有一个标题标签来显示公司的名称，即“在线食品商店”。导航栏包含“主页”、“关于”、“菜单”和“联系人”选项卡。导航栏还包括公司的标志和背景图片，以及“在线美食商店”和特色产品的更多细节。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" 
     content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <link 
      href="https://fonts.googleapis.com/css2?
      family=Ubuntu+Mono&display=swap" 
      rel="stylesheet">    
</head>

<body>
    <header>
        <h1 id="top">Online</h1>
        <h1 id="top1">FoodShop</h1>
    </header>
    <hr>
    <nav id="navbar">
        <img src="5.jpeg">
        <ul id="navcontent">
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Menu</a></li>
            <li><a href="contact.html">ContactUs</a></li>
        </ul>
    </nav>
    <div id="container1">
        <div id="row1">
            Welcome to Online FoodShop
        </div>
        <button class="btn">ORDER NOW</button>
        <div id="container3">
            <div id="row2">
                <button class="btn">Prices</button>
            </div>
            <div id="row3">
                <button class="btn">Specials</button>
            </div>
        </div>
    </div>
    <hr>
    <h1 id="top3">Featured Products</h1>
    <div id="container4">
        <div id="row4">
            <button class="btn">ORDER NOW</button>
        </div>
        <div id="row5">
            <button class="btn">ORDER NOW</button>
        </div>
        <div id="row6">
            <button class="btn">ORDER NOW</button>
        </div>
    </div>
    <footer>Copyright © 2020-2021 OnlineFoodShop.
           All Rights are reserved</footer>
</body>
</html>
```

**contact.html:** 下面的 html 代码向我们描述了导航栏的“ContactUs”选项卡中有哪些内容。我们已经使用输入标签来输入查询的“查询”、“姓名”、“电子邮件-id”、“电话号码”和“解释”的类型。我们还使用单选按钮来询问客户的“在线食品商店”会员资格。该表单还提供了“提交”和“重置”按钮。

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <link rel="stylesheet" href="style.css">
    <title>ContactUs</title>
</head>

<body>
    <div id="ContactUs">
        <h1>Contact Us</h1>
        <form action="#">
            <div class="form-shape">
                <label for="query">
                    Type of Query
                </label>
                <select name="myQuery" id="query">
                    <option value="sel" selected>
                        Select
                    </option>
                    <option value="ord">
                        Order related Issues
                    </option>
                    <option value="Site">
                        Site related Issues
                    </option>
                    <option value="fed">
                        Complaint related Issues
                    </option>
                    <option value="others">
                        Others
                    </option>
                </select>
            </div>
            <div class="form-shape">
                <label for="name">Name</label>
                <input type="text" name="myName" 
                    id="name" 
                    placeholder="Enter your Name">
            </div>
            <div class="form-shape">
                <label for="email">Email-Id</label>
                <input type="email" name="myEmail" 
                    id="email" 
                    placeholder="Enter your email">
            </div>
            <div class="form-shape">
                <label for="pho">Phone Number</label>
                <input type="phone" name="myPhone" 
                    id="pho" 
                    placeholder="Enter your Phone no">
            </div>
            <div id="radio">
                Are you a member of OnlneFoodShop:
                Yes <input type="radio" name="eligible">
                No <input type="radio" name="eligible">
            </div>
            <div class="form-shape">
                <label for="message">
                    Ellaborate your query
                </label>
                <textarea name="mesg" id="message" 
                    cols="30" rows="10">
                </textarea>
            </div>
            <input type="submit" value="Submit">
            <input type="reset" value="Reset">
        </form>
    </div>
</body>

</html>
```

**style.css:** 这是样式表块，它为我们提供了网页的正确外观。

*   **头部样式:**由两个“头”标签组成。我们使用了*字体样式*“Ubuntu”来设计标题，我们还使用了适当的颜色来使一些文本看起来有吸引力。
*   **导航栏样式:**基本由 logo 样式和内容样式组成。首先，我们将导航栏视为一个弹性框，并将*弹性方向*指定为“列”。我们已经通过*显示将标志图像居中:块*。我们使用了*边距:自动*属性来居中图像。然后我们将导航栏的内容视为一个 flexbox，然后我们对其进行了适当的定位。
*   **Background image styling:** We used *before* pseudo selectors to set the respective background images.

    ```html
    /*CSS Reset*/
    *{
        margin:0px;
        padding:0px;
    }
    /*Header Styling*/

    #top{
        color:rgb(245, 10, 10);
        text-align:center;
        font-size:46px;
        font-family: 'Ubuntu Mono', monospace;
    }
    #top1{
        text-align:center;
        color:black;
        font-size:21px;
        font-family: 'Ubuntu Mono', monospace;
    }
    /* Navigation bar styling*/

    /*Navbar image styling*/
    #navbar img{
        display:block;
        width: 50px;
        height:50px;
        margin:auto;
        margin-bottom: 3px;
    }

    /*Navbar Functionality*/
    #navbar{
        display:flex;
        flex-direction: column;
        background-color: gray;
        height: 14vh;
        width: 100vw;
        font-family: 'Ubuntu Mono', monospace;
        margin-top:10px;
       border: 2px solid black;
       border-radius:15px;
    }

    /*Navbar content functionality*/
    #navcontent{
        display: flex;
        justify-content: center;
    }

    /*Navbar content styling*/
    ul li{
        list-style: none;
        margin: 15px;
        border-radius: 20px;
    }
    ul li a{
        padding: 1px;
        color:white;
        text-decoration: none;
        border-radius:10px;
    }
    ul li a:hover{
        background-color: red;
        border-radius: 10px;
    }

    /* website background image designing */
    #container1{
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100vw;
        height:63vh;
    }

    /*Setting the background image using before pseudo selector*/ 
    #container1::before{
        content:'';
        background: url("./1.jpg") no-repeat center center/cover;
        width: 100vw;
        height:59vh;
        position: absolute;
        top:0px;
        left: 0px;
        font-family: 'Ubuntu Mono', monospace;
        margin-right:45px;
        font-weight: bold;
        z-index: -1;
        opacity: 0.89;
        border: 2px solid black;
        border-bottom-left-radius: 100px;
    }

    #row1{
       color: black;
        font-weight:bold;
        font-size: 2rem;
        text-align: center;
        margin-top: 35px;
    }
    /*Button Styling*/
    .btn{
        margin-top:15px;
        border: 3px solid white;
        border-radius:15px;
        background-color:yellow;
        font-size:20px;
        font-weight: bold;
        font-family: 'Ubuntu Mono', monospace;
    }
    .btn:hover{
        cursor: pointer;
        background-color: red;
    }

    #container3{
        display: flex;
        justify-content: space-evenly;
    }
    #row2{
        width:24vw;
        height:21vh;
        box-shadow: 2px 7px 16px 19px;
         margin-top:51px;
         margin-bottom: 51px;
         display: flex;
        justify-content: center;
         align-items: flex-end;
         position: relative;
         margin-right: 38px;
         border-radius: 40px;
    }
    #row2::before{
        content: '';
        background: url('2.jpeg') no-repeat center center/cover;
        position: absolute;
        top: 0px;
        left:0px;
        width: 24vw;
        height:21vh;
        z-index: -1;
        border-radius: 40px;
    }
    #row3{
        position: relative;
        width: 24vw;
        height:21vh;
        display: flex;
        justify-content: center;
         align-items: flex-end;
         box-shadow: 2px 7px 16px 19px;
         margin-top:51px;
         margin-bottom: 51px;

         margin-left: 38px;
         border-radius: 40px;
    }
    #row3::before{
        content: '';
        background: url('3.jpeg') no-repeat center center/cover;
        position: absolute;
        top:0px;
        left:0px;
        width: 24vw;
        height:21vh;
        z-index: -1;
        border-radius: 40px;
    }

    #top3{
        text-align: center;
        color:red;
        font-family: 'Ubuntu Mono', monospace;
    }
    #container4{
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
        margin: 41px;
    }  
    #row4{
        width: 29vw;
        height: 360px;
        border: 2px solid black;
        background:url('a1.jpeg') no-repeat center center/cover; 
        display: flex;
        justify-content:center;
        align-items:flex-end;
        border-radius: 15px;
    }
    #row5{
        width: 29vw;
        height: 360px;
        border: 2px solid black;
        background:url('a2.jpeg') no-repeat center center/cover;
        display: flex;
        justify-content:center;
        align-items:flex-end;
        border-radius: 15px;
    }
    #row6{
        width: 30vw;
        height: 360px;
        border: 2px solid black;
        background:url('a3.jpeg') no-repeat center center/cover;
        display: flex;
        justify-content:center;
        align-items:flex-end;
        border-radius: 15px;
    }
    /*Designing the footer*/
    footer{
        text-align: center;
    }
    /*Designing of Contact Us*/
    #ContactUs{
        width:100vw;
        height:100vh;
        display:flex;
        flex-direction: column;
        align-items: center;
        background-color: gray;
    }
    .form-shape input, .form-shape select, .form-shape textarea{
       width: 92%;
       padding: 0.5rem;
    }
    /*Changing the color of placeholder*/
    ::placeholder{                  
        color:gray;
    }
    /*Making the webpage responsive using media queries*/
    @media only screen and (max-width:1131px){
        #row4{
            width: 42vw;
        }
        #row5{
            width:45vw;
        }
        #row6{
            margin-top: 20px;
            width:90vw;
        }
    }
    @media only screen and (min-width:600px) and (max-width:781px)
    {
        #row4{
            width:84vw;
            margin: auto;
            margin-left: 22px;
        }
        #row5{

            width:84vw;
            margin: auto;
            margin-top: 20px;
            margin-left: 22px;
        }
        #row6{
            width:84vw;
            margin: auto;
            margin-top: 20px;
            margin-left: 22px;
        }
    }
    @media only screen and (max-width:600px){
        #row4{
            width:78vw;
            margin: auto;
            margin-left: 3px;
        }
        #row5{

            width:78vw;
            margin: auto;
            margin-top: 20px;
            margin-left: 3px;
        }
        #row6{
            width:78vw;
            margin: auto;
            margin-top: 20px;
            margin-left: 3px;
        }
    }
    @media only screen and (min-height:1000px){
        #navbar{
            height:10vh;
        }
        #container1::before{
            height:39vh;
        }
        #container1{
            height:44vh
        }
    }

    ```

    **输出:**

    *   **15.6 英寸笔记本电脑:**<video class="wp-video-shortcode" id="video-515960-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201119123537/WhatsApp-Video-2020-11-19-at-11.28.52-AM.mp4?_=1">[https://media . geeksforgeeks . org/WP-content/uploads/20201119123537/WhatsApp-Video-2020-11-19-at-11 . 28 . 52-am . MP4](https://media.geeksforgeeks.org/wp-content/uploads/20201119123537/WhatsApp-Video-2020-11-19-at-11.28.52-AM.mp4)</video>T9】
    *   **iPhone 6/7/8 Plus:**<video class="wp-video-shortcode" id="video-515960-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201120015430/WhatsApp-Video-2020-11-20-at-1.53.32-AM.mp4?_=2">[https://media . geeksforgeeks . org/WP-content/uploads/20201120015430/WhatsApp-Video-2020-11-20-at-1 . 53 . 32-am . MP4](https://media.geeksforgeeks.org/wp-content/uploads/20201120015430/WhatsApp-Video-2020-11-20-at-1.53.32-AM.mp4)</video>
    *   **iPad Pro:**<video class="wp-video-shortcode" id="video-515960-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201120021319/WhatsApp-Video-2020-11-20-at-2.11.45-AM.mp4?_=3">[https://media . geeksforgeeks . org/WP-content/uploads/20201120021319/WhatsApp-Video-2020-11-20-at-2 . 11 . 45-am . MP4](https://media.geeksforgeeks.org/wp-content/uploads/20201120021319/WhatsApp-Video-2020-11-20-at-2.11.45-AM.mp4)</video>