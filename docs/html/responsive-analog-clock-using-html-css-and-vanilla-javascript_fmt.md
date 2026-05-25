
# 使用 HTML、CSS 和香草 JavaScript 的响应模拟时钟

> 原文: [https://www.geeksforgeeks.org/responsive-analog-clock-using-html-CSS-and-vanilla-JavaScript/](https://www.geeksforgeeks.org/responsive-analog-clock-using-html-css-and-vanilla-javascript/)

在本文中，我们将创建一个**模拟时钟**。这主要是基于 HTML，CSS &香草 JavaScript。

## 进场:

1.  创建一个 HTML 文件，我们将在其中添加主 div，接下来我们将添加 4 个 div 标签，分别用于小时、分钟、秒针和 pin。
2.  创建一个 CSS 文件来设计我们的网页，并为不同的手指定不同的长度。
3.  创建一个 JavaScript 文件，为不同时钟指针的旋转创建一个简短的逻辑。

## 时钟指针旋转逻辑:

### 1. 时针

```html
For Achieving 12hrs,
hour hand moves 360deg.

i.e.  12hrs   ⇢   360degs

so,    1hr    ⇢   30degs

and, 60mins   ⇢   30degs

so,    1min   ⇢   0.5degs

Total Rotation of hour hand:
    (30deg * hrs) + (0.5deg * mins)
```

### 2. 分针

```html
For Achieving 60mins,
hour hand moves 360deg.

i.e.  60mins   ⇢   360degs

so,    1min    ⇢   6degs

Total Rotation of minute hand:
        6deg * mins
```

### 3. 秒针

```html
For Achieving 60secs,
hour hand moves 360deg.

i.e.  60secs   ⇢   360degs

so,    1sec    ⇢   6degs

Total Rotation of second hand:
        6deg * secs
```

## HTML 代码:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Analog Clock</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="clock">
        <div class="hr"></div>
        <div class="min"></div>
        <div class="sec"></div>
        <div class="pin"></div>
    </div>
<script src="index.js"></script>
</body>
</html>
```

## CSS 代码:

```html
/* Restoring browser effects */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* All of the same styling to the body */
body {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #000;
    background-image: linear-gradient(
            70deg, black, white);
}

/* Sizing, positioning of main dial of the clock */
.clock {
    width: 40vw;
    height: 40vw;
    background-image: linear-gradient(
                70deg, black, white);
    background-size: cover;
    box-shadow: 0 3em 5.8em;
    border-radius: 50%;
    position: relative;
}

.hr,
.min,
.sec {
    width: 1%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -100%);
    transform-origin: bottom;
    z-index: 2;
    border-radius: 2em;
}

.pin {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    width: 1em;
    height: 1em;
    background: rgb(38, 0, 255);
    border: 2px solid #ffffff;
    border-radius: 10em;
    margin: auto;
    z-index: 10;
}

/* Different length of different hands of clock */
.hr {
    height: 25%;
    background-color: #ff0000;
}

.min {
    height: 30%;
    background-color: #ff9900;
}

.sec {
    height: 40%;
    background-color: #99ff00;
    transform-origin: 50% 85%;
}
```

## JS 代码:

```html
// Selecting all of the css classes on which
// we want to apply functionalities
const hr = document.querySelector('.hr')
const min = document.querySelector('.min')
const sec = document.querySelector('.sec')

// Setting up the period of working
setInterval(() => {

// Extracting the current time 
    // from DATE() function
    let day = new Date()
    let hour = day.getHours()
    let minutes = day.getMinutes()
    let seconds = day.getSeconds()

// Formula that is explained above for 
    // the rotation of different hands
    let hrrotation = (30 * hour) + (0.5 * minutes);
    let minrotation = 6 * minutes;
    let secrotation = 6 * seconds;

hr.style.transform =
        `translate(-50%,-100%) rotate(${hrrotation}deg)`
    min.style.transform =
        `translate(-50%,-100%) rotate(${minrotation}deg)`
    sec.style.transform =
        `translate(-50%,-85%) rotate(${secrotation}deg)`
});
```

## 完整代码:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <style>
/* Restoring browser effects */        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

/* All of the same styling to the body */        
        body {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #000;
            background-image: linear-gradient(
                70deg, black, white);
        }

/* Sizing, positioning of main dial of the clock */        
        .clock {
            width: 40vw;
            height: 40vw;
            background-image: linear-gradient(
                70deg, black, white);
            background-size: cover;
            box-shadow: 0 3em 5.8em;
            border-radius: 50%;
            position: relative;
        }

.hr,
        .min,
        .sec {
            width: 1%;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -100%);
            transform-origin: bottom;
            z-index: 2;
            border-radius: 2em;
        }

.pin {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            width: 1em;
            height: 1em;
            background: rgb(38, 0, 255);
            border: 2px solid #ffffff;
            border-radius: 10em;
            margin: auto;
            z-index: 10;
        }

/* Different length of different hands of clock */        
        .hr {
            height: 25%;
            background-color: #ff0000;
        }

.min {
            height: 30%;
            background-color: #ff9900;
        }

.sec {
            height: 40%;
            background-color: #99ff00;
            transform-origin: 50% 85%;
        }
    </style>
</head>
<body>
    <div class="clock">
        <div class="hr"></div>
        <div class="min"></div>
        <div class="sec"></div>
        <div class="pin"></div>
    </div>
<script>
// Selecting all of the css classes 
        // on which we want to apply functionalities
        const hr = document.querySelector('.hr')
        const min = document.querySelector('.min')
        const sec = document.querySelector('.sec')

// Setting up the period of working
        setInterval(() => {

// Extracting the current time 
            // from DATE() function
            let day = new Date()
            let hour = day.getHours()
            let minutes = day.getMinutes()
            let seconds = day.getSeconds()

// Formula that is explained above for 
            // the rotation of different hands
            let hrrotation = (30 * hour) + (0.5 * minutes);
            let minrotation = 6 * minutes;
            let secrotation = 6 * seconds;

hr.style.transform =
                `translate(-50%,-100%) rotate(${hrrotation}deg)`
            min.style.transform =
                `translate(-50%,-100%) rotate(${minrotation}deg)`
            sec.style.transform =
                `translate(-50%,-85%) rotate(${secrotation}deg)`
        });
    </script>
</body>
</html>
```

## 输出:

![模拟时钟输出](img/40b591158a0e65f1eb932a415cf877b2.png)
