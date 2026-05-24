# 使用 HTML 和 CSS 设计日历

> 原文:[https://www . geesforgeks . org/design-a-calendar-use-html-and-CSS/](https://www.geeksforgeeks.org/design-a-calendar-using-html-and-css/)

在本文中，我们将使用 HTML 和 CSS 创建一个日历。首先，我们要对 HTML 略知一二。如果有人不知道 HTML 和 CSS，他们将无法使日历变得更好。本文的主要重点是 HTML 标签和我们将使用 CSS 的方式。

**方法:**首先我们将使用表标签，它将用于创建日历的结构。这将让我们了解如何使用 HTML 创建日历。稍后我们将应用一些 CSS 属性来使日历的设计更好。

**创建结构:**在本节中，我们将首先使用<表>标签创建日历的结构。这将有助于我们了解日历的结构。

## HTML

```html
<!DOCTYPE html>
<html>

<body>
    <!-- Here we are using attributes like
        cellspacing and cellpadding -->

    <!-- The purpose of the cellpadding is 
        the space that a user want between
        the border of cell and its contents-->

    <!-- cellspacing is used to specify the 
        space between the cell and its contents -->
    <h2 align="center" style="color: orange;">
        January 2021
    </h2>
    <br />

    <table bgcolor="lightgrey" align="center" 
        cellspacing="21" cellpadding="21">

        <!-- The tr tag is used to enter 
            rows in the table -->

        <!-- It is used to give the heading to the
            table. We can give the heading to the 
            top and bottom of the table -->

        <caption align="top">
            <!-- Here we have used the attribute 
                that is style and we have colored 
                the sentence to make it better 
                depending on the web page-->
        </caption>

        <!-- Here th stands for the heading of the
            table that comes in the first row-->

        <!-- The text in this table header tag will 
            appear as bold and is center aligned-->

        <thead>
            <tr>
                <!-- Here we have applied inline style 
                     to make it more attractive-->
                <th>Sun</th>
                <th>Mon</th>
                <th>Tue</th>
                <th>Wed</th>
                <th>Thu</th>
                <th>Fri</th>
                <th>sat</th>
            </tr>
        </thead>

        <tbody>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td>1</td>
                <td>2</td>
            </tr>
            <tr></tr>
            <tr>
                <td>3</td>
                <td>4</td>
                <td>5</td>
                <td>6</td>
                <td>7</td>
                <td>8</td>
                <td>9</td>
            </tr>
            <tr>
                <td>10</td>
                <td>11</td>
                <td>12</td>
                <td>13</td>
                <td>14</td>
                <td>15</td>
                <td>16</td>
            </tr>
            <tr>
                <td>17</td>
                <td>18</td>
                <td>19</td>
                <td>20</td>
                <td>21</td>
                <td>22</td>
                <td>23</td>
            </tr>
            <tr>
                <td>24</td>
                <td>25</td>
                <td>26</td>
                <td>27</td>
                <td>28</td>
                <td>29</td>
                <td>30</td>
            </tr>
            <tr>
                <td>31</td>
                <td>1</td>
                <td>2</td>
                <td>3</td>
                <td>4</td>
                <td>5</td>
                <td>6</td>
            </tr>
        </tbody>
    </table>
</body>

</html>
```