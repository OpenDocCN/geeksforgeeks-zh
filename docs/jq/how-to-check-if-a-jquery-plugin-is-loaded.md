# 如何检查是否加载了 jQuery 插件？

> 原文:[https://www . geesforgeks . org/如何检查是否加载了 jquery 插件/](https://www.geeksforgeeks.org/how-to-check-if-a-jquery-plugin-is-loaded/)

有多种方法可以让我们简单地检查 jQuery 插件是否使用 jQuery 成功加载。我们还可以检查插件中的特定功能是否可访问。本教程将演示如何检查是否加载了 jQuery 插件。

*   **步骤 1:** 使用 [npm](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 安装 [**浏览器同步**](https://www.browsersync.io/) 。我们将使用浏览器同步启动一个服务器，并提供一个网址来查看 HTML 网站，并使用内容交付网络加载 **jQuery** 。我们将在全球范围内安装浏览器同步。

    ```html
    npm install -g browser-sync
    ```

*   **第二步:**我们将在本教程中使用 [**jQuery-UI**](https://jqueryui.com/) 插件。我们将使用 jQuery 测试这个插件是否成功加载。下载这个插件的最新版本，并将其解压到您的项目根文件夹中。
*   **Step 3:** Create a **index.html** file
    **Example 1:** The jQuery plugins are namespaces on the jQuery scope. The **jquery-ui** plugin does not extend the **fn** namespace, hence we can check if the plugin is loaded successfully by using the above code. **ui** represents the name of the plugin and can be replaced with the plugin name to be checked. We have loaded jQuery in the **head** tag because it needs to be available before it can be used in the application. It is recommended practice to load all JavaScript files at the end of the **body** tag for increasing performance and render the page faster. Hence, we have used the **$(document).ready()** function before we can check if the plugin was loaded successfully or not. 
    The [**typeof**](https://www.geeksforgeeks.org/javascript-typeof-operator/) operator returns the data type of its operand in the form of a string. In this case, the operand is the **jQuery** **$** operator itself.

    ## 超文本标记语言

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>JQuery Plugin</title>
        <script src=
    "https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js">
        </script>
    </head>
    <body>
        <div>Hello GeeksForGeeks</div>
        <script type="text/javascript">
            $(document).ready(function () {
                if (typeof $.ui !== 'undefined') {
                    console.log('jquery-ui is loaded successfully')
                }         
            });
        </script>
        <script src="jquery-ui-1.12.1/jquery-ui.js" 
                type="text/javascript"></script>
    </body>
    </html>
    ```

    **示例 2:** 由于每个插件都保证有一些功能定义或值等同于**真**，我们可以使用代码中所示的较短版本。

    ## java 描述语言

    ```html
    if ($.ui) {
        console.log('jquery-ui is loaded successfully')
    }
    ```