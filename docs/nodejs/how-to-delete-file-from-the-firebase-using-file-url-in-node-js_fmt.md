# 如何使用 Node.js 中的文件 URL 从 Firebase 中删除文件？

> 原文：[https://www.geeksforgeeks.org/how-to-delete-file-from-the-firebase-using-file-url-in-node-js/](https://www.geeksforgeeks.org/how-to-delete-file-from-the-firebase-using-file-url-in-node-js/)

要从 Firebase 存储中删除一个文件，我们需要一个引用来将该文件存储在存储中。由于我们只有文件 URL，我们需要在 Firebase 存储中创建文件的引用对象，然后删除该文件。

使用文件 URL 删除文件可以分两步完成：

1.  从 `firebase.storage` 获取文件的引用。
2.  使用 [`refFromUrl`](https://firebase.google.com/docs/reference/js/firebase.storage.Storage#reffromurl) 方法来获取对存储的引用。然后使用从第一步获得的存储中文件的引用来删除该文件。

方法 `refFromUrl` 返回对该文件的引用，可以将两种类型的文件 URL 作为输入：

1.  一个指向文件的下载 URL。
2.  从对象元数据下载的 URL。

## 示例 1：使用 `refFromURL` 方法从给定的文件 URL 中删除文件。

### JavaScript

```js
var fileUrl = 
'https://firebasestorage.googleapis.com/b/bucket/o/images%20geeksforgeeks.jpg';

// Create a reference to the file to delete
var fileRef = storage.refFromURL(fileUrl);

console.log("File in database before delete exists : " 
        + fileRef.exists())

// Delete the file using the delete() method 
fileRef.delete().then(function () {

// File deleted successfully
    console.log("File Deleted")
}).catch(function (error) {
    // Some Error occurred
});

console.log("File in database after delete exists : "
        + fileRef.exists())
```