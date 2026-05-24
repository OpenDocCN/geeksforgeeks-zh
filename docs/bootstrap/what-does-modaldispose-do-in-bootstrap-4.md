# 什么起作用。Bootstrap 4 中的 modal('dispose ')做什么？

> 原文:[https://www . geesforgeks . org/what-do-modaldispose-do-in-bootstrap-4/](https://www.geeksforgeeks.org/what-does-modaldispose-do-in-bootstrap-4/)

在引导程序 4 中，**。模态(‘dispose’)**是一个定义为**破坏**模态的函数。即使使用了**，模态**仍然是 DOM** 的一部分。模态(' dispose')** ，此功能仅**破坏模态组件的当前实例**。

**语法:**

```html
$("#*modalID*").modal("dispose");
```

**示例:**此示例说明了的使用。modal('dispose ')方法。当点击*处置按钮*时，模态组件的 jQuery 实例被删除。因此，单击按钮后，其他模态函数都不起作用。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Dispose Modal</title>
    <meta charset="UTF-8">
    <link rel="stylesheet" 
          href=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css">
    <script src=
"https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js">
  </script>
    <script src=
"https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js">
  </script>
    <script src=
"https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js">
  </script>
</head>

<body>
    <button id="clickBtn" 
            class="btn btn-primary">
      Click Me!
  </button>

    <div id="myModal" class="modal fade">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">Example Modal</h5>
                    <button id="dismissBtn"
                            type="button"
                            class="close">
                        <span aria-hidden="true">×</span>
                    </button>
                </div>
                <div class="modal-body">
                    Body of the Modal
                </div>
                <div class="modal-footer">
                    <button id="closeBtn"
                            class="btn btn-secondary">
                      Close
                  </button>
                    <button id="disposeBtn"
                            class="btn btn-secondary">
                      Dispose
                  </button>
                </div>
            </div>
        </div>
    </div>
</body>

<script>
    $(document).ready(function() {
        $("#clickBtn").click(function() {
            $("#myModal").modal('show');
        });
        $("#dismissBtn").click(function() {
            $("#myModal").modal('hide');
        });
        $("#closeBtn").click(function() {
            $("#myModal").modal('hide');
        });
        $("#disposeBtn").click(function() {
            $("#myModal").modal('dispose');
        });
    });
</script>

</html>
```

**输出:**
![](img/7534024a211121c0e2a0f1b3012e7e52.png)

**注意:**要在使用 dispose 函数后关闭 modal，我们可以修改上面的代码来隐藏 modal，并在销毁它的同时删除 fade 类。

```html
$("#disposeBtn").click(function(){
     $("#myModal").removeClass('fade').modal('hide');
     $("#myModal").modal("dispose");
});

```