# HTML |响应模式登录表单

> 原文:[https://www . geesforgeks . org/html-响应式-模态-登录-表单/](https://www.geeksforgeeks.org/html-responsive-modal-login-form/)

**响应登录表单**

**按照步骤使用 CSS 创建响应性登录表单。**

**第一步:添加 HTML**
在容器内添加图像，并为每个字段添加带有匹配标签的输入。在它们周围包装一个“表单”元素来处理输入。

**第二步:添加 CSS**
添加设计登录页面所需的 CSS 尽量保持设计简洁。

**程序:**这段代码将通过如何设计设计以及哪个属性用于创建哪个设计的注释来指导您。

```html
<!DOCTYPE html>
<html>
<style>
    /*set border to the form*/

    form {
        border: 3px solid #f1f1f1;
    }
    /*assign full width inputs*/

    input[type=text],
    input[type=password] {
        width: 100%;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #ccc;
        box-sizing: border-box;
    }
    /*set a style for the buttons*/

    button {
        background-color: #4CAF50;
        color: white;
        padding: 14px 20px;
        margin: 8px 0;
        border: none;
        cursor: pointer;
        width: 100%;
    }
    /* set a hover effect for the button*/

    button:hover {
        opacity: 0.8;
    }
    /*set extra style for the cancel button*/

    .cancelbtn {
        width: auto;
        padding: 10px 18px;
        background-color: #f44336;
    }
    /*centre the display image inside the container*/

    .imgcontainer {
        text-align: center;
        margin: 24px 0 12px 0;
    }
    /*set image properties*/

    img.avatar {
        width: 40%;
        border-radius: 50%;
    }
    /*set padding to the container*/

    .container {
        padding: 16px;
    }
    /*set the forgot password text*/

    span.psw {
        float: right;
        padding-top: 16px;
    }
    /*set styles for span and cancel button on small screens*/

    @media screen and (max-width: 300px) {
        span.psw {
            display: block;
            float: none;
        }
        .cancelbtn {
            width: 100%;
        }
    }
</style>

<body>

    <h2>Login Form</h2>
    <!--Step 1 : Adding HTML-->
    <form action="/action_page.php">
        <div class="imgcontainer">
            <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" 
                 alt="Avatar" class="avatar">
        </div>

        <div class="container">
            <label><b>Username</b></label>
            <input type="text" placeholder="Enter Username" name="uname" required>

            <label><b>Password</b></label>
            <input type="password" placeholder="Enter Password" name="psw" required>

            <button type="submit">Login</button>
            <input type="checkbox" checked="checked"> Remember me
        </div>

        <div class="container" style="background-color:#f1f1f1">
            <button type="button" class="cancelbtn">Cancel</button>
            <span class="psw">Forgot <a href="#">password?</a></span>
        </div>
    </form>

</body>

</html>
```

**输出:**
![](img/ecdd186fe0fef0d5d53a8b40ac958f16.png)

**按照步骤创建响应模式登录表单**

**第一步:添加 HTML。**
使用“表单”元素处理输入。然后为每个字段添加带有匹配标签的输入。

**STEP 2:添加 CSS**
添加设计登录页面所需的 CSS 尽量保持设计简洁。

**程序:**

```html
<!DOCTYPE html>
<html>
<style>

    /*assign full width inputs*/
    input[type=text],
    input[type=password] {
        width: 100%;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #ccc;
        box-sizing: border-box;
    }

    /*set a style for the buttons*/
    button {
        background-color: #4CAF50;
        color: white;
        padding: 14px 20px;
        margin: 8px 0;
        border: none;
        cursor: pointer;
        width: 100%;
    }

    /* set a hover effect for the button*/
    button:hover {
        opacity: 0.8;
    }

    /*set extra style for the cancel button*/
    .cancelbtn {
        width: auto;
        padding: 10px 18px;
        background-color: #f44336;
    }

    /*centre the display image inside the container*/
    .imgcontainer {
        text-align: center;
        margin: 24px 0 12px 0;
        position: relative;
    }

    /*set image properties*/
    img.avatar {
        width: 40%;
        border-radius: 50%;
    }

    /*set padding to the container*/
    .container {
        padding: 16px;
    }

    /*set the forgot password text*/
    span.psw {
        float: right;
        padding-top: 16px;
    }

    /*set the Modal background*/
    .modal {
        display: none;
        position: fixed;
        z-index: 1;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        overflow: auto;
        background-color: rgb(0, 0, 0);
        background-color: rgba(0, 0, 0, 0.4);
        padding-top: 60px;
    }

    /*style the model content box*/
    .modal-content {
        background-color: #fefefe;
        margin: 5% auto 15% auto;
        border: 1px solid #888;
        width: 80%;
    }

    /*style the close button*/
    .close {
        position: absolute;
        right: 25px;
        top: 0;
        color: #000;
        font-size: 35px;
        font-weight: bold;
    }

    .close:hover,
    .close:focus {
        color: red;
        cursor: pointer;
    }

    /* add zoom animation*/
    .animate {
        -webkit-animation: animatezoom 0.6s;
        animation: animatezoom 0.6s
    }

    @-webkit-keyframes animatezoom {
        from {
            -webkit-transform: scale(0)
        }
        to {
            -webkit-transform: scale(1)
        }
    }

    @keyframes animatezoom {
        from {
            transform: scale(0)
        }
        to {
            transform: scale(1)
        }
    }

    @media screen and (max-width: 300px) {
        span.psw {
            display: block;
            float: none;
        }
        .cancelbtn {
            width: 100%;
        }
    }
</style>

<body>

    <h2>Modal Login Form</h2>
    <!--Step 1 : Adding HTML-->
    <button onclick="document.getElementById('id01').style.display='block'" style="width:auto;">Login</button>

    <div id="id01" class="modal">

        <form class="modal-content animate" action="/action_page.php">
            <div class="imgcontainer">
                <span onclick="document.getElementById('id01').style.display='none'" class="close" title="Close Modal">×</span>
                <img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" alt="Avatar" class="avatar">
            </div>

            <div class="container">
                <label><b>Username</b></label>
                <input type="text" placeholder="Enter Username" name="uname" required>

                <label><b>Password</b></label>
                <input type="password" placeholder="Enter Password" name="psw" required>

                <button type="submit">Login</button>
                <input type="checkbox" checked="checked"> Remember me
            </div>

            <div class="container" style="background-color:#f1f1f1">
                <button type="button" onclick="document.getElementById('id01').style.display='none'" class="cancelbtn">Cancel</button>
                <span class="psw">Forgot <a href="#">password?</a></span>
            </div>
        </form>
    </div>

    <script>
        var modal = document.getElementById('id01');
        window.onclick = function(event) {
            if (event.target == modal) {
                modal.style.display = "none";
            }
        }
    </script>
</body>

</html>
```

**输出:**
![](img/5b01f0bc3ecea1794a752a13582351d4.png)

![](img/28dc8ce90a09b668f169fcb2b8e7c6a6.png)

HTML 是网页的基础，通过构建网站和网络应用程序用于网页开发。您可以通过以下 [HTML 教程](https://www.geeksforgeeks.org/html-tutorials/)和 [HTML 示例](https://www.geeksforgeeks.org/html-examples/)从头开始学习 HTML。