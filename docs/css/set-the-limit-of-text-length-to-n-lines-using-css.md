# 使用 CSS

将文本长度限制设置为 N 行

> 原文:[https://www . geesforgeks . org/set-将文本长度限制为 n 行-使用-css/](https://www.geeksforgeeks.org/set-the-limit-of-text-length-to-n-lines-using-css/)

可以使用 CSS 将文本长度限制在![N](img/19e409e13c1238e1f3ff3dbd06cdd45e.png "Rendered by QuickLaTeX.com")行。这就是所谓的线夹紧或多线截断。

可能有两种情况:

*   **Truncating text after 1 line**: If you need to truncate text after 1 line then the **text-overflow** property of CSS can be used. It creates ellipses and gracefully cut off words.

    ```html
    div{
      white-space: nowrap; 
      overflow: hidden;
      text-overflow: ellipsis;
    }

    ```

    下面的代码演示了 CSS 的**文本溢出**属性:

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title></title>

        <style>
            .text{
                white-space: nowrap; 
                overflow: hidden;
                text-overflow: ellipsis;
            }
        </style>
    </head>

    <body>
        <div class="text">
            Hello GeeksforGeeks. A Computer Science portal for geeks.
            It contains well written, well thought articles. 
            This is a paragraph containing multiple lines.
        </div>
    </body>
    </html>                    
    ```

*   **Truncating text after more than 1 line**: If you need to truncate text after more than 1 line then you will have to use WebKit. Webkit is the html/css rendering engine used in Apple’s Safari browser, and in Google’s Chrome.

    使用网络工具包的各种问题包括:

    1.  WebKit 仅在某些浏览器中受支持。它仅受谷歌 chrome 和苹果 Safari 浏览器支持，不受 Internet Explorer、微软 Edge、Firefox 或 Opera Mini 支持。
    2.  它有时会切断单词的最后几个字母，因此它不会只在空格处断开。
    3.  在网络工具包中，省略号没有替代选项，也就是说，除了省略号之外，您不能在截断行的末尾使用任何东西。

    ```html
    .text{
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        line-height: 16px;    
        max-height: 32px;     
        -webkit-line-clamp: 2; /* Write the number of 
                                  lines you want to be 
                                  displayed */
        -webkit-box-orient: vertical;
    }

    ```

    下面的代码演示了使用 WebKit 截断 N 行:

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title></title>

        <style>
            .text{
                overflow: hidden;
                text-overflow: ellipsis;
                display: -webkit-box;
                line-height: 16px; 
                max-height: 32px;     

                /* The number of lines to be displayed */
                -webkit-line-clamp: 2; 
                -webkit-box-orient: vertical;
            }
        </style>    
    </head>

    <body>
        <div class="text">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, 
            sed do eiusmod tempor incididunt ut labore et dolore 
            magna aliqua. Ut enim ad minim veniam, quis nostrud 
            exercitation ullamco laboris nisi ut aliquip ex ea 
            commodo consequat. Duis aute irure dolor in reprehenderit 
            in voluptate velit esse cillum dolore eu fugiat nulla 
            pariatur. Excepteur sint occaecat cupidatat non proident, 
            sunt in culpa qui officia deserunt mollit anim id est 
            laborum.Lorem ipsum dolor sit amet, consectetur adipisicing 
            elit, sed do eiusmod tempor incididunt ut labore et dolore 
            magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation 
            ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis 
            aute irure dolor in reprehenderit in voluptate velit esse 
            cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat 
            cupidatat non proident, sunt in culpa qui officia deserunt 
            mollit anim id est laborum.
        </div>
    </body>
    </html>                    
    ```

    Opera 网络浏览器有自己的方式来处理这种情况。它在文本被截断的那一行应用省略号。

    ```html
    .text{
        overflow: hidden;
        white-space: normal;
        height: 1.2em; /* exactly 2 lines */
        text-overflow: -o-ellipsis-lastline;
    }

    ```

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title></title>
        <style>
            .text{
                overflow: hidden;
                white-space: normal;

                /* Exactly 2 lines are displayed. 
                    Height of 1 line is 1.2em*/
                height: 2.4em; 
                text-overflow: -o-ellipsis-lastline;
            }
        </style>
    </head>

    <body>
        <div class="text">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, 
            sed do eiusmod tempor incididunt ut labore et dolore magna 
            aliqua. Ut enim ad minim veniam, quis nostrud exercitation
            ullamco laboris nisi ut aliquip ex ea commodo consequat. 
            Duis aute irure dolor in reprehenderit in voluptate velit 
            esse cillum dolore eu fugiat nulla pariatur. Excepteur 
            sint occaecat cupidatat non proident, sunt in culpa qui 
            officia deserunt mollit anim id est laborum.Lorem ipsum 
            dolor sit amet, consectetur adipisicing elit, sed do 
            eiusmod tempor incididunt ut labore et dolore magna aliqua.
            t enim ad minim veniam, quis nostrud exercitation ullamco 
            laboris nisi ut aliquip ex ea commodo consequat. Duis aute 
            irure dolor in reprehenderit in voluptate velit esse cillum 
            dolore eu fugiat nulla pariatur. Excepteur sint occaecat 
            cupidatat non proident, sunt in culpa qui officia deserunt 
            mollit anim id est laborum.
        </div>
    </body>
    </html>                    
    ```