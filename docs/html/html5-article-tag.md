# HTML5

<article>Tag</article>

> 原文：[https://www.geeksforgeeks.org/html5-article-tag/](https://www.geeksforgeeks.org/html5-article-tag/)

The **<article>** tag is one of the new sectioning element in HTML5\. The HTML strong<article> tag is used to represent an article. More specifically, the content within the <article> tag is independent of the other content of the site (even though it can be related).

In other words, The article element represents a component of a page that consists of self-contained composition in a document, page, or site. For Ex. in syndication.

**A potential source for Article Element are:**

*   A magazine/newspaper article
*   A blog entry
*   A forum post
*   A user-submitted a comment

**This tag is most often used in two contexts:**

*   On a page with a single piece of content, a single <article> element can be used to contain the main content and set it off from the rest of the page.
*   On a page with multiple pieces of content (a blog index page, a search results page, a category page, news feed), multiple <article> elements can be used to contain each individual piece of content.

Either way, it is similar to the <div> element and displays the stylish work the same. However, using the <article> element instead of <div> provides more semantic information to screen readers, search engines, and third-party applications.

**Note:** This tag does not render as anything special in a browser, you have to use CSS for that.

**Default CSS setting:** Most browsers will display the Article element with the following values.

## HTML

```html
<article> { 
    display:block; 
} 
```

**Example:** Using inline styling in an article element

## HTML

```html
<!DOCTYPE html>
<html>
  <body>
    <article
      style="
        width: 300px;
        border: 2px solid gray;
        padding: 10px;
        border-radius: 10px;
        margin: 5px;
      "
    >
      <img
        src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png"
        alt=""
        width="300"
        height="250"
        class="alignnone size-medium wp-image-560930"
      />
      <h1>GeeksforGeeks</h1>

<p>
        Sandeep Jain(FOUNDER) An IIT Roorkee alumnus and 
        founder of GeeksforGeeks. Apart from GeeksforGeeks, 
        he has worked with DE Shaw and Co. as a software 
        developer and JIIT Noida as an assistant professor.
      </p>

    </article>
  </body>
</html>
```

**Output:** 

![](img/ee74595ba41318727d2a674344ea53a3.png)

**Supported Browsers:** 

*   Google Chrome 6.0 and above
*   Internet Explorer 9.0 and above
*   Firefox 4.0 and above
*   Opera 11.1 and above
*   Safari 5.0 and above