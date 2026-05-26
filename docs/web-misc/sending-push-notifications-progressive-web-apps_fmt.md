# 发送推送通知：渐进式网络应用

> 原文：[https://www.geeksforgeeks.org/sending-push-notifications-progressive-web-apps/](https://www.geeksforgeeks.org/sending-push-notifications-progressive-web-apps/)

**我们需要权限才能发送推送通知。**

**要点：**

*   通知必须及时。
*   应该是精确的（包含用户需要的所有信息）。
*   应该与用户相关。

**基本示例：** 航空公司应用程序必须发送推送通知，如“您的航班将从……开始登机。”

## 支持推送通知的浏览器

*   Chrome 44
*   Firefox 44
*   Opera 42

## 通知类型

### 持久通知

它与 Service Worker 相关联。

```html
self.registration.showNotification('Title', { 
    actions : [ {               
        action : 'View',
        title : 'Action title',
        icon : 'Path' }],
    // other options
});
```

要和它们互动，有不同的 API：

```html
self.addEventListener('notificationclick', evt=>{ 
    if(!evt.action) {
        console.log('Notification Clicked');
        return ;
    }
    // Handles action clicks
});
```

**视图：**

```html
self.addEventListener('notificationclick', evt=>{ 
    switch(evt.action) {
        case 'view' : console.log('View action clicked');
        break;
        default : console.warn(`${evt.action} action clicked`);
        break;
    }
});
```

### 非持久通知

它不与 Service Worker 相关联。作为开发者，我们通过 Notification API 与之交互。

**通知静态成员：**

```html
if(Notification.permission === 'granted') {
    showNotification();
    return;
}
if(Notification.permission !== 'denied') {
    Notification.requestPermission().then (p=> {
        if(p === 'granted')
            showNotification();
    });
}
```

**如何显示通知：**

```html
var n = new Notification('Title', // object
{
    body : 'body text',
    // Little tiny badge at top left corner of screen
    badge :'path',
    // Setting picture related to the notification
    icon : 'path',
    // Combining different Notifications by providing them with the same tag name
    tag : 'tag name',
    // To notify buzz, set it true 
    renotify : false,    
    data : { /* object */ } 
);
```

**不同的其他属性也可以用以下格式编写：**

*   **动作相关属性 –**

```html
var n = new Notification('Title', // body, images, tag, etc.
{
    // True, when notifications remain open until the user explicitly clicks on it to close
    requiredInteraction : false,
    actions : [ {               
        // Takes objects which has three properties
        action : 'Id',
        title : 'Action title',
        icon : 'Path' 
    }],
});
```

*   **声音属性 –**

```html
// body, images, tag, data, action
// True, vibrate or make sound
silent : false,
// path to sound (Till date no browser supports this)
sound : 'path',
// This indicates to vibrate for 200ms then 100ms then 200ms, so on       
vibrate : [200, 100, 200], 
```

*   **杂项属性 –**

```html
// Direction (left to right or right to left(rtl))
dir : 'ltr',
// Language
lang :'en-US',   
timestamp : Date.now()   // Time
```

## 通知实例成员

```javascript
var n = new Notification('Title', {/* options */});
n.addEventListener('error', evt=>{ console.error('出现问题', evt); });
n.addEventListener('click', evt=>{ console.log('Notification clicked'); });
n.close();
```