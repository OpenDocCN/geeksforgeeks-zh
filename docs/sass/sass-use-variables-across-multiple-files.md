# SASS |跨多个文件使用变量

> 原文:[https://www . geesforgeks . org/sass-use-variables-跨多个文件/](https://www.geeksforgeeks.org/sass-use-variables-across-multiple-files/)

*   在 SASS 中跨多个文件使用变量是通过 SASS 的@import 规则实现的。*   @导入规则，导入 Sass 和 CSS 样式表，用于提供变量，@ mixins 和函数。以便将所有样式表组合在一起，用于编译的 css。*   它还导入网址，如自举等框架..*   The @import no longer encouraged in future updates so prefer @use rule instead.

    **语法:**

    ```html
    /* importing name and file path is /_file.scss */
    @import 'file';

    ```

    *   **Approach 1:** Import multiple Sass partials
        *   要使用@import 导入多个 sass 部分，请添加@import，后跟引号内的第一个文件名，然后逗号(，)，再后跟以分号结尾的引号内的第二个文件名
        *   ```html
            /* importing name and file path is /_file1.scss and  /_file2.scss */
            @import 'file1', 'file2' ;

            ```

        **示例 1:** 以下示例说明了上述方法。
        T3】SASS 文件

        ```html
        /* _colors.scss */
        $primary:#00ff40;
        $secondary: #f44336;
        $tretiary:#03a9f4;
        $tera: #ffeb3b;
        $dark:#000000;
        $grey:#919191;
        $light:#dddddd;
        $white:#FFFFFF;

        /* _std.scss */
        html,
        body,
        ul,
        ol {
            margin: 0;
            padding: 0;
        }
        body {
                color:$grey;
            font-family: Helvetica, sans-serif;
            background-image: url('/img/backimg.jpg');
            background-repeat: no-repeat;
              background-attachment: fixed;
          background-position: center;
          background-size: cover;
            }

        /*_section.scss*/

        div{

            padding: {
                top: 20px;
                left: 10px;
                right: 10px;
                bottom: 20px;
                }
            h1{

                color: $secondary !important;
                align-items: center;

            }
          }
        /* style.scss*/
        @import 'colors';
        @import 'std', 'section';
        ```

        **编译后的 CSS 文件:** style.css

        ```html
        html,
        body,
        ul,
        ol {
          margin: 0;
          padding: 0;
        }

        body {
          color: #919191;
          font-family: Helvetica, sans-serif;
          background-image: url("/img/backimg.jpg");
          background-repeat: no-repeat;
          background-attachment: fixed;
          background-position: center;
          background-size: cover;
        }

        div {
          padding-top: 20px;
          padding-left: 10px;
          padding-right: 10px;
          padding-bottom: 20px;
        }

        div h1 {
          color: #f44336 !important;
          -webkit-box-align: center;
              -ms-flex-align: center;
                  align-items: center;
        }

        ```

    *   **Approach 2:** Import Plain CSS
        *   通过以下方式用@import 加载普通 CSS:
        *   @import 后跟扩展名为的 CSS 文件的路径。双引号内的 css。
        *   如果是网址路径，请填写在网址(" ")中指定的网址；
        *   ```html
            /* importing plain CSS*/
            @import "mytheme.css";
            @import "http://fonts.googleapis.com/css?family=Droid+Sans";
            @import url("http://fonts.googleapis.com/css?family=Droid+Sans");
            @import url(mytheme);
            @import "landscape" screen and (orientation: landscape);

            ```

        **示例 2:** 以下示例说明了上述方法。
        T3】SASS 文件: style.scss

        ```html
        @mixin google-font($family) {
          @import url("http://fonts.googleapis.com/css?family=#{$family}");
        }

        @include google-font("Serif Sans");
        ```

        **编译后的 CSS 文件:** style.css

        ```html
        @import url("http://fonts.googleapis.com/css?family=Serif Sans");
        ```

    *   **Approach 3:** Import Modules and configure Modules
        *   通过以下方式加载模块并用@import 配置模块:
        *   让事情变得简单。Sass 还支持仅导入文件，如下所示:
        *   _ filename.scss 导入为仅导入文件
            filename . import . SCS 作为

            ```html
            @forward "filename" as filename-*;

            ```

        *   万一@不建议使用这种方法。
        *   要配置模块，通过@import 通过定义与模块初始加载相关的全局变量来加载模块。

        **示例 3:**
        下面的示例说明了上面的方法。
        T4【SASS 文件】

        ```html
        /*_libray.scss */

        $purple:Purple;
        $white:white;
        button{
             color:$white;
             border-color:$purple;
             background-color:$purple;
             padding :10px;
        }

        /* _library.import.scss */

        @forward 'library' as lib-*;

        /* style.sass  */

        $lib-color: indigo;
        @import "library";
        ```

        **编译后的 CSS 文件:style.css**

        ```html
        button{
             color: white;
             border-color:indigo;
             background-color:indigo;
             padding :10px;
        }

        ```

**参考:**T2】https://sass-lang.com/documentation/at-rules/import