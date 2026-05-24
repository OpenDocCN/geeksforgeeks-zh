# 如何将快递错误信息传递给 Angular view？

> 原文:[https://www . geesforgeks . org/如何传递-快速-错误-消息到角度-视图/](https://www.geeksforgeeks.org/how-to-pass-express-errors-message-to-angular-view/)

web 应用程序主要有两个部分，一个是前端，另一个是后端。我们将首先从后端开始。express 捕获运行路由处理程序和中间件时出现的所有错误。我们只需将它们正确地发送到前端以获取用户知识。

Express 捕获并处理同步和异步发生的错误。Express 附带了一个默认的错误处理程序，因此您不需要编写自己的错误处理程序就可以开始了。

**方法:**

*   Create Angular app to use.
*   Create the same back-end route.
*   We send an error when the user registration fails. Therefore, we created a "/registration" route in the express application. When registration fails now, use res.status to send an error (401). Json () method.
*   Now on the front end, auth.service.ts is sending a registration request to the back end. This will return an observable response. So we can subscribe to this request, except for the front-end back-end response.
*   Therefore, either the error cases or the success cases are handled in the returned observable interior.

**示例:**用一个非常简单的示例来解释它假设我们正在尝试在数据库中创建一个新用户，并从注册页面为此发送一个帖子请求。

```ts
router.post('/signup',UserController.(req,res)=>{
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