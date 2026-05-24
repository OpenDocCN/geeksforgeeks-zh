# HTML、XML 和 DHTML 的区别

> 原文:[https://www . geesforgeks . org/区别-html-xml-and-dhtml/](https://www.geeksforgeeks.org/difference-between-html-xml-and-dhtml/)

**1。**[**HTML**](https://www.geeksforgeeks.org/html-tutorials/)

*   HTML stands for hypertext markup language.
*   Used to design the layout of documents and specify hyperlinks.
*   How high-speed browsers display text, pictures and other supporting media.
*   Support multimedia and new page layout functions.
*   Easy to integrate with other programming languages.
*   HTML consists of a series of elements.
*   Many tags are provided to control the presentation of information on the webpage, such as , < li >, < hr > and so on.

**<u>HTML 语法:</u>**

```html
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>

<h1>Hello World</h1>
<p>This is GeeksForGeeks portal.</p>

</body>
</html>
```

**2。**[**XML**](https://www.geeksforgeeks.org/xml-basics/)

*   XML stands for extensible markup language.
*   Markup language is a mechanism to identify document structure.
*   XML is designed to store and transmit data.
*   XML is designed to describe itself.
*   XML defines a standard way to add tags to documents.
*   Provides the ability to define tags and their structural relationships.
*   All semantics of XML documents are either defined by the application that processes them or by the stylesheet.

**<u>XML 语法:</u>**

```html
<note>
  <to>Geeks</to>
  <from>GeeksForGeeks</from>
  <heading>Welcome to new course</heading>
  <body>Don't forget to signup before this weekend!</body>
</note>
```

**3。**[**DHTML**](https://www.geeksforgeeks.org/dhtml-introduction/)

*   DHTML stands for dynamic HTML.
*   DHTML is a TERM used to describe the technology of making web pages dynamic and interactive.
*   DHTML refers to the content of the web page that changes every time you view it. For example, graphics can be moved from one location to another in response to user actions, such as mouse clicks.
*   Enable web pages to respond to user input without sending a request to a web server.
*   Describes the combination of HTML, stylesheets and scripts that allow animation of documents.

**<u>DHTML 语法:</u>**

```html
<html>
<head>
<script type="text/javascript">
function sameInfo()
{
for (i=0; i<document.myForm1.option.length; i++)
    {
    document.myForm2.option[i].value=document.myForm1.option[i].value;
    }
}
</script>
</head>
<body>

<form name="myForm1">
First name: <input type="text" name="option"><br />
Last name: <input type="text" name="option"><br />
Address: <input type="text" name="option"><br />
E-mail: <input type="text" name="option"><br />
<br />
<input type="button" onclick="sameInfo()" value="Same information below"><br />
</form>

<form name="myForm2">
First name: <input type="text" name="option"><br />
Last name: <input type="text" name="option"><br />
Address: <input type="text" name="option"><br />
E-mail: <input type="text" name="option"><br />
</form>

</body>
</html>
```