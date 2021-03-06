# HTML5新标签完成静态博客的构建

### 项目地址

demo: [http://demo.wingsico.org/html5/tags/](http://demo.wingsico.org/html5/tags/)

### 项目目录

```bash
.
|____index.html
|____.DS_Store
|____css
| |____index.css
|____images
| |____.DS_Store
| |____index.png
| |____figure.jpg
```

### 代码

> HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <link rel="stylesheet" href="./css/index.css">
  <title>HTML5静态博客</title>
</head>
<body>
  <header>
    <h1 class="index-image">wingsico</h1>
    <nav class="navigator">
      <ul>
        <li><a href="#Home" id="Home">Home</a></li>
        <li><a href="#AboutMe" id="AboutMe">AboutMe</a></li>
        <li><a href="#Contact" id="Contact">Contact</a></li>
        <li><a href="#Links" id="Links">Links</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <figure>
      <section>
        <figcaption>Wingsico.Think</figcaption>
        <p class="small-title">—— Better late than never.</p>
      </section>
      <section>
        <img src="./images/figure.jpg" alt="figure" class="figure-image" />        
      </section>
    </figure>
    <hr />
    <article class="content">
      <section>
        <h2>Skills</h2>
        <section class="skills">
          <mark>html</mark><meter value="75" low="50" high="70" min="0" max="100" optimum="90"></meter><br>
          <mark>css</mark><meter value="60" low="50" high="70" min="0" max="100" optimum="90"></meter><br>
          <mark>js</mark><meter value="50" low="50" high="70" min="0" max="100" optimum="90"></meter><br>
          <mark>vueJs</mark><meter value="50" low="50" high="70" min="0" max="100" optimum="90"></meter><br>
          <mark>reactJs</mark><meter value="30" low="50" high="70" min="0" max="100" optimum="90"></meter><br>
        </section>
        <p></p>
      </section>
      <section>
        <h2>Contact</h2>
        <ul class="contacts">
          <li>
            <mark>Blog</mark><a href="http://wingsico.org">http://wingsico.org</a>
          </li>
          <li>
            <mark>Github</mark><a href="https://github.com/wingsico">https://github.com/wingsico</a>
          </li>
          <li>
            <mark>Gitbook</mark><a href="http://gitbook.wingsico.org">http://gitbook.wingsico.org</a>
          </li>
        </ul>
      </section>
      <section class="about-me">
        <h2>AboutMe</h2>
        <p>The first known study of the sublime is ascribed to Longinus: Peri Hupsous/Hy<wbr>psous or On the Sublime. This is thought to
        have been written in the 1st century AD though its origin and authorship are uncertain. </p>
      </section>
    </article>
  </main>

  <footer>
     <p>©2018 Powered by wingsico</p>
  </footer>

  <script>
    (function () {
      var url = window.location.href;
      if (url.indexOf('#') < 0) {
        window.location.hash = 'Home'
      }
    })()
  </script>
</body>
</html>
```

> css

```css

@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: translateY(30px)
  }
  100% {
    opacity: 1;
    transform: translateY(0px);
  }
}

@keyframes fadeInRight {
  0% {
    opacity: 0;
    transform: translateX(-100px);
  }
  100% {
    opacity: 1;
    transform: translateX(0px);
  }
}

@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(100px);
  }
  100% {
    opacity: 1;
    transform: translateX(0px);
  }
}




body {
  max-width: 960px;
  margin: 100px auto;
  background-color: aliceblue;
}

a {
  text-decoration: none;
  color: rgb(7, 7, 7);
  outline: none;
}

header h1.index-image {
  display: inline-block;
  margin: 0;
  height: 80px;
  content: url('../images/index.png');
  animation: fadeIn 1s;
}

ul {
  padding: 0;
  margin: 0;
  list-style: none;
}

header nav.navigator {
  float: right;
  height: 80px;
  display: flex;
  align-items: center;
}

header nav.navigator ul li {
  display: inline-block;
  text-align: center;
  font-size: 20px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

header nav.navigator ul li + li {
  margin-left: 40px;
}

header nav.navigator ul li a {
  display: inline;
  padding: 14px 14px;
  border-radius: 5px;
  transition: background 0.5s, color 0.1s;
}

header nav.navigator ul li a:hover {
  background-color: #44CEFF;
  color: #fff;
}


header nav.navigator ul li > a:target {
  background-color: #44CEFF;
  color: #fff;
}

main {
  margin-top: 70px;
}

main figure {
  margin: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

main figure section {
  display: inline-block;
  vertical-align: top;
  text-align: center;
  width: 49%;
}

main figure section:nth-child(1) {
  animation: fadeInRight 1s;
}

main figure section:nth-child(2) {
  animation: fadeInLeft 1s;  
}

main figure section figcaption {
  display: inline-block;
  font-size: 60px;
  font-weight: bold;
  color: slateblue;
  width: 420px;
  text-align: center;
}

main figure section .small-title {
  display: inline-block;
  text-align: right;
  width: 420px;
}

main figure section .figure-image {
  width: 420px;
}

hr {
  height: 2px;
  background-image: linear-gradient(to right, aliceblue, #ccc, aliceblue);
  margin-top: 50px;
  border: none;
}

main article.content {
  display: flex;
  justify-content: space-around;
}

main article section {
  width: 100%;
  box-sizing: border-box;
  padding: 0 0.5em;
}


main article section h2 {
  font-size: 24px;
  font-weight: bold;
  color: #44ceff;
  text-align: center;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

main article section .skills {
  text-align: justify;
  line-height: 2em;
  display: inline-block;
}

main article section .skills mark {
  display: inline-block;
  font-family: cursive;
  color: #fff;
  font-size: 20px;
  text-align: center;
  background-color: deepskyblue;
  border-radius: 5px;
  box-sizing: border-box;
  width: 80px;
  vertical-align: top;
  margin-left: 20px;
}

main article section .skills mark::after {
  content: ':';
  display: inline-block;
  margin-left: 5px;
  vertical-align: top;
}


main article section .skills meter {
  width: 60%;
  line-height: 1;
  margin-left: 15px;
  height: 1.75em;
}

main article section ul.contacts li{
  text-align: left;
  font-size: 18px;
  margin-bottom: 30px;
}

main article section ul.contacts li mark{
  display: inline-block;
  padding: 0 0.1em;
  color: #000;
  font-weight: bold;
  border-radius: 6px;
  background-color: #eee;
  border: 1px solid #ddd;
  box-shadow: 1px 2px 4px 0px #000;
  margin-right: 5px;
  vertical-align: top;
}

main article section ul.contacts li a {
  display: inline-block;
  text-overflow: ellipsis;
  max-width: 70%;
  overflow: hidden;  
}

main article section ul.contacts li a:hover {
  color: #44ceff;
}

main article section.about-me p {
  text-align: justify;
  text-indent: 2em;
  line-height: 1.5em;
}

footer {
  height: 100px;
  background-color: #fff;
  border-top: 1px solid #ccc;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

footer p {
  text-align: center;
}
```



