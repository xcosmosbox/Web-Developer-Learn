# Web Developer Learn Notebook For CSS

## CSS

内容：

1. 什么是CSS
2. CSS快速入门
3. CSS选择器（重难点）
4. 美化页面（文字、阴影、超链接、列表、渐变……）
5. 盒子模型
6. 浮动
7. 定位
8. 网页动画（特效效果）



### 什么是CSS

Cascading style sheet 层叠级联样式表

CSS：表现（美化网页，对字体、颜色、边框、高度、宽度）



### 快速入门

html内的代码：

```html
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--规范，<style> 可以编写css的代码，每一个声明使用分号结尾
        语法：
            选择器{
                声明1；
                声明2；
                声明3；
                ……
            }
    -->
    <link rel="stylesheet" href="css/style.css">
    
</head>
<body>

<h1>我是标题</h1>

</body>
```

css内的代码：

```css
h1{
    color: red;
}
```



#### CSS的优势

1. 内容和表现分离
2. 网页结构表现统一，可以实现复用
3. 样式十分的丰富
4. 建议使用独立于html 的css文件
5. 利用SEO，容易被搜索引擎收录



#### CSS的3种导入方式

1. 行内样式
2. 外部样式
3. 内部样式
4. 三者的优先级：取决于语法在结构上距离被渲染的对象的远近，采用就近原则，即使是外部样式，只要离被渲染的对象更将，其优先级也一样会高于内部样式。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--规范，<style> 可以编写css的代码，每一个声明使用分号结尾
        语法：
            选择器{
                声明1；
                声明2；
                声明3；
                ……
            }
    -->

    <!--内部样式-->
    <style>
        h1{
            color: aqua;
        }
    </style>

    <!--外部样式-->
    <link rel="stylesheet" href="css/style.css">

    <!--内部样式-->
    <style>
        h2{
            color:greenyellow;
        }
    </style>

</head>
<body>

<!--行内样式-->
<h1 style="color: beige">我是标题</h1>
<h1>我也是标题</h1>

</body>
</html>
```

拓展：外部样式的两种写法：

1. 链接式（本质是html语法）：

   ```html
   	<!--外部样式-->
       <link rel="stylesheet" href="css/style.css">
   ```

   

2. 导入式（本质是CSS语法）：

   ```html
       <style>
           @import url("css/style.css");
       </style>
   ```

   

### CSS选择器

作用：选择页面上的某一个或某一类元素

#### 基本选择器

1. 标签选择器
2. 类选择器：不同的标签可以有同一个class
3. Id选择器：id选择器和class选择器不同的是，id必须保证全局唯一

> 选择器不遵循就近原则，id选择器>class选择器>标签选择器



标签选择器代码：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        <!--标签选择器，会选择页面上所有所属的这个标签的元素-->
        h1{
            color: #ffd155;
            background: #b3ffb4;
            border-radius: 24px;
        }
        p{
            font-size: 80px;
        }
    </style>


</head>
<body>

<h1>Java</h1>
<h1>coding</h1>
<p>python</p>


</body>
</html>
```



类选择器代码：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        <!--类选择器的格式 .class 的名称{}
            好处：可以多个标签归类，是同一个class，可以复用
        -->
        .r{
            color: #ff79ff;
        }
        .pip{
            color: greenyellow;
        }
        .a{
            color: #f3ff5f;
        }
    </style>

    <link rel="stylesheet" href="css/style.css">
</head>
<body>

<h1 class="a">标题1</h1>
<h1 class="r">标题2</h1>
<h1 class="a">标题3</h1>

<p class="pip">P标签</p>

</body>
</html>
```



id选择器代码：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        <!--id选择器：id选择器和class选择器不同的是，id必须保证全局唯一
            #id名称{}
        -->
        #a {
            color: greenyellow;
        }
    </style>

</head>
<body>


<h1 id="a">标题1</h1>
<h1 id="r">标题2</h1>
<h1>标题3</h1>

<p id="pip">P标签</p>

</body>
</html>
```



#### 层次选择器

1. 后代选择器：在某个元素的后面，其后的所有代都会被选中

   ```html
           <!--后代选择器-->
           ul p{
               background: #b3ffb4;
           }
   ```

   

2. 子选择器：只选择一代，即儿子代

   ```html
           /*子选择器*/
           body>p{
               color: #ff79ff;
               background: greenyellow;
           }
   ```

   

3. 相邻兄弟选择器：只选择同class的目的标签，且只向下相邻，并且最多向下相邻一次（向下相邻一个兄弟）

   ```html
           /*相邻兄弟选择器*/
           .neiborhod + p{
               background: aqua;
           }
   ```

   

4. 通用选择器：向下相邻所有选中的同层次标签（向下相邻所有兄弟）

   ```html
           /*通用选择器*/
           .neiborhod~p{
               background: green;
           }
   ```



#### 结构伪类选择器

```html
    <style>
        <!--ul的第一个子元素-->
            ul li:first-child{
                background: #ff79ff;
            }

        <!--ul的最后一个子元素-->
            ul li:last-child{
                background: #b3ffb4;
            }

        /*选择p1：定位到父元素，然后按顺序选择第一个元素
            选择p标签的父级元素，选中父级元素的第一个，并且是当前元素才生效
        */
        p:nth-child(2){
            color: #b3ffb4;
        }

        /*选中父级元素，然后按照类型进行选中*/
        p:nth-of-type(2){
            background: beige;
        }
    </style>
```



#### :star:属性选择器（常用）

实际上就是将id和class结合了

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        .demo a{
            float: left;
            display: block;
            height: 50px;
            width: 50px;
            border-radius: 10px;
            background: antiquewhite;
            text-align: center;
            color: #ff79ff;
            text-decoration: none;
            margin-right: 5px;
            font: bold 20px/50px Arial;
        }

        /*属性名，属性名=属性值（正则表达式）
            ‘=’绝对等于
            ‘*=’包含

        */
        <!--存在id属性的元素    a[]{}-->
            a[id]{
                background: #f3ff5f;
            }
            a[id=first]{
                background: #f3ff5f;
            }
        /*class中所有含有link的元素*/
        a[class*="links"]{
            background: #ffd155;
        }

        /*选中href中以http开头的元素*/
        a[href^='http']{
            color: #b3ffb4;
        }

        /*以pdf结尾的元素*/
        a[href$=pdf]{
            color: blueviolet;
        }
    </style>

</head>
<body>

<p class="demo">
    <a href="http://www.baidu.com" class="links items first" id="first">1</a>
    <a href="" class="links items active" target="_blank" title="test">2</a>
    <a href="image/pic.png" class="links item">3</a>
    <a href="image/pic.png" class="links item">4</a>
    <a href="image/pic.png" class="links item">5</a>
    <a href="http://www.bilibili.com" class="links item">6</a>
    <a href="/a.pdf" class="links item">7</a>
    <a href="/abc.pdf" class="links item">8</a>
    <a href="abc.doc" class="links item">9</a>
    <a href="abcd.doc" class="links item last">10</a>

</p>

</body>
</html>
```

> =  绝对相等
>
> *=  包含
>
> ^=  以……开头
>
> $=  以……结尾





### 美化网页元素

#### 为什么要美化网页

1. 有效传递页面信息
2. 美化网页、页面更好看，吸引用户
3. 凸显页面的主题
4. 提高用户体验



#### span标签 ####

重点要突出的字，用span标签套起来

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        #title1{
            font-size: 30px;
        }
    </style>

</head>
<body>

学习 <span id="title1">Java</span>

</body>
</html>
```



#### 改变文本字体样式

> font-family：字体（使用逗号分隔不同的字体）
>
> font-size：字体大小
>
> font-weight：字体粗细
>
> color：字体颜色

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        body{
            /*通过使用逗号将两种字体分隔开，这样英文就用英文字体，中文就用中文字体*/
            font-family: 楷体,"Arial Black";
            color: #ffd155;
        }
        h1{
            font-size: 50px;
        }
        .p1{
           font-weight: bold;
        }
    </style>

</head>
<body>

<h1>Java</h1>

<p class="p1">
    Java是一门面向对象编程语言，不仅吸收了C++语言的各种优点，还摒弃了C++里难以理解的多继承、指针等概念，因此Java语言具有功能强大和简单易用两个特征。
</p>

<p>
    Java语言作为静态面向对象编程语言的代表，极好地实现了面向对象理论，允许程序员以优雅的思维方式进行复杂的编程
</p>

<p>Love is more than a word，

    it says so much.

    When I see these four letters,

    I almost feel your touch.

    This is only happened since，

    I fell in love with you.

    Why this word does this,

    I haven't got a clue.</p>

</body>
</html>
```



#### 文本样式

1. 颜色：color、rbg、rgba
2. 文本对齐的方式：text-align=center
3. 首行缩进：text-indent：2em
4. 行高：line-height
5. 装饰：text-decoration
6. 文本图片水平对齐：vertical-align: middle

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--
    颜色的三种表示：
        单词
        RGB 0-F
        RGBA A：0-1

    text-align：排版
    text-indent: 2em; 段落首行缩进2个位置
    -->
    <style>
        h1{
            /*color: red;*/
            /*color: #b3ffb4;*/
            color: rgba(0,255,255,0.5);
            text-align: center;
        }
        .p1{
            text-indent: 2em;
        }
        .p3{
            background: #b3ffb4;
            height: 300px;
            line-height: 300px;
        }
        .l1{
            /*下划线*/
            text-decoration: underline;
        }
        .l2{
            /*中划线*/
            text-decoration: line-through;
        }
        .l3{
            /*上划线*/
            text-decoration: overline;
        }
        /*水平对齐  参照物a，b{}*/
        img,span{
            vertical-align: middle;
        }
        /* a标签默认带下划线，如果要去下划线，就将值赋值为none就行了 */
        a{
            text-decoration: none;
        }

    </style>

</head>
<body>

<a href="">dasdas</a>

<p>
    <img src="image/pic.png" alt="">
    <span>daosjdoiasidasjo</span>
</p>

<p class="l1">123</p>
<p class="l2">123</p>
<p class="l3">123</p>

<h1>Java</h1>

<p class="p1">
    Java是一门面向对象编程语言，不仅吸收了C++语言的各种优点，还摒弃了C++里难以理解的多继承、指针等概念，因此Java语言具有功能强大和简单易用两个特征。
</p>

<p>
    Java语言作为静态面向对象编程语言的代表，极好地实现了面向对象理论，允许程序员以优雅的思维方式进行复杂的编程
</p>

<p class="p3">Love is more than a word，

    it says so much.

    When I see these four letters,

    I almost feel your touch.

    This is only happened since，

    I fell in love with you.

    Why this word does this,

    I haven't got a clue.
</p>

</body>
</html>
```



#### 文本阴影和超链接伪类

超链接伪类：

1. `a:hover` 鼠标悬浮处的颜色
2. `a:active` 鼠标按住但还未释放时的颜色
3. `a:visited` 鼠标点击后的颜色

阴影：`text-shadow：10px 10px 10px #b3ffb4`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        <!--默认的颜色-->
        a{
            text-decoration: none;
            color: #ffd155;
        }
        /*鼠标悬浮处的颜色*/
        a:hover{
            color: #b3ffb4;
            font-size: 50px;
        }
        /*鼠标按住未释放的状态*/
        a:active{
            color: #ff79ff;
        }
        /*点击后的颜色*/
        a:visited{
            color: green;
        }
        /*阴影（不常用）*/
        #price{
            text-shadow: 10px 10px 10px #b3ffb4;
        }
    </style>

</head>
<body>

<a href="#">
    <img src="../image/pic.png" alt="">
</a>

<p>
    <a href="#"> 码出高效 </a>
</p>

<p>
    <a href="">作者：古井</a>
</p>

<p id="price">
    $99
</p>



</body>
</html>
```



#### 列表样式练习

```css
#nav{
    width: 300px;
    background:#b3ffb4;
}

.title{
    font-size: 18px;
    font-weight: bold;
    text-indent: 1em;
    line-height: 35px;
    background: red;
}

/*
    list-style:
        none 去掉原点
        circle 空心圆
        decimal  数字
        square  正方形
*/
ul li{
    height: 30px;
    list-style: none;
}

a{
    text-decoration: none;
    font-size: 14px;
    color: #ffd155;
}
a:hover{
    color: orange;
    text-decoration: underline;
}
```



#### 背景

背景颜色

```css
background-color: #FAACA8;
```

背景图片，三种平铺方式

```css
        .div1{
            /*水平平铺*/
            background-repeat: repeat-x;
        }

        .div2{
            /*竖直平铺*/
            background-repeat: repeat-y;
        }

        .div3{
            /*垂直平铺*/
            background-repeat: no-repeat;
        }
```

背景颜色和图片可以合起来写作一条语句：

```css
    /*颜色 图片 图片位置*/
    background: red url("../../image/img.png") 270px 10px no-repeat;
```

背景渐变：

```css
        /*背景渐变*/
        /*渐变分为两种：径向渐变、圆形渐变*/
        body{
            background-color: #FAACA8;
            background-image: linear-gradient(19deg, #FAACA8 0%, #DDD6F3 100%);

        }
```

示例代码：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        div{
            width: 1000px;
            height: 700px;
            border: 1px solid red;
            background-image: url("../image/pic.png");/*默认是全部平铺的*/
        }

        .div1{
            /*水平平铺*/
            background-repeat: repeat-x;
        }

        .div2{
            /*竖直平铺*/
            background-repeat: repeat-y;
        }

        .div3{
            /*垂直平铺*/
            background-repeat: no-repeat;
        }

        /*背景渐变*/
        /*渐变分为两种：径向渐变、圆形渐变*/
        body{
            background-color: #FAACA8;
            background-image: linear-gradient(19deg, #FAACA8 0%, #DDD6F3 100%);

        }

    </style>

</head>
<body>

<div class="div1">

</div>

<div class="div2">

</div>

<div class="div3">

</div>

</body>
</html>
```



### 盒子模型及边框使用

#### 什么是盒子

margin：外边距

padding：内边距

border：边框



#### 边框

1. 边框的粗细
2. 边框的样式
3. 边框的颜色

粗细、样式和颜色可以用一行代码就进行设置：`border: 3px solid black;`



#### 外边距

外边距的妙用：居中元素

> margin：0 auto；居中



#### 盒子的计算方式

元素到底有多大：margin+border+padding+内容宽度

> margin：0 auto；居中

```html
<div style="width: 500px; height: 1000px">
    <div style="margin: 0 auto">
        <img src="../image/header.jpg" alt="">
    </div>
</div>
```



#### 代码示例

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        <!--对一些内容的初始化常见操作-->
        /*h1,ul,li,a,body{*/
            /*!*body总有一个默认的外边距margin=0*!*/
            /*margin: 0;*/
            /*padding: 0;*/
            /*text-decoration: none;*/
        /*}*/

        <!--border :粗细，样式，颜色-->
        #box{
            width: 50px;
            border: 1px solid red;
            margin: 0 auto;
        }

        h2{
            font-size: 16px;
            background: antiquewhite;
            line-height: 30px;
            color: cyan;
        }

        form{
            background: #DDD6F3;
        }

        div:nth-of-type(1) input{
            border: 3px solid black;
        }

        input{
            border: 1px solid black;
        }

    </style>

</head>
<body>

<div id="box">
    <h2>会员登陆</h2>
    <form action="#">
        <div>
            <span>用户名：</span>
            <input type="text">
        </div>
        <div>
            <span>密码：</span>
            <input type="text">
        </div>
        <div>
            <span>邮箱：</span>
            <input type="text">
        </div>
    </form>
</div>

</body>
</html>
```



### 圆角边框和阴影

#### 圆角边框

圆角

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--边框是按照左上  右上  右下   左下，顺时针方向-->
    <!--圆圈：
        圆角 = 半径！
    -->
    <style>
        div{
            width: 100px;
            height: 100px;
            border: 10px solid crimson;
            border-radius: 50px 20px 10px 5px;
        }
    </style>

</head>
<body>

<div></div>

</body>
</html>
```

圆：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        div{
            width: 100px;
            height: 100px;
            border: 10px solid crimson;
            border-radius: 100px 100px 100px 100px;
        }
    </style>

</head>
<body>

<div></div>

</body>
</html>
```

扇形：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        <!--以下两种情况都是正确的-->
        /*div{*/
            /*width: 100px;*/
            /*height: 50px;*/
            /*border: 1px solid crimson;*/
            /*border-radius: 50px 50px 0px 0px;*/
        /*}*/
        div{
            width: 100px;
            height: 50px;
            border: 10px solid crimson;
            border-radius: 100px 100px 0px 0px;
        }

        img{
            border-radius: 300px;
        }
    </style>

</head>
<body>

<div></div>

<img src="../image/pic.png" alt="">

</body>
</html>
```



#### 阴影

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--margin：0 auto；居中
        要求：块元素，块元素有固定的宽度
    -->
    <style>
        /*div{*/
            /*width: 100px;*/
            /*height: 100px;*/
            /*border: 10px solid crimson;*/
            /*box-shadow: 10px 10px 1px yellow;*/
        /*}*/

        img{
            border-radius: 50px;
            box-shadow: 20px 20px 20px yellow;
        }
    </style>

</head>
<body>

<div style="width: 500px; height: 1000px">
    <div style="margin: 0 auto">
        <img src="../image/header.jpg" alt="">
    </div>
</div>

</body>
</html>
```





### display和浮动（float）

块级元素：独占一行

> h1~h6    p     div    列表……

行内元素：不独占一行

> span      a        img       strong……



行内元素可以被包含在块级元素中，但反之不行。



#### display

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--
        block  块元素
        inline  行内元素
        inline-block  是块元素，但是可以内联，可以在一行，被称为内块元素
    -->
    <style>
        div{
            width: 100px;
            height: 100px;
            border: 1px solid salmon;
            display: inline;
        }
        span{
            width: 100px;
            height: 100px;
            border: 1px solid indianred;
            display: inline-block;
        }
    </style>

</head>
<body>

<div>div块元素</div>
<span>span行内元素</span>

</body>
</html>
```

这个是一种实现行内元素排列的方式，但是我们很多情况都是用float



#### float

左右浮动float

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
    	div{
            margin: 10px;
            padding: 5px;
        }

        #father{
            border: 1px #000 solid;
        }

        .layer01{
            border: 1px #FAACA8 dashed;
            display: inline-block;
            float: left;
        }

        .layer02{
            border: 1px #ffd155 dashed;
            display: inline-block;
            float: left;
        }

        .layer03{
            border: 1px #b3ffb4 dashed;
            display: inline-block;
            float: left;
        }

        .layer04{
            border: 1px #DDD6F3 dashed;
            font-size: 12px;
            line-height: 23px;
            display: inline-block;
            float: left;
        }
    </style>
</head>
<body>

<div id="father">
    <div class="layer01"><img src="../image/pic.png" alt=""></div>
    <div class="layer02"><img src="../image/header.jpg" alt=""></div>
    <div class="layer03"><img src="../image/img.png" alt=""></div>
    <div class="layer04">浮动的盒子可以向左浮动，也可以向右浮动，直到它的外边缘碰到</div>
</div>

</body>
</html>
```



#### overflow及父级边框塌陷问题

clear：

```
/*
clear: left;  右侧不允许有浮动元素
clear: right;  左侧不允许有浮动元素
clear: both;  两侧不允许有浮动元素
clear: none;  允许周围有浮动元素
*/
```

边框坍塌的解决方案：

1. 增加父级元素的高度：

   ```css
   #father{
       border: 1px #000 solid;
       height: 800px;
   }
   ```

2. 增加啊一个空的div标签

   ```CSS
   <div class="clear"></div>
   
   .clear{
       clear: both;
       margin: 0px;
       padding: 0px;
   }
   ```

3. overflow（常用）:star:

> 在父级元素中增加一个 `overflow：hidden`

```css
#father{
    border: 1px #000 solid;
    overflow: hidden; //或者填auto也行
}
```

4. 为父类增加一个伪类：after（常用）（推荐）:star:

   ```css
   #father:after{
       content: '';
       display: block;
       clear: both;
   }
   ```

小结：

| 浮动元素后面增加空的div       | 简单，代码中尽量避免空div                            |
| ----------------------------- | ---------------------------------------------------- |
| **设置父元素的高度**          | **简单，元素假设有了固定的高度，就会被限制**         |
| **overflow**                  | **简单，但下拉的一些场景要避免使用**                 |
| **为父类添加一个伪类：after** | **写法稍微复杂，但没用其它负面影响，最常用也最推荐** |

对比：

- display
  - 方向不可控
- float
  - 浮动起来的话会脱离标准文档流，所以要解决父级边框的塌陷问题



### 定位

#### 相对定位

相对于自己原来的位置进行偏移

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        div{
            margin: 10px;
            padding: 5px;
            font-size: 12px;
            line-height: 25px;
        }
        #father{
            border: 1px solid salmon;
            padding: 0px;
        }
        #first{
            border: 1px solid lavender;
            /*相对定位*/
            position: relative;
        }
        #second{
            border: 1px solid violet;
            /*相对定位*/
            position: relative;
        }
        #third{
            border: 1px solid darkcyan;
            /*相对定位*/
            position: relative;
        }

    </style>

</head>
<body>

<div id="father">
    <div id="first">第一个盒子</div>
    <div id="second">第二个盒子</div>
    <div id="third">第三个盒子</div>
</div>

</body>
</html>
```

相对定位：position: relative;

相对于原来的位置，进行指定的偏移，如果相对定位的话，它仍然在标准文档流中，原来的位置会被保留。

#### 绝对定位

1. 没用父级元素定位的情况下，那么绝对定位就是标签相对于浏览器边框进行偏移
2. 如果父级元素存在定位，那么绝对定位就是标签相对于父级元素的边框进行偏移

绝对定位：position: absolute;

```html
        #second{
            border: 1px solid violet;
            /*绝对定位*/
            position: absolute;
            right: 30px;
            top: -10px;
        }
```



#### 固定定位 fixed

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        body{
            height: 1000px;
        }
        div:nth-of-type(1){/*absolute 绝对定位*/
            width: 100px;
            height: 100px;
            background: red;
            position: absolute;
            right: 0px;
            bottom: 0px;
        }
        div:nth-of-type(2){/*fixed 固定定位*/
            width: 50px;
            height: 50px;
            background: yellow;
            position: fixed;
            right: 0px;
            bottom: 0px;
        }
    </style>

</head>
<body>

<div>div1</div>
<div>div2</div>

</body>
</html>
```



#### z-index

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        #content{
            padding: 0px;
            margin: 0px;
            overflow: hidden;
            font-size: 12px;
            line-height: 25px;
            border: 1px #000000 solid;
        }

        ul,li{
            padding: 0px;
            margin: 0px;
            list-style: none;
        }

        /*父级元素相对定位*/
        #content ul{
            position: relative;
        }

        .tipText,.tipBg{
            position: absolute;
            width: 380px;
            top: 230px;
        }

        .tipText{
            color: white;
            /*z-index设施的是层级，层级越高，显示在越上层，最低是0，最高无限*/
            z-index: 99;
        }

        .tipBg{
            background: black;
            /*设置透明度，两种写法最好都写上，
                因为opacity是最新的写法，但为了让旧版本的浏览器兼容
                第二个写法就是为了能让不兼容的旧版本浏览器能够正常显示的
                浏览器会自己选择在一个进行加载
            */
            opacity: 0.5;
            filter: alpha(opacity=50);
        }
    </style>
</head>
<body>

<div id="content">
    <ul>
        <li><img src="../image/header.jpg" alt=""></li>
        <li class="tipText">学习</li>
        <li class="tipBg"></li>
        <li>时间：2020-07-14</li>
        <li>地点：地球</li>
    </ul>
</div>

</body>
</html>
```

