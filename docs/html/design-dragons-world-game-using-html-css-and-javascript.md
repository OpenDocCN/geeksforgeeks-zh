# 使用 HTML CSS 和 JavaScript 设计龙的世界游戏

> 原文:[https://www . geesforgeks . org/design-dragons-world-game-use-html-CSS-and-JavaScript/](https://www.geeksforgeeks.org/design-dragons-world-game-using-html-css-and-javascript/)

**项目介绍:**《龙的世界》是一个游戏，一条龙试图通过跳过挡路的龙来从另一条龙手中拯救自己。当一条龙从另一条龙手中救下自己时，分数会更新。

该项目将包含 HTML，CSS 和 JavaScript 文件。该 HTML 文件增加了游戏的结构，然后使用 CSS 进行造型。JavaScript 为游戏增加了功能。

**文件结构:**

*   index.html
*   style.css
*   script.js

**HTML 代码:**

*   **标题部分:**会显示游戏名称。
*   **游戏结束部分:**输了游戏会显示。
*   **障碍部分:**将包含龙必须自救的障碍。
*   **龙的部分:**它将包含必须从障碍中拯救的龙，即另一条龙。
*   **分数部分:**会显示游戏当前的分数。

**index.html**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <link rel="stylesheet" href=
        "style.css?_cacheOverride=1606401798626">

    <link href=
"https://fonts.googleapis.com/css2?family=Ubuntu:ital, 
        wght@0, 300;1, 700&display=swap"
        rel="stylesheet">
</head>

<body>
    <h1 id="gameName">Welcome to Dragon's world</h1>
    <div class="container">
        <div class="gameover">Game Over</div>
        <div id="scorecount">Your score : 0</div>
        <div class="obstacle animateobstacle"></div>
        <div class="dragon" style="left: 426px;"></div>
    </div>
</body>

</html>
```

**CSS 代码:**

*   **定位游戏名称:**游戏名称由 CSS 的*绝对*属性定位。
*   **背景图样式:**在*容器*类中，我们已经将游戏的背景图与*背景尺寸*设置为*覆盖*。
*   **记分卡样式:**我们已经将记分卡放置在页面的右上角，并为其提供了合适的背景颜色，以使其具有吸引力。其中的文本将显示在*白色*中。
*   **障碍物图像样式:**我们已经将障碍物定位到页面的左下角，并为其提供动画，以便其可以向左移动。
*   **龙的造型:**我们已经将龙定位在页面的左下角，并为它提供动画，这样它就可以跳起来自救了。
*   **游戏结束样式:**我们已经将游戏结束部分定位到页面中心，当龙被障碍物击中时，它就会出现。

**style.css**

```html
/* CSS Reset */
*{
    margin:0px;
    padding:0px;
}
body {
    /* Hides the  bottom scrollbar */
    overflow: hidden;
}
/* Styling of the Game's Name */
#gameName {
    position: absolute;
    top:30vh;
    left:38vw;
}
/* Background image styling */
.container {
    background-image: url(cover.png);
    background-size: cover;
    width:100vw;
    height:100vh;
}
/* ScoreCard Styling */
#scorecount {
    position: absolute;
    top:20px;
    right:20px;
    background-color: black;
    padding: 28px;
    border-radius: 20px;
    color: white;
}
/* Obstacle image styling and positioning */
.obstacle {
    background-image: url(obstacle.png);
    background-size: cover;
    width:154px;
    height: 126px;
    position: absolute;
    bottom:0px;
    right:120px;
}
/* Applying animation to the obstacle
 so that it can move towards left */
.animateobstacle {
    animation: aniob 5s linear infinite;
}
@keyframes aniob {
    0% {
        left:100vw;
    }
    100% {
        left:-10vw;
    }
}
/* Dragon's styling */
.dragon {
    background-image: url(dragon.png);
    background-size: cover;
    width: 194px;
    height: 126px;
    position: absolute;
    bottom:0px;
    left:90px;
}
/* Applying animation to the dragon so 
that it can save himself by jumping up */
.animatedragon {
    animation: ani 1s linear;
}
@keyframes ani {
    0% {
        bottom:0px;
    }
    25% {
        bottom:150px;
    }
    50% {
        bottom:300px;
    }
    75% {
        bottom:211px;
    }
    100% {
        bottom:0px;
    }
}
/* gameover styling and positioning */
.gameover {
    visibility: hidden;
    font-family: 'Ubuntu', sans-serif;
    position: absolute;
    top: 50vh;
    left: 35vw;
    color: red;
    font-weight: bold;
    font-size: 6rem;
    background-color: firebrick;
    border-radius: 20px;
}

```

**JavaScript 代码:**

**1。龙的运动:**这是由 *onkeydown* 事件提供的。

*   **向上箭头键:**按下时，龙会向上跳(动画由 CSS 提供)。
*   **左箭头键:**按下时，龙会向左移动(动画由 CSS 提供)。
*   **右箭头键:**按下时，龙会向左移动(动画由 CSS 提供)。

```html
document.onkeydown = function(e) {
    console.log(e.keyCode);
    if (e.keyCode == 38) {
        dragon = document.querySelector('.dragon');
        dragon.classList.add('animatedragon');
        setTimeout(() => {
            dragon.classList.remove('animatedragon');
        }, 700);
    }
    if (e.keyCode == 37) {
        dragon = document.querySelector('.dragon');
        dragonx = parseInt(window.getComputedStyle(dragon, null)
            .getPropertyValue('left'));
        dragon.style.left = dragonx - 112 + "px";
    }
    if (e.keyCode == 39) {
        dragon = document.querySelector('.dragon');
        dragonx = parseInt(window.getComputedStyle(
            dragon, null).getPropertyValue('left'));
        dragon.style.left = dragonx + 112 + "px";
    }
}

```

**2。更新分数:**只有满足给定条件时，分数才被满足。我们将计算障碍和龙的左值和底值，然后根据适当的值增加分数，该值表明龙已经从障碍中拯救了自己。为此，我们采用了“交叉”变量，并为其指定了“真”。当龙安全通过障碍物时，我们将该值设置为“假”。大约 1 秒后，我们将 cross 的值更改为“true”。我们还使障碍在每次穿越后跑得更快，从而增加了难度。

```html
setInterval(() => {
    dragon = document.querySelector('.dragon');
    gameover = document.querySelector('.gameover');
    obstacle = document.querySelector('.obstacle');

    dx = parseInt(window.getComputedStyle(
        dragon, null).getPropertyValue('left'));

    dy = parseInt(window.getComputedStyle(
        dragon, null).getPropertyValue('bottom'));

    ox = parseInt(window.getComputedStyle(
        obstacle, null).getPropertyValue('left'));

    oy = parseInt(window.getComputedStyle(
        obstacle, null).getPropertyValue('bottom'));

    offsetx = Math.abs(dx - ox);
    offsety = Math.abs(dy - oy);

    console.log(offsetx, offsety);

    if (offsetx < 120 && offsety <= 125 144) { gameover.style.visibility="visible" ; obstacle.classlist.remove('animateobstacle'); } else if (offsetx < && cross) score +="1;" updatescore(score); cross="false;" settimeout(()> {
            cross = true;
        }, 1000);
        setInterval(() => {
            obsanidur = parseFloat(window
                .getComputedStyle(obstacle, null)
                .getPropertyValue('animation-duration'));

            obstacle.style.animationDuration
                = obsanidur - 0.01 + 's';
        }, 500);
    }
}, 10);

function updateScore(score) {
    scorecount.innerHTML = "Your score : " + score;
}
=>
```

**script.js**

```html
<script>
    cross = true;
    score = 0;
    document.onkeydown = function(e) {
        console.log(e.keyCode);
        if (e.keyCode == 38) {
            dragon = document.querySelector('.dragon');

            dragon.classList.add('animatedragon');

            setTimeout(() => {
                dragon.classList.remove('animatedragon');
            }, 700);
        }
        if (e.keyCode == 37) {
            dragon = document.querySelector('.dragon');

            dragonx = parseInt(window.getComputedStyle(
                dragon, null).getPropertyValue('left'));

            dragon.style.left = dragonx - 112 + "px";
        }
        if (e.keyCode == 39) {
            dragon = document.querySelector('.dragon');

            dragonx = parseInt(window.getComputedStyle(
                dragon, null).getPropertyValue('left'));

            dragon.style.left = dragonx + 112 + "px";
        }
    }
    setInterval(() => {
        dragon = document.querySelector('.dragon');
        gameover = document.querySelector('.gameover');
        obstacle = document.querySelector('.obstacle');

        dx = parseInt(window.getComputedStyle(
            dragon, null).getPropertyValue('left'));

        dy = parseInt(window.getComputedStyle(
            dragon, null).getPropertyValue('bottom'));

        ox = parseInt(window.getComputedStyle(
            obstacle, null).getPropertyValue('left'));

        oy = parseInt(window.getComputedStyle(
            obstacle, null).getPropertyValue('bottom'));

        offsetx = Math.abs(dx - ox);
        offsety = Math.abs(dy - oy);

        console.log(offsetx, offsety);

        if (offsetx < 120 && offsety <= 144) {
            if (score != 0)
                scorecount.innerHTML = "Your score : " + score;
            gameover.style.visibility = 'visible';
            obstacle.classList.remove('animateobstacle');
        } else if (offsetx < 125 && cross) {
            score += 1;
            updateScore(score);
            cross = false;
            setTimeout(() => {
                cross = true;
            }, 1000);
            setInterval(() => {
                obsanidur = parseFloat(window
                .getComputedStyle(obstacle, null)
                .getPropertyValue('animation-duration'));

                obstacle.style.animationDuration
                    = obsanidur - 0.01 + 's';
            }, 500);
        }
    }, 10);

    function updateScore(score) {
        scorecount.innerHTML = "Your score : " + score;
    }
</script>
```

**参考:** [龙游](https://github.com/SAEb-ai/Dragon-s-World-Game)

**输出:**

<video class="wp-video-shortcode" id="video-525311-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201206163914/WhatsApp-Video-2020-12-06-at-4.36.51-PM.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201206163914/WhatsApp-Video-2020-12-06-at-4.36.51-PM.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201206163914/WhatsApp-Video-2020-12-06-at-4.36.51-PM.mp4)</video>