# 如何将Express错误信息传递给Angular视图？

> 原文: [https://www.geeksforgeeks.org/how-to-pass-express-errors-message-to-angular-view/](https://www.geeksforgeeks.org/how-to-pass-express-errors-message-to-angular-view/)

Web应用程序主要有两个部分，一个是前端，另一个是后端。我们将首先从后端开始。Express捕获运行路由处理程序和中间件时出现的所有错误。我们只需将它们正确地发送到前端以获取用户知识。

Express捕获并处理同步和异步发生的错误。Express附带了一个默认的错误处理程序，因此您不需要编写自己的错误处理程序就可以开始了。

## 方法:

*   创建要使用的Angular应用。
*   创建相同的后端路由。
*   当用户注册失败时，我们发送一个错误。因此，我们在Express应用程序中创建了一个`/registration`路由。当注册失败时，使用`res.status`发送错误（401）。`json()`方法。
*   现在在前端，`auth.service.ts`正在向后端发送注册请求。这将返回一个可观察的响应。因此，我们可以订阅这个请求，以处理来自后端的响应。
*   因此，在返回的可观察对象内部处理错误情况或成功情况。

## 示例:

用一个非常简单的示例来解释它。假设我们正在尝试在数据库中创建一个新用户，并从注册页面为此发送一个POST请求。

```ts
router.post('/signup', UserController.(req,res)=>{
    bcrypt.hash(req.body.password,10)
    .then((hash)=>{
        var user = new User({
            email: req.body.email,
            password: hash
        })
        User.save((err,d)=>{
            if(err){
                res.status(401).json({
                    message: 'Failed to create new user'
                })
            } else{
                res.status(200).json({
                    message: 'User created'
                })
            }
        })
    })
})
```