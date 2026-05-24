# Bulma | File

布尔玛是一个基于 Flexbox 的免费开源 CSS 框架。它是组件丰富的，兼容的，并且有很好的文档记录。它本质上是高度反应的。它使用类来实现它的设计。

**文件**元素用于上传自定义文件输入。“文件”组件由几个子元素组成，我们必须专门添加这些子元素才能很好地设计我们的内容。下面列出了这些元素。

*   `file-label`
*   `file-input` – 它是原生文件输入，为造型目的而隐藏。
    *   `file-cta` – 是上传的行动号召。
        *   `file-icon` – 是可选的上传图标
        *   `file-label` – “选择文件…”文本
    *   `file-name` – 所选文件名的容器。

## 示例 1

此示例显示了简单的布尔玛文件输入。

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Bulma File</title>
    <link rel='stylesheet' 
          href='https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 100px;
      }
    </style>
  </head>
  <body>
    <!-- font-awesome cdn -->
    <script src='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.0-2/js/all.min.js'>
    </script>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-5'>
          <div class="file">
            <label class="file-label">
              <input class="file-input" 
                     type="file" 
                     name="image">
              <span class="file-cta">
                <span class="file-icon">
                  <i class="fas fa-upload"></i>
                </span>
                <span class="file-label">
                  Choose a file…
                </span>
              </span>
            </label>
          </div>
        </div>
      </div>
    </div>
  </body>
</html>
```

### 输出

![](img/16b1142514c85b1b0356a3f9ab4ee00e.png)

简单文件输入

## 示例 2

该示例显示了将选定文件名包装在盒子容器中的文件输入。

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Bulma File</title>
    <link rel='stylesheet' 
          href='https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 100px;
      }
    </style>
  </head>
  <body>
    <!-- font-awesome cdn -->
    <script src='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.0-2/js/all.min.js'>
    </script>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-5'>
          <div class="file has-name">
            <label class="file-label">
              <input class="file-input" 
                     type="file" name="image">
              <span class="file-cta">
                <span class="file-icon">
                  <i class="fas fa-upload"></i>
                </span>
                <span class="file-label">
                  Choose a file…
                </span>
              </span>
              <span class="file-name">
                Nature-at-its-best.png
              </span>
            </label>
          </div>
        </div>
      </div>
    </div>
  </body>
</html>
```

### 输出

![](img/b8f9c6b968edd8d71f92e0953620449b.png)

具有选定文件名的文件输入

## 示例 3

本示例显示文件输入和所选文件名的不同对齐方式。

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Bulma File</title>
    <link rel='stylesheet' 
          href='https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 100px;
      }
      div.file{
        margin-bottom: 15px;
      }
      .file.is-right {
        justify-content:flex-start;
      }
    </style>
  </head>
  <body>
    <!-- font-awesome cdn -->
    <script src='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.0-2/js/all.min.js'>
    </script>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-5'>
          <div class="file has-name">
            <label class="file-label">
              <input class="file-input" 
                     type="file" name="image">
              <span class="file-cta">
                <span class="file-icon">
                  <i class="fas fa-upload"></i>
                </span>
                <span class="file-label">
                  Choose a file…
                </span>
              </span>
              <span class="file-name">
                Nature-at-its-best.png
              </span>
            </label>
          </div>
          <div class="file has-name is-right">
            <label class="file-label">
              <input class="file-input" 
                     type="file" 
                     name="image">
              <span class="file-cta">
                <span class="file-icon">
                  <i class="fas fa-upload"></i>
                </span>
                <span class="file-label">
                  Choose a file…
                </span>
              </span>
              <span class="file-name">
                Nature-at-its-best.png
              </span>
            </label>
          </div>
        </div>
      </div>
    </div>
  </body>
</html>
```

### 输出

![](img/0df733d857d4516ff4a79aedabe476d7.png)

不同的联盟文件输入

## 示例 4

该示例显示了不同的颜色文件输入。

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Bulma File</title>
    <link rel='stylesheet'
          href='https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 100px;
      }
      div.file{
        margin-bottom: 15px;
      }
      .file.is-right {
        justify-content:flex-start;
      }
    </style>
  </head>
  <body>
    <!-- font-awesome cdn -->
    <script src='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.0-2/js/all.min.js'>
    </script>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-5'>
          <div class="file has-name is-primary">
            <label class="file-label">
              <input class="file-input" 
                     type="file" name="image">
              <span class="file-cta">
                <span class="file-icon">
                  <i class="fas fa-upload"></i>
                </span>
                <span class="file-label">
                  Choose a file…
                </span>
              </span>
              <span class="file-name">
                Nature-at-its-best.png
              </span>
            </label>
          </div>
          <div class="file has-name is-link">
            <label class="file-label">
              <input class="file-input" 
                     type="file" 
                      name="image">
              <span class="file-cta">
                <span class="file-icon">
                  <i class="fas fa-upload"></i>
                </span>
                <span class="file-label">
                  Choose a file…
                </span>
              </span>
              <span class="file-name">
                Nature-at-its-best.png
              </span>
            </label>
          </div>
        </div>
      </div>
    </div>
  </body>
</html>
```

**输出:**

![](img/ba1fc328d2389fc6cfb234f344f53fdd.png)

### 不同的颜色文件输入

## 示例 5: 本示例显示了不同大小的文件输入。

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Bulma File</title>
    <link rel='stylesheet' 
          href='https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 100px;
      }

      div.file{
        margin-bottom: 15px;
      }

      .file.is-right {
        justify-content:flex-start;
      }
    </style>
  </head>
  <body>
    <!-- font-awesome cdn -->
    <script src='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.0-2/js/all.min.js'></script>   
    <div class='container'>
      <div class='columns is-mobile is-centered'>
        <div class='column is-6'>
          <div class="file has-name is-small">
            <label class="file-label">
              <input class="file-input" 
                     type="file" 
                     name="image">
              <span class="file-cta">
                <span class="file-icon">
                  <i class="fas fa-upload"></i>
                </span>
                <span class="file-label">
                  Small file...
                </span>
              </span>
              <span class="file-name">
                Nature-at-its-best.png
              </span>
            </label>
          </div>

          <div class="file has-name">
            <label class="file-label">
              <input class="file-input" 
                     type="file" 
                     name="image">
              <span class="file-cta">
                <span class="file-icon">
                  <i class="fas fa-upload"></i>
                </span>
                <span class="file-label">
                  Normal file...
                </span>
              </span>
              <span class="file-name">
                Nature-at-its-best.png
              </span>
            </label>
          </div>

          <div class="file has-name is-medium">
            <label class="file-label">
              <input class="file-input"
                     type="file" 
                     name="image">
              <span class="file-cta">
                <span class="file-icon">
                  <i class="fas fa-upload"></i>
                </span>
                <span class="file-label">
                  Medium file…
                </span>
              </span>
              <span class="file-name">
                Nature-at-its-best.png
              </span>
            </label>
          </div>

          <div class="file has-name is-large">
            <label class="file-label">
              <input class="file-input" 
                     type="file" 
                     name="image">
              <span class="file-cta">
                <span class="file-icon">
                  <i class="fas fa-upload"></i>
                </span>
                <span class="file-label">
                  Large file…
                </span>
              </span>
              <span class="file-name">
                Nature-at-its-best.png
              </span>
            </label>
          </div>

        </div>
      </div>
    </div>
  </body>
</html>
```

**输出:**

![](img/5f5f47be1cacf2f8f0b1e487f388acdb.png)

### 不同大小的文件输入

## 示例 6: 该示例显示了装箱块输入

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Bulma File</title>
    <link rel='stylesheet' 
          href='https://cdnjs.cloudflare.com/ajax/libs/bulma/0.7.5/css/bulma.css'>
    <!-- custom css -->
    <style>
      div.columns{
        margin-top: 100px;
      }

      div.file{
        margin-bottom: 15px;
      }
```

# 盒装文件上传组件示例

以下是一个使用 Bulma CSS 框架构建的文件上传组件示例，展示了六种不同颜色主题的盒装样式。

```html
</style>
</head>
<body>
    <!-- font-awesome cdn -->
    <script src='https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.12.0-2/js/all.min.js'></script>
    <div class='container'>
        <div class='columns is-mobile is-centered'>
            <div class='column is-3'>
                <div class="file has-name is-boxed is-primary">
                    <label class="file-label">
                        <input class="file-input" type="file" name="image">
                        <span class="file-cta">
                            <span class="file-icon">
                                <i class="fas fa-upload"></i>
                            </span>
                            <span class="file-label">
                                Choose file...
                            </span>
                        </span>
                        <span class="file-name">
                            Nature-at-its-best.png
                        </span>
                    </label>
                </div>
                <div class="file has-name is-boxed is-link">
                    <label class="file-label">
                        <input class="file-input" type="file" name="image">
                        <span class="file-cta">
                            <span class="file-icon">
                                <i class="fas fa-upload"></i>
                            </span>
                            <span class="file-label">
                                Choose file...
                            </span>
                        </span>
                        <span class="file-name">
                            Nature-at-its-best.png
                        </span>
                    </label>
                </div>
                <div class="file has-name is-boxed is-info">
                    <label class="file-label">
                        <input class="file-input" type="file" name="image">
                        <span class="file-cta">
                            <span class="file-icon">
                                <i class="fas fa-upload"></i>
                            </span>
                            <span class="file-label">
                                Choose file...
                            </span>
                        </span>
                        <span class="file-name">
                            Nature-at-its-best.png
                        </span>
                    </label>
                </div>
            </div>
            <div class='column is-3'>
                <div class="file has-name is-boxed is-success">
                    <label class="file-label">
                        <input class="file-input" type="file" name="image">
                        <span class="file-cta">
                            <span class="file-icon">
                                <i class="fas fa-upload"></i>
                            </span>
                            <span class="file-label">
                                Choose file...
                            </span>
                        </span>
                        <span class="file-name">
                            Nature-at-its-best.png
                        </span>
                    </label>
                </div>
                <div class="file has-name is-boxed is-warning">
                    <label class="file-label">
                        <input class="file-input" type="file" name="image">
                        <span class="file-cta">
                            <span class="file-icon">
                                <i class="fas fa-upload"></i>
                            </span>
                            <span class="file-label">
                                Choose file...
                            </span>
                        </span>
                        <span class="file-name">
                            Nature-at-its-best.png
                        </span>
                    </label>
                </div>
                <div class="file has-name is-boxed is-danger">
                    <label class="file-label">
                        <input class="file-input" type="file" name="image">
                        <span class="file-cta">
                            <span class="file-icon">
                                <i class="fas fa-upload"></i>
                            </span>
                            <span class="file-label">
                                Choose file...
                            </span>
                        </span>
                        <span class="file-name">
                            Nature-at-its-best.png
                        </span>
                    </label>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```

**输出:**

![](img/d7ebe036808bb5de6fd1f6898f58c49f.png)

**组件说明：**
*   该示例包含六个文件上传组件，分为两列布局。
*   每个组件使用 `file`、`has-name`、`is-boxed` 类，并搭配不同的颜色主题类：`is-primary`、`is-link`、`is-info`、`is-success`、`is-warning`、`is-danger`。
*   组件结构包含一个 `file-label`，其中包含 `file-input`、`file-cta`（内含上传图标和“Choose file...”文字）以及显示文件名的 `file-name`。