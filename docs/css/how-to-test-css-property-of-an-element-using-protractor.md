# 如何用量角器测试一个元素的 CSS 属性？

> 原文:[https://www . geeksforgeeks . org/如何使用量角器测试元素属性/](https://www.geeksforgeeks.org/how-to-test-css-property-of-an-element-using-protractor/)

**量角器**是为 Angular 和 AngularJS 应用开发的端到端测试框架。它像一个真正的用户一样，在一个真正的浏览器中运行与它交互的应用程序。在本文中，我们将测试元素的 CSS 属性。

**先决条件:** [量角器的安装和设置](https://www.geeksforgeeks.org/angularjs-end-to-end-e2e-testing-protractor-installation-and-setup/)

**方法:**

*   We will create a basic test program in which we will test the CSS properties of an element.
*   All protractor tests will have a file containing the configuration, which will be the initial file to start the test.
*   Let's create this file with the name **conf.js** .

    ## conf . js:

```html
exports.config = {

    // Capabilities to be passed to 
    // the webdriver instance
    capabilities: {
        'browserName': 'chrome'
    },

    // Framework to use Jasmine is 
    // recommended
    framework: 'jasmine',

    // Spec patterns are relative to
    // the current working directory 
    // when protractor is called
    specs: ['test.js'],

    // Options to be passed to Jasmine.
    jasmineNodeOpts: {
        defaultTimeoutInterval: 30000
    },

    // Url for the file
    baseUrl: 'file://' + __dirname + '/',

    onPrepare: function () {
        browser.resetUrl = 'file://';
    }
};
```