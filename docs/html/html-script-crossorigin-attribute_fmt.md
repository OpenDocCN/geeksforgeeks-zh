
# HTML `<script>` 跨原点属性

>&# x539F；&# x 6587；&# xFF1A；[HTML `<script>` 跨原点属性](https://www . geesforgeeks . org/HTML-script-cross origin-attribute/)

The **HTML `<script>` cross origin Attribute** is used to load external scripts from third-party servers or other domains into their own domain under the support of HTTP CORS requests. This attribute is used to protect sensitive information from being affected by third parties when retrieving results.

跨来源资源共享(CORS) is a tool that allows web pages to request resources from another domain outside their own domain. It is also used to manage cross-origin requests, i.e., requests for resources from external domains.

## 句法

```html
&lt；脚本 cross origin=&quot；匿名|使用凭证&quot；&gt；
```

## 属性值

- **匿名**: It has a default value. It defines sending CORS requests without passing credentials information.
- **use-credentials**: Cross-origin requests will be sent with credentials, cookies, and certificates.

## 注意

This attribute is only effective when we try to retrieve resources from third-party domains.

## 示例

下面的代码说明了跨原点属性与 `<script>` 元素的使用。

```html
<!DOCTYPE html>
<html>
<head>
<title>HTML 脚本跨原点属性</title>
</head>
<body>
<h1>geeksforgeeks</h1>
<h2>HTML 脚本跨原点属性</h2>
<br/>
<button>提交</button>
<script type="text/JavaScript" src="my_script.js" cross origin="匿名"></script>
</body>
</html>
```

