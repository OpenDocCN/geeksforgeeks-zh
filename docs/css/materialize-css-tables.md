# 物化 CSS |表格

> 原文:[https://www.geeksforgeeks.org/materialize-css-tables/](https://www.geeksforgeeks.org/materialize-css-tables/)

表格是组织大量数据的一种很好且简单的方式。物化 CSS 提供了一些工具类来设置表格的样式。除了改善移动体验，手机屏幕宽度上的所有表格都自动居中。以下是表格的样式:

*   **Stripped Table:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>

        <!--Import Google Icon Font-->
        <link href=
    "https://fonts.googleapis.com/icon?family=Material+Icons"
            rel="stylesheet">

        <!-- Compiled and minified CSS -->
        <link rel="stylesheet" href=
    "https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.5/css/materialize.min.css">

        <!--Let browser know website is 
            optimized for mobile-->
        <meta name="viewport" content=
            "width=device-width, initial-scale=1.0" />
    </head>

    <body>
        <table class="striped">
            <thead>
                <tr>
                    <th>Student</th>
                    <th>Study Time(days)</th>
                    <th>Marks</th>
                </tr>
            </thead>

            <tbody>
                <tr>
                    <td>Atul</td>
                    <td>2</td>
                    <td>80</td>
                </tr>
                <tr>
                    <td>Aman</td>
                    <td>4</td>
                    <td>71</td>
                </tr>
                <tr>
                    <td>Ansh</td>
                    <td>2</td>
                    <td>98</td>
                </tr>
                <tr>
                    <td>John</td>
                    <td>5</td>
                    <td>96</td>
                </tr>
            </tbody>
        </table>

        <!-- Compiled and minified JavaScript -->
        <script src=
    "https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.5/js/materialize.min.js">
        </script>
    </body>

    </html>
    ```

    **输出:**

    ![](img/8135ee257e803cc47c893a0e45ead51e.png)

*   **Bordered Table:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <!--Import Google Icon Font-->
        <link href=
    "https://fonts.googleapis.com/icon?family=Material+Icons"
            rel="stylesheet">

        <!-- Compiled and minified CSS -->
        <link rel="stylesheet" href=
    "https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.5/css/materialize.min.css">

        <!--Let browser know website is
            optimized for mobile-->
        <meta name="viewport" content=
            "width=device-width, initial-scale=1.0" />
    </head>

    <body>
        <table class="bordered">
            <thead>
                <tr>
                    <th>Student</th>
                    <th>Study Time(days)</th>
                    <th>Marks</th>
                </tr>
            </thead>

            <tbody>
                <tr>
                    <td>Atul</td>
                    <td>2</td>
                    <td>80</td>
                </tr>
                <tr>
                    <td>Aman</td>
                    <td>4</td>
                    <td>71</td>
                </tr>
                <tr>
                    <td>Ansh</td>
                    <td>2</td>
                    <td>98</td>
                </tr>
                <tr>
                    <td>John</td>
                    <td>5</td>
                    <td>96</td>
                </tr>
            </tbody>
        </table>

        <!-- Compiled and minified JavaScript -->
        <script src=
    "https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.5/js/materialize.min.js">
        </script>
    </body>

    </html>
    ```

    **输出:**

    ![](img/f4226c5248a3d711b4eb58d80f1a2bf5.png)

*   **Highlighted Table:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <!--Import Google Icon Font-->
        <link href=
    "https://fonts.googleapis.com/icon?family=Material+Icons"
            rel="stylesheet">

        <!-- Compiled and minified CSS -->
        <link rel="stylesheet" href=
    "https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.5/css/materialize.min.css">

        <!--Let browser know website is 
            optimized for mobile-->
        <meta name="viewport" content=
            "width=device-width, initial-scale=1.0" />
    </head>

    <body>
        <table class="highlight">
            <thead>
                <tr>
                    <th>Student</th>
                    <th>Study Time(days)</th>
                    <th>Marks</th>
                </tr>
            </thead>

            <tbody>
                <tr>
                    <td>Atul</td>
                    <td>2</td>
                    <td>80</td>
                </tr>
                <tr>
                    <td>Aman</td>
                    <td>4</td>
                    <td>71</td>
                </tr>
                <tr>
                    <td>Ansh</td>
                    <td>2</td>
                    <td>98</td>
                </tr>
                <tr>
                    <td>John</td>
                    <td>5</td>
                    <td>96</td>
                </tr>
            </tbody>
        </table>

        <!-- Compiled and minified JavaScript -->
        <script src=
    "https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.5/js/materialize.min.js">
        </script>
    </body>

    </html>
    ```

    **输出:**

    ![](img/1d182529e521f32dbda6bb667246a8d5.png)

*   **Centered Table:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <!--Import Google Icon Font-->
        <link href=
    "https://fonts.googleapis.com/icon?family=Material+Icons"
            rel="stylesheet">

        <!-- Compiled and minified CSS -->
        <link rel="stylesheet" href=
    "https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.5/css/materialize.min.css">

        <!--Let browser know website is 
            optimized for mobile-->
        <meta name="viewport" content=
            "width=device-width, initial-scale=1.0" />
    </head>

    <body>
        <table class="centered">
            <thead>
                <tr>
                    <th>Student</th>
                    <th>Study Time(days)</th>
                    <th>Marks</th>
                </tr>
            </thead>

            <tbody>
                <tr>
                    <td>Atul</td>
                    <td>2</td>
                    <td>80</td>
                </tr>
                <tr>
                    <td>Aman</td>
                    <td>4</td>
                    <td>71</td>
                </tr>
                <tr>
                    <td>Ansh</td>
                    <td>2</td>
                    <td>98</td>
                </tr>
                <tr>
                    <td>John</td>
                    <td>5</td>
                    <td>96</td>
                </tr>
            </tbody>
        </table>

        <!-- Compiled and minified JavaScript -->
        <script src=
    "https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.5/js/materialize.min.js">
        </script>
    </body>

    </html>
    ```

    **输出:**

    ![](img/67017a3d09ec072a3ae12040a7b19de1.png)

*   **Responsive Table:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <!--Import Google Icon Font-->
        <link href=
    "https://fonts.googleapis.com/icon?family=Material+Icons"
            rel="stylesheet">

        <!-- Compiled and minified CSS -->
        <link rel="stylesheet" href=
    "https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.5/css/materialize.min.css">

        <!--Let browser know website is 
            optimized for mobile-->
        <meta name="viewport" content=
            "width=device-width, initial-scale=1.0" />
    </head>

    <body>
        <table class="responsive-table">
            <thead>
                <tr>
                    <th>Student</th>
                    <th>Study Time(days)</th>
                    <th>Marks</th>
                </tr>
            </thead>

            <tbody>
                <tr>
                    <td>Atul</td>
                    <td>2</td>
                    <td>80</td>
                </tr>
                <tr>
                    <td>Aman</td>
                    <td>4</td>
                    <td>71</td>
                </tr>
                <tr>
                    <td>Ansh</td>
                    <td>2</td>
                    <td>98</td>
                </tr>
                <tr>
                    <td>John</td>
                    <td>5</td>
                    <td>96</td>
                </tr>
            </tbody>
        </table>

        <!-- Compiled and minified JavaScript -->
        <script src=
    "https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.5/js/materialize.min.js">
        </script>
    </body>

    </html>
    ```

    **听着:**

    ![](img/347b28cf8a50025ceebc7db79a14cb59.png)