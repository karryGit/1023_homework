# 1023_homework
使用Vue.js编写的界面效果

***

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>homework</title>
    <script src="node_modules/vue/dist/vue.js"></script>
</head>
<body>
<div id="app">
    <link rel="stylesheet" :href="css">
    <!--切换按钮部分-->
    <div class="header">
        <img @click="clicked" :class="color" class="header_one" :src="grade"/>
        <img @click="clicked1" :class="color1" class="header_two" :src="list"/>
    </div>
    <!--下面图片和内容部分-->
    <div id="content" class="clear_float">
        <div id="content_left" v-for="value in array" class="float-left">
            <img  :src="value.image" alt="">
            <div class="hengxian"></div>
            <a class="content_a" :href="value.url">
                <p class="title">{{value.title}}</p>
            </a>
        </div>
    </div>
</div>
<script>
        new Vue({
            el: '#app',
            data: {
                css:'css/homework.css',
                grade:'img/grade.png',
                list:'img/list.png',
                color:'',
                color1:'',
                array: [{
                    "title": "What You Need To Know About CSS Variables",
                    "url": "http://tutorialzine.com/2016/03/what-you-need-to-know-about-css-variables/",
                    "image": 'https://tutorialzine.com/media/2016/03/css-variables.jpg'
                },
                    {
                        "title": "Freebie: 4 Great Looking Pricing Tables",
                        "url": "http://tutorialzine.com/2016/02/freebie-4-great-looking-pricing-tables/",
                        "image": 'https://tutorialzine.com/media/2016/02/great-looking-pricing-tables.jpg'
                    },
                    {
                        "title": "20 Interesting JavaScript and CSS Libraries for February 2016",
                        "url": "http://tutorialzine.com/2016/02/20-interesting-javascript-and-css-libraries-for-february-2016/",
                        "image": 'https://tutorialzine.com/media/2016/02/interesting-resources-february.jpg'
                    },
                    {
                        "title": "Quick Tip: The Easiest Way To Make Responsive Headers",
                        "url": "http://tutorialzine.com/2016/02/quick-tip-easiest-way-to-make-responsive-headers/",
                        "image": 'https://tutorialzine.com/media/2016/02/quick-tip-responsive-headers.png'
                    },
                    {
                        "title": "Learn SQL In 20 Minutes",
                        "url": "http://tutorialzine.com/2016/01/learn-sql-in-20-minutes/",
                        "image": 'https://tutorialzine.com/media/2016/01/learn-sql-20-minutes.png'
                    },
                    {
                        "title": "Creating Your First Desktop App With HTML, JS and Electron",
                        "url": "http://tutorialzine.com/2015/12/creating-your-first-desktop-app-with-html-js-and-electron/",
                        "image": 'https://tutorialzine.com/media/2015/12/creating-your-first-desktop-app-with-electron.png'
                    }]
            },
            methods:{
                clicked:function () {
                    this.color = 'color';
                    this.color1 = '';
                    this.css = 'css/homework.css'
                },
                clicked1:function () {
                    this.color1 = 'color';
                    this.color = '';
                    this.css = 'css/homework1.css'
                }
            }
        })
</script>
</body>
</html>
```

```	
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

img {
    vertical-align: top;
    border: none
}
/*浮动左*/
.float-left {
    float: left;
}

/*浮动右*/
.float-right {
    float: right;
}

/*清除浮动必须加到父级元素上*/
.clear_float::after {
    content: "";
    display: table;
    clear: both;
}

#app {
    width: 100%;
    height: 600px;
}

a {
    text-decoration: none;
}
.header {
    position: relative;
    width: 90%;
    margin: 10px auto;
    height: 30px;
    background-color: rgb(86, 150, 179);
}

.header img {
    width: 22px;
    height: 22px;
}

.header_one {
    padding: 2px;
    background-color: rgb(71, 123, 163);
    position: absolute;
    right: 8%;
    top: 4px;
}

.header_two {
    padding: 2px;
    background-color: rgb(71, 123, 163);
    position: absolute;
    right: 4%;
    top: 4px;
}

#content {
    height: 550px;
    width: 85%;
    margin: 0 auto;
}

#content_left {
    margin-right: 6px;
    position: relative;
    word-wrap: break-word;
    word-break: break-all;
    width: 48%;
}

#content_left img {
    margin: 2px;
    width: 100%;
    height: 180px;
}

.content_a {
    font-size: 10px;
    color: white;
    position: absolute;
    left: 29%;
    top: 70%;
}
.content_a p{
    width: 138px;
    word-wrap: break-word;
    word-break: break-all;
    text-align: center;
}
.color{
    background-color: rgb(188,48,140)
}
```

***

### 通过切换href改变css的class

```
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

img {
    vertical-align: top;
    border: none
}
/*浮动左*/
/*.float-left {*/
    /*float: left;*/
/*}*/

/*浮动右*/
.float-right {
    float: right;
}

/*清除浮动必须加到父级元素上*/
.clear_float::after {
    content: "";
    display: table;
    clear: both;
}

#app {
    width: 100%;
    height: 600px;
}

a {
    text-decoration: none;
}
.header {
    position: relative;
    width: 90%;
    margin: 10px auto;
    height: 30px;
    background-color: rgb(86, 150, 179);
}

.header img {
    width: 22px;
    height: 22px;
}

.header_one {
    padding: 2px;
    background-color: rgb(71, 123, 163);
    position: absolute;
    right: 8%;
    top: 4px;
}

.header_two {
    padding: 2px;
    background-color: rgb(71, 123, 163);
    position: absolute;
    right: 4%;
    top: 4px;
}

#content {
    height: 550px;
    width: 85%;
    margin: 0 auto;
}

#content_left {
    margin-right: 6px;
    position: relative;
    word-wrap: break-word;
    word-break: break-all;
    width: 48%;
}

#content_left img {
    margin: 2px;
    width: 87%;
    height: 200px;
}

.content_a {
    font-size: 10px;
    color: white;
    position: absolute;
    left: 29%;
    top: 70%;
}
.content_a p{
    word-wrap: break-word;
    word-break: break-all;
}
.color{
    background-color: rgb(188,48,140)
}
.title{
    font-size: 20px;
    color: black;
    position: absolute;
    left: 276px;
    top: -119px;
    width: 354px;
}
.hengxian{
    margin: 5px;
    width: 200%;
    height: 1px;
    background-color: rgb(238,238,238);
}
```



