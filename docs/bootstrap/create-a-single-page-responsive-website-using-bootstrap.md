# 使用引导程序创建单页响应网站

> 原文:[https://www . geesforgeks . org/create-单页响应网站-使用-bootstrap/](https://www.geeksforgeeks.org/create-a-single-page-responsive-website-using-bootstrap/)

每个人都想创建一个兼容所有设备的网站，如电脑、笔记本电脑、平板电脑和手机。所以要让一个网站具有响应性，最好的方法是使用 [Bootstrap](https://www.geeksforgeeks.org/bootstrap-tutorials/) 创建一个网站。

因为它是一个单页网站，当你点击网站上的任何菜单时，它会到达你的特定部分。

**代码实现:**

[**HTML**](https://www.geeksforgeeks.org/html-tutorials/) **代码:**

在 HTML 代码中，您必须从引导数据库中复制起始模板，并将其粘贴到您的 HTML 文件中。之后创建一个 [**导航条**](https://www.geeksforgeeks.org/bootstrap-navigation-bar/) 。

然后你只需要使用 bootstrap 的网格系统，你就能创建一个像这样简单且响应迅速的网站。

## index.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8" />
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1" />

    <!-- Bootstrap CSS -->
    <link
      href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta2/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity=
"sha384-BmbxuPwQa2lc/FVzBcNJ7UAyJxM6wuqIj61tLrc4wSX0szH/Ev+nYRRuWlolflfl"
      crossorigin="anonymous"
    />
    <link rel="stylesheet"
          href="style.css" />
    <link rel="preconnect" 
          href="https://fonts.gstatic.com" />
    <link
      href=
"https://fonts.googleapis.com/css2?family=Roboto+Condensed&display=swap"
      rel="stylesheet"
    />
    <title>GFG</title>
  </head>
  <body>
    <section id="navbar">
      <nav class="navbar navbar-expand-lg navbar-light">
        <div class="container-fluid">
          <a class="navbar-brand" href="#">
              Geeks for Geeks
            </a>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarSupportedContent"
            aria-controls="navbarSupportedContent"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" 
               id="navbarSupportedContent">
            <ul class="navbar-nav m-auto">
              <li class="nav-item">
                <a class="nav-link active" 
                   aria-current="page" 
                   href="#">Home</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" 
                   href="#service">Services</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" 
                   href="#about">About Us</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" 
                   href="#product">Products</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" 
                   href="#social">Contact Us</a>
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </section>

    <!-- banner -->
    <section id="banner">
      <div class="container-fluid" id="banner-container">
        <div class="row" id="banner-row">
          <div class="col-md-6" id="banner-col">
            <h3>
              BEST PROFESSIONAL WEBSITE DESIGN 
              SOFTWARE DEVELOPMENT COMPANY
            </h3>

<p>
              The fastest way to grow your business with the leader in
              Technology
            </p>

            <div class="d-grid gap-2 d-md-flex justify-content-center">
              <a class="btn btn-primary" 
                 href="#" 
                 role="button">Contact Us</a>
            </div>
          </div>
          <div class="col-md-6" id="banner-col2">
            <img
              class="img-responsive rounded mx-auto d-block"
              src="images/gfg.png"
              alt=""
            />
          </div>
        </div>
      </div>
    </section>

    <!-- services -->
    <section id="service">
      <h1 class="text-center">SERVICES</h1>
      <div class="container-fluid" id="service-container">
        <div class="row" id="banner-row">
          <div class="col-md-4" id="service-col1">
            <img
              src="images/gfg.png"
              class="img-fluid rounded mx-auto d-block"
              alt="..."
            />
            <h3>Website Design</h3>

<p>
              User Experience Design. 
              Website Content Strategy. 
              Cross Browser
              and Platform Testing.
            </p>

          </div>
          <div class="col-md-4" id="service-col2">
            <img
              src="images/gfg.png"
              class="img-fluid rounded mx-auto d-block"
              alt="..."
            />
            <h3>Bulk SMS</h3>

<p>
              1.Toll Free Number 
              2\. IVR 
              3\. Virtual Number 
              4\. Political or any
              Voice Broadcasting
            </p>

          </div>
          <div class="col-md-4" id="service-col3">
            <img
              src="images/gfg.png"
              class="img-fluid rounded mx-auto d-block"
              alt="..."
            />
            <h3>Payment Gateways</h3>

<p>
              PayU India is the flagship company of
               Naspers group which is a $25
              Billion internet and media conglomerate
               listed on London and
              Johannesburg stock exchanges respectively.
            </p>

          </div>
        </div>
      </div>
    </section>
    <hr />

    <!-- about Us -->
    <section id="about">
      <h1 class="text-center">About Us</h1>
      <div class="container-fluid" id="about-container">
        <div class="row" id="banner-row">
          <div class="col-md-6" id="about-col">
            <h3>Why Us</h3>
            <ul>
              <li>
                Probuz is all about Delivering High 
                Quality web design and development 
                services, Cost effective and 
                reliable solutions.
              </li>
              <li>SCHOOL/COLLEGE MANAGEMENT SOFTWARE
                   (CAMPUS PRO)</li>
              <li>
                Let us take care of your Business needs.
                 Customer Productivity is our Priority.
              </li>
              <li>Our expertise in Business includes</li>
            </ul>
          </div>
          <div class="col-md-6" id="banner-col2">
            <img
              class="img-responsive rounded mx-auto d-block"
              src="images/gfg.png"
              alt=""
            />
          </div>
        </div>
      </div>
    </section>
    <hr />
    <!-- product -->

    <section id="product">
      <h1 class="text-center">Our Products</h1>
      <div class="container-fluid" id="product-container">
        <div class="row" id="banner-row">
          <div class="col-md-6" id="about-col">
            <img
              class="img-responsive rounded mx-auto d-block"
              src="images/gfg.png"
              alt=""
            />
          </div>
          <div class="col-md-6" id="product-col2">
            <h3>Product List</h3>

            <ul>
              <li>CLINIC MANAGMENT SYSTEM</li>
              <li>SCHOOL/COLLEGE MANAGEMENT 
                  SOFTWARE (CAMPUS PRO)</li>
              <li>SERVICE MANAGEMENT SOFTWARE</li>
              <li>E-COMMERCE WEBSITE</li>
            </ul>
          </div>
        </div>
      </div>
    </section>
    <hr />
    <!-- social -->
    <section id="social">
      <h1 class="text-center">Get In Touch</h1>
      <div class="d-grid gap-2 d-md-flex justify-content-center">
        <div class="row align-items-center" id="social-row">
          <div class="col-md-4 social-col">
            <a href=""
              ><img
                class="img-responsive rounded mx-auto d-block"
                src="images/gfg.png"
                alt=""
            /></a>
          </div>
          <div class="col-md-4 social-col">
            <a href=""
              ><img
                class="img-responsive rounded mx-auto d-block"
                src="images/icons8-instagram-64.png"
                alt=""
            /></a>
          </div>
          <div class="col-md-4 social-col">
            <a href=""
              ><img
                class="img-responsive rounded mx-auto d-block"
                src="images/icons8-twitter-64.png"
                alt=""
            /></a>
          </div>
        </div>
      </div>
    </section>

    <!-- footer -->
    <section id="footer">
      <section id="banner">
        <div class="container-fluid" id="banner-container">
          <div class="row" id="banner-row">
            <div class="col-md-4" id="footer-col1">
              <h3>My Website</h3>

<p>
                At XYZ we believe that customers should 
                always get easy-to-use, best in the kind
                 and fast services.xyz has achieved 
                 standards which helps customer to 
                 achieve satisfaction and realize
                  value for their hard earned money.
              </p>

            </div>
            <div class="col-md-4" id="footer-col2">
              <h3>Contact Us</h3>

<p>Call Us- 1800-121-6532</p>

<p>Email Us- support@xyz.com</p>

            </div>

            <div class="col-md-4" id="footer-col2">
              <h3>Subscribe To Newsletter</h3>
              <form>
                <div class="mb-3">
                  <input
                    type="email"
                    placeholder="Enter Your Email"
                    class="form-control"
                    id="exampleInputEmail1"
                    aria-describedby="emailHelp"
                  />
                  <div id="emailHelp" 
                       class="form-text">
                    We'll never share your email with anyone else.
                  </div>
                </div>
                <button type="submit" 
                        class="btn btn-primary">
                        Submit
                </button>
              </form>
            </div>
          </div>
        </div>
      </section>
    </section>

    <!-- Optional JavaScript; choose one of the two! -->

    <!-- Option 1: Bootstrap Bundle with Popper -->
    <script
      src=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta2/dist/js/bootstrap.bundle.min.js"
      integrity=
"sha384-b5kHyXgcpbZJO/tY9Ul7kGkf1S0CWuKcCD38l8YkeH8z8QjE0GmW1gYU5S9FOnJ0"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```

**CSS 代码:**

所以，大家都知道 bootstrap 不足以让网站具有交互性，所以在这里添加了一些 CSS。

您可以根据自己的要求更改 navbar 背景颜色。

## style.css

```html
*{
    margin: 0;
    padding: 0;
    font-family: 'Roboto Condensed', sans-serif;
}

/* navbar */

.navbar-nav{
    margin-right: 0 !important;
    padding-right: 100px;
}

.navbar{
    background-color: #0a193d;
    color: white !important;
}

.nav-item a{
    color: white !important;
}

.nav-item{
    padding-left: 2px;
}

.navbar-brand{
    color: white !important;
    padding-left: 100px;
}

#navbar button{
    color: white !important;
}

/* banner */

#banner-container{
    background-color: #0a193d;
    color: white !important;
    padding-top: 80px;
    padding-bottom: 80px;

}

#banner-row img{
    max-width: 70%;
    height: auto;
    display: block;
    padding-left: 30px;
}

#banner-row h3, p{
    padding-left: 20px;
    padding-top: 20px;
    text-align: center;
}

#banner-row a{
    background-color: white !important;
    color: black !important;
    border: none;
    margin-left: 20px;
    margin-top: 20px;

}
#banner-col{
    padding-left: 20px;
}
/* service */
#service{
    padding-top: 80px;
    padding-bottom: 80px;
}

#service h1{
    padding-bottom: 70px;
}

/* about */

#about{
    padding-top: 80px;
    padding-bottom: 80px;
}

#about h1{
    padding-bottom: 70px;
}

#about-col ul{
    padding-top: 50px;
    padding-left: 50px;
}

#about-col ul li{
    padding-top: 15px;

}

/* product */

#product{
    padding-top: 80px;
    padding-bottom: 80px;
}

#product h1{
    padding-bottom: 70px;
}

#product-col2 ul{
    padding-top: 90px;
}

#product-col2 ul li{
    padding-top: 15px;
}

/* social */

#social{
    padding-top: 80px;
    padding-bottom: 80px;
}

#social h1{
    padding-bottom: 70px;
}

.social-col a:hover img{
   transform: translateY(-10px);
}

#social-row{
    flex-direction: row;
}

/* footer */

.mb-3{
  padding-top: 10px;
}

/* media */
@media only screen and (max-width: 987px){
    .navbar-brand{
        padding-left: 0px;
    }
}

@media only screen and (max-width: 768px){
    #banner-row img{
        padding-top: 20px;
    }

   .social-col{
       width: 33%;
   }

}
```

**输出:**

![](img/74a9f6180c12830a0d4d0b2c132b8862.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软边缘
*   火狐浏览器
*   歌剧
*   狩猎

您可以在给定的链接–[https://saurabhsonewane.github.io/gfg1.github.io/](https://saurabhsonewane.github.io/gfg1.github.io/)查看该项目