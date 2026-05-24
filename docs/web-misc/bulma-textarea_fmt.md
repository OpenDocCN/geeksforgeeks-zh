# Bulma Textarea

> 哎哎哎:# t0]https://www . geeksforgeeks . org/bulma-textarea/

`Bulma`是一个基于`Flexbox`的免费开源`CSS`框架。它是组件丰富的，兼容的，并且有很好的文档记录。它本质上是高度反应的。它使用类来实现它的设计。
表单的“文本区”组件在外观上没有那么吸引人。使用`Bulma`，我们可以通过添加一些简单的`Bulma`类，以更好的方式设计表单的文本区元素。`Bulma` `textarea`元素有不同的颜色、不同的样式、不同的大小和不同的状态。

## 示例 1: 简单的布尔玛文本区

```html
<html>
  <head>
    <title>Bulma Textarea</title>
    <link rel='stylesheet'
          href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 80px;
      }
    </style>
  </head>
  <body>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-5'>
          <div class="field">
            <div class="control">
              <textarea class="textarea"
                        placeholder='Normal Textarea'>
              </textarea>
            </div>
          </div>
        </div>
      </div>
    </div>
  </body>
</html>
```

**输出:**

![](img/5aa34bc3a08f73450a868dd74769e240.png)

## 示例 2: 不同颜色的文本区域

```html
<html>
  <head>
    <title>Bulma Textarea</title>
    <link rel='stylesheet'
          href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 80px;
      }
    </style>
  </head>
  <body>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-5'>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-primary"
                        placeholder='Primary Textarea'>
              </textarea>
            </div>
          </div>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-link"
                        placeholder='Link Textarea'>
               </textarea>
            </div>
          </div>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-info"
                        placeholder='Info Textarea'>
             </textarea>
            </div>
          </div>
        </div>

        <div class='column is-5'>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-success"
                        placeholder='Success Textarea'>
              </textarea>
            </div>
          </div>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-warning"
                        placeholder='Warning Textarea'>
              </textarea>
            </div>
          </div>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-danger"
                        placeholder='Danger Textarea'>
               </textarea>
            </div>
          </div>
        </div>
      </div>
    </div>
  </body>
</html>
```

**输出:**

![](img/917101cfa8a15068b8be34ae28377585.png)

## 示例 3: 不同大小的文本区域

```html
<html>
  <head>
    <title>Bulma Textarea</title>
    <link rel='stylesheet'
          href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 80px;
      }
    </style>
  </head>
  <body>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-5'>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-small"
                        placeholder='small Textarea'>
              </textarea>
            </div>
          </div>
          <div class="field">
            <div class="control">
              <textarea class="textarea"
                        placeholder='Normal Textarea'>
              </textarea>
            </div>
          </div>
        </div>

        <div class='column is-5'>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-medium"
                        placeholder='Medium Textarea'>
              </textarea>
            </div>
          </div>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-large"
                        placeholder='Large Textarea'>
              </textarea>
            </div>
          </div>
        </div>
      </div>
    </div>
  </body>
</html>
```

**输出:**

![](img/081bbb5629fd2d854c7a7cc8eb8e7ce5.png)

## 示例 4: textarea 的不同状态

```html
<html>
  <head>
    <title>Bulma Textarea</title>
    <link rel='stylesheet'
          href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 80px;
      }
    </style>
  </head>
  <body>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-5'>
          <div class="field">
            <div class="control">
              <textarea class="textarea"
                        placeholder='Normal Textarea'>
              </textarea>
            </div>
          </div>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-focused"
                        placeholder='Focused Textarea'>
               </textarea>
            </div>
          </div>
        </div>

        <div class='column is-5'>
          <div class="field">
            <div class="control">
              <textarea class="textarea is-hovered"
                        placeholder='Hovered Textarea'>
              </textarea>
            </div>
          </div>
          <div class="field">
            <div class="control is-loading">
              <textarea class="textarea"
                        placeholder='Loading Textarea'>
             </textarea>
            </div>
          </div>
        </div>
      </div>
    </div>
  </body>
</html>
```

**输出:**

![](img/ba26c2c50608149e06de6185f66ad237.png)

## 示例 5: 只读文本区域

```html
<html>
  <head>
    <title>Bulma Textarea</title>
    <link rel='stylesheet'
          href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 80px;
      }
    </style>
  </head>
  <body>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-5'>
          <div class="field">
            <div class="control">
              <textarea class="textarea"
                        placeholder=
                          "I am content of Readonly
Textarea, You can't write me" readonly></textarea>
            </div>
          </div>
      </div>
    </div>

  </body>
</html>
```

**输出:**

![](img/ecc50f8d4c42f137e5a79cbeb94c453c.png)

## 示例 6: 禁用的文本区域

```html
<html>
  <head>
    <title>Bulma Textarea</title>
    <link rel='stylesheet'
          href=
'https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 80px;
      }
    </style>
  </head>
  <body>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-5'>
          <div class="field">
            <div class="control">
              <textarea col='20'
                        class="textarea"
                        placeholder='Disabled Textarea'
                               disabled>
               </textarea>
            </div>
          </div>
      </div>
    </div>

  </body>
</html>
```

**输出:**

![](img/b8bd753f9421e82a3e8968239718b79a.png)