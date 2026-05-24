# 在 ngResource 上使用 Restangular 有什么区别？

> 原文:[https://www . geeksforgeeks . org/using-restangular-over-ng resource/](https://www.geeksforgeeks.org/what-is-the-difference-between-of-using-restangular-over-ngresource/)有何区别

Restangular 和 ngResource 之间的主要区别:

*   Restangular 没有像$resource 那样对对象进行“神奇”的填充，而是使用 promises(promise 代表操作的最终结果。您将使用一个承诺来指定当操作成功或失败时尝试什么)。
*   Restangular 没有尾随斜线的问题，附加的:在 URL 中，转义信息，只需要数组来获取列表，等等。
*   Restangular 支持所有 HTTP 方法，而$resource 只支持“GET”、“POST”、“PUT”、“DELETE”。
*   Restangular 支持盒子的 Etag。你不需要做任何事情。ETags 和如果不匹配将用于您的所有请求。
*   在 Restangular 中，如果您从服务器接收到某个具有自身链接的项目，您将使用它来询问服务器，而不是手动编写 URL。
*   每次你想尝试一个邀请，你只需要使用 Restangular 返回的东西就可以了。您不能为此创建替换对象。但是，在使用$resource 时，您必须为每个请求创建一个$resource 对象。
*   使用$resource，您需要写下网址模板。在 Restangular 中，您不需要编写任何 URL。您只需写下您想要获取的资源的名称，就可以了。
*   如果您有嵌套 RESTful 资源，Restangular 可以为您处理它们。您不需要知道网址、路径或任何东西来尝试您想要的所有 HTTP 操作。

## java 描述语言

```ts
// Restangular returns promises
Restangular.all('users').getList() // GET: /users
    .then(function (users) {

        // Returns an inventory of users
        // First Restangular obj in list: { id: 123 }
        $scope.user = users[0]; 
    })
// code

// Restangular objects are self-aware and 
// skills to form their own RESTful requests
// GET: /users/123/cars
$scope.user.getList('cars'); 

// You'll also use your own custom methods
// on Restangular objects
// POST: /users/123/sendMessage
$scope.user.sendMessage(); 

// Chain methods together to simply
// build complex requests
$scope.user.one('messages', 123)
    .one('from', 123).getList('unread');
// GET: /users/123/messages/123/from/123/unread
```

简而言之，我们会说，除了额外的功能和基于承诺的方法之外，Restangular 还可以处理您的所有网址，这样您就不需要了解它们。

## java 描述语言

```ts
Restangular.one("users", 123).get().then(function(user) {
    $scope.user = user;
});

// code

// Automatically does the request to /users/123/cars 
// because it remembers during which object you're asking it.
$scope.user.getList('cars')
```