# 如何保证 HTML 的可读性？

> 原文:[https://www . geesforgeks . org/如何确保 html 的可读性/](https://www.geeksforgeeks.org/how-to-ensure-readability-of-html/)

一个简洁的 [HTML](https://www.geeksforgeeks.org/html-tutorials/) 代码节省了另一个开发人员的时间，也节省了你长时间浏览时的时间和精力。在有大型软件项目的公司里，你的代码应该是可读和可理解的，因为代码在某个时候必须被另一个人修改。

在本文中，我们将研究 3 个技巧来显著提高 HTML 和 JavaScript 代码的可读性。

1.  格式和缩进
2.  使用描述性名称
3.  避免不必要的评论

**格式化和缩进:**如果人们仔细查看你的 HTML 代码，他们肯定会注意到第一眼是否格式化不当。在大多数情况下，代码没有正确对齐或者格式不正确。开发人员总是喜欢干净的代码，对于某些人来说，缺少适当的格式会变得非常烦人。

*   **不良做法:**下面是一个合理的 HTML 代码片段，执行时不会出错。虽然这个片段是恰当的，但它对我们来说相当不和谐。仅仅是无法读取代码。一个人永远不可能一下子理解代码，他可能不会从代码中学到什么，而是开始解开它。

    ## 超文本标记语言

    ```html
    <!DOCTYPE html>
    <html><head><style>body{color:green;}</style></head><body><h1>GeeksforGeeks</h1>
    <p>A computer science portal for geeks</p></body></html>
    ```

*   **良好实践:**需要始终一致地应用格式。括号之间有适当缩进和间距的相同 HTML 代码现在看起来格式正确且干净。

    ## 超文本标记语言

    ```html
    <!DOCTYPE html>
    <html>
      <head>
        <style>
          body{
            color: green;
          }
        </style>
      </head>
      <body>
        <h1>GeeksforGeeks</h1>
        <p>A computer science portal for geeks</p>

      </body>
    </html>
    ```

**使用描述性名称:**应该可以写描述性的 [JavaScript 代码](https://www.geeksforgeeks.org/javascript-tutorial/)。即使是初学者也应该能够毫无问题地阅读您的代码，并理解其中试图实现或完成的内容。即使他们不清楚语法，他们也应该对正在发生的事情有很高的理解。下面是 JavaScript 中的一个反例。

*   **不良做法:**没有一定的背景，人们无法知道在这种情况下应该发生什么。如果我们用下面的代码通过使用描述性名称来更改上面的代码片段，那么就更容易理解其中发生了什么，即使我们没有任何上下文或函数描述作为注释。

    ## java 描述语言

    ```html
    function fn(o) {
      o.mk = 'Toyota';
    }

    var c = {mk: 'Honda', md: 'Accord', y: 1998};
    var x, y;

    x = c.mk;
    fn(c);
    y = c.mk;
    ```

*   **好做法:**仅仅根据变量和函数名，很明显我们是在更改一辆车的公司名。即使在第二个例子中使用了更多的字母，它肯定比第一个例子有更多的优点。

    ## java 描述语言

    ```html
    function ChangeCompany(car) {
      car.company = 'Toyota';
    }

    var car = {company: 'Honda', model: 'Accord', year: 1998};
    var car1, car2;

    car1 = car.company;
    ChangeCompany(car);
    car2 = car.company;
    ```

**避免不必要的注释:**为了避免混乱和混乱，我们还可以做的一件事是避免不必要的注释，并确保代码是自我解释的和充分的。这意味着我们应该尽量完全避免评论，并尽可能删除它们。唯一的例外是最相关的评论，甚至应该用最少的词来解释它们。

*   **不良做法:**下面是一些地方可能会发现的反例。在这个例子中，主要的问题是阅读它的人会从代码本身分心。多余的不必要的注释段落打乱了只有 3 行的实际代码。

    ## 超文本标记语言

    ```html
    <!DOCTYPE html>
    <html>
        <!--The <head> element is a container for metadata
        and is placed between the <html> tag and the <body>
        tag. Metadata is data about the HTML document
        and it is not displayed-->
        <head>
            <!--The <style> tag is used to define style
            information for a document. It is specified
            how HTML elements should render in a browser
            inside the <style>-->
            <style>
                body{ color: green; }
            </style>
        </head>
        <!--The <body> tag defines the document's body.
        The contents of an HTML document, such as
        headings, paragraphs, images, etc are contained
        inside the <body> element -->
        <body>
            <h1>GeeksforGeeks</h1>
            <p>A computer science portal for geeks</p>

        </body>
    </html>
    ```

*   **良好实践:**在上面的代码片段中，有 12 行注释，这意味着它更侧重于注释而不是实际代码。下面是写干净 HTML 代码的正确方法。

    ## 超文本标记语言

    ```html
    <!DOCTYPE html>
    <html>
        <head>
            <style>
                body{ color: green; }
            </style>
        </head>
        <body>
            <h1>GeeksforGeeks</h1>
            <p>A computer science portal for geeks</p>

        </body>
    </html>
    ```