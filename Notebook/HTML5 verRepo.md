# Web Developer Learn Notebook For HTML5

## HTML 5

### 网页的基本信息

DOCTYPE：告诉浏览器，我们要使用什么规范

html标签：总标签，html代码全写在这个总标签的内部

注释的快捷键：ctrl+/

head标签：代表网页头部

body标签：代表网页主体

title标签：网页的标题

meta标签：描述性标签，它用来描述我们网站的一些信息。meta标签一般用来做SEO。



### 网页的基本标签

#### 标题标签

```html
<!--标题标签-->
<h1>一级标签</h1>
<h2>二级标签</h2>
<h3>三级标签</h3>
<h4>四级标签</h4>
<h5>五级标签</h5>
<h6>六级标签</h6>
```



#### 段落标签

```html
<!--段落标签-->
<p>文本的第一段</p>
<p>文本的第二段</p>
<p>文本的第三段</p>
<p>文本的第四段</p>
```



#### 换行标签

```html
<!--换行标签，换行标签是一个单标签-->
嘿 <br/>
！<br/>
换行<br/>
```



#### 水平线标签

```html
<!--水平线标签-->
<hr/>
```



#### 字体样式标签

```html
<!--粗体和斜体-->
<h1>字体样式标签</h1>
粗体： <strong>这是粗体</strong><br/>
斜体： <em>这是斜体</em>
```



#### 注释和特殊符号

```html
<!--特殊符号-->
<p>空格： &nbsp;</p>
<h2>我要空&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;格</h2>

<p>大于符号： &gt; </p>
<p>小于符号： &lt; </p>

<p>版权符号： &copy;</p>
```



### 图像标签

常见的图像格式：JPG、GIF、PNG、BMP（位图）……

图像标签：img

图像标签中的各种属性：

1. src（必须）：图像的地址
2. alt（必须）：图像的替代文字
3. title（可选）：鼠标悬停提示文字
4. width（可选）：图像宽度
5. height（可选）：图像高度

```html
<!-- img学习
src：图片地址（分为相对地址和绝对地址）
       ‘../’代表上一级目录
src 和 alt是必填的
-->
<img src="resources/image/eigenvalue.jpg" alt="Eigenvalue" title="悬停文字">
```



### 超链接标签

文本超链接

图像超链接

href：链接路径

target：链接在那个窗口打开

常用值：_self 、 _blank

应用1：在新窗口打开还是在本窗口打开

```html
<a href="htmlDemo1.html" target="_blank">点击跳转到第一个html文件的页面中</a>
<a href="https://www.baidu.com" target="_blank">点击跳转到百度</a>
```

应用2：图像超链接，点击图像跳转页面

```html
 <!--图像超链接，点击图像跳转页面-->
    <a href="MainTag.html" target="_self">点击图像和文字都能跳转到MainTag文件的页面
        <img src="resources/image/pic.png" alt="Eigenvalue" title="悬停文字">

    </a>
```

应用3：锚标签，回到顶部

```html
<a href="#top">回到顶部</a>
```

应用4：功能性链接，邮箱链接

```html
<!--功能性链接
    邮件链接： mailto
-->
<a href="mailto:12345678@qq.com">点击启动邮箱并联系我</a>
```



### 行内元素和块元素

块元素

1. 无论内容多少，该元素独占一行
2. （p、h1-h6……）

行内元素

1. 内容撑开宽度，左右都是行内元素的可以排在一行
2. （a、strong、em……）



### 列表标签

#### 有序列表

ol标签

```html
<!--有序序列-->
<ol>
    <li>Java</li>
    <li>python</li>
    <li>c</li>
    <li>C++</li>
    <li>前后端</li>
</ol>
```

#### 无序列表

ul标签

```html
<!--无序列表-->
<ul>
    <li>Java</li>
    <li>python</li>
    <li>c</li>
    <li>C++</li>
    <li>前后端</li>
</ul>
```

#### 自定义标签

dl：标签

dt：列表名称

dd：列表内容

```html
<!--自定义列表
    dl:标签
    dt：列表名称
    dd：列表内容
-->
<dl>
    <dt>列表名称</dt>

    <dd>Java</dd>
    <dd>python</dd>
    <dd>Linux</dd>
    <dd>C</dd>
    <dd>位置</dd>

    <dd>西安</dd>
    <dd>成都</dd>
    <dd>北上广</dd>
    <dd>前后端</dd>

</dl>
```



### 表格标签

为什么使用表格：

1. 简单通用
2. 结构稳定

基本结构：

1. 单元格：利用border属性调整单元格的边框大小
2. 行：tr
3. 列：td
4. 跨行：colspan
5. 跨列：rowspan

小练习：

```html
<!--小练习-->
<table border="1px">
    <tr>
        <td colspan="3">学生成绩</td>
    </tr>
    <tr>
        <td rowspan="2">张三</td>
        <td>语文</td>
        <td>90</td>
    </tr>
    <tr>
        <td>数学</td>
        <td>85</td>
    </tr>
    <tr>
        <td rowspan="2">李四</td>
        <td>语文</td>
        <td>88</td>
    </tr>
    <tr>
        <td>数学</td>
        <td>95</td>
    </tr>
</table>
```



### 媒体元素

视频元素和音频元素

> src：资源路径
>
> controls：能够让页面中出现视频播放选项
>
> autoplay：能够让视频自动播放

```html
<!--音频和视频
    src：资源路径
    controls：能够让页面中出现视频播放选项
    autoplay：能够让视频自动播放
-->
<video src="resources/video/test.mp4" controls="controls" autoplay="autoplay"></video>
<audio src="resources/audio/test.mp3" controls="controls" autoplay="autoplay"></audio>
```



### 页面结构分析

| 元素名  | 描述                                               |
| ------- | -------------------------------------------------- |
| header  | 标记头部区域的内容（用于页面或页面中的一块区域）   |
| footer  | 标记脚部区域的内容（用于整个页面或页面的一块区域） |
| section | Web页面中的一块独立区域                            |
| article | 独立的文章内容                                     |
| aside   | 相关内容或应用（常用于侧边栏）                     |
| nav     | 导航类辅助内容                                     |

```html
<header> <h2>页面头部</h2></header>

<section> <h2>网页主体</h2></section>

<footer> <h2>页面脚部</h2></footer>
```



### iframe内联框架

> src：引用页面地址
>
> name：框架标识名

```html
<!--iframe内联框架
    src：地址
    name：识别标签，其它标签可以通过将name中的内容写入其它标签中target进行跳转
    w、h：内联标签在页面中占用的窗口大小
-->
<iframe src="http://www.baidu.com" name="百度" frameborder="0" width="1000" height="800"></iframe>

<!--通过内联框架中的name实现跳转-->
<a href="" target="百度">点击跳转</a>
```



### :star:表单

> form：表单标签
>
> method：规定如何发送表单数据，常用值有：POST、GET
>
> action：表示向何处发送表单数据，表单提交的位置，可以是网站，也可以是一个请求处理地址

```html
<!--表单
    action：表单提交的位置，可以是网站，也可以是一个请求处理地址
    method:post,get提交方式
        get：我们可以在url中看到我们提交的信息，不安全，但高效，不可以传输大文件
        post：比较安全，可以传输大文件
-->
<form action="MainTag.html" method="post">
    <!--文本输入框：input type=“text”-->
    <p>名字: <input type="text" name="username"></p>

    <!--密码框：input type=“password”-->
    <p>密码：<input type="password" name="password"></p>


    <p>
        <input type="submit">
        <input type="reset">
    </p>
    
</form>
```

表单元素格式：

| 属性      | 说明                                                         |
| :-------- | :----------------------------------------------------------- |
| type      | 指定元素的类型。text、password、checkbox、radio、submit、reset、file、hidden、image和button，默认为text |
| name      | 指定表单元素名称                                             |
| value     | 元素的初始值。type为radio时必须指定一个值。                  |
| size      | 指定表单元素的初始宽度。当type为text或password时，表单元素的大小以字符为单位。对于其它类型，宽度以像素为单位。 |
| maxlength | type为text或password时，输入的最大字符数                     |
| checked   | type为radio或checkbox时，指定按钮是否是被选中。              |
| disabled  | 禁用某个选项                                                 |
| hidden    | 隐藏某个表单                                                 |
| readonly  | 只读                                                         |



#### 文本框和单选框

```html
 <!--文本输入框
        value="xcosmosbox" 默认初始值
        maxlength="8" 最大可输入长度
        size="30" 输入框的长度
    -->
    <p>名字: <input type="text" name="username" value="xcosmosbox" maxlength="8" size="30"></p>

<!--单选框标签
        input type="radio"
        value：单选框的值
        name：表示组，一个组内的选择只能选一个
    -->
    <p>性别：
        <input type="radio" value="boy" name="sex">男
        <input type="radio" value="girl" name="sex">女
    </p>
```



#### 按钮和多选框

多选框：checkbox

普通按钮：button

图片按钮：image

提交按钮：submit

重置按钮：reset

```html
<!--多选框
        input type="checkbox"
    -->
    <p>爱好：
        <input type="checkbox" value="sleep" name="hobby">睡觉
        <input type="checkbox" value="code" name="hobby">敲代码
        <input type="checkbox" value="chat" name="hobby">聊天
        <input type="checkbox" value="game" name="hobby">打游戏
    </p>
    
    
    <!--按钮
        input type="button"  普通按钮
        input type="image"   图片按钮
        input type="submit"  提交按钮
        input type="reset"   重置按钮
    -->
    <p>按钮：
        <input type="button" name="btn1" value="点击下载">
        <input type="image" src="resources/image/pic.png">
    </p>
    <p>
        <input type="submit">
        <input type="reset" value="清空表单">
    </p>
```





#### 列表框、文本域和文件域

列表框：select标签

文本域：textarea标签

文件域：file

```html
    <!--下拉框，也叫列表框
        select 下拉框
        selected 默认选择
    -->
    <p>国家：
        <select name="列表名称" id="">
            <option value="选项的值" >中国</option>
            <option value="选项的值">美国</option>
            <option value="选项的值">瑞士</option>
            <option value="选项的值" selected>日本</option>
        </select>
    </p>

    <!--文本域
         cols="30" rows="10"
    -->
    <p>反馈：
        <textarea name="textarea" cols="30" rows="10">文本内容</textarea>
    </p>

    <!--文件域
        input type="file"
        name="files"
    -->
    <p>
        <input type="file" name="files">
        <input type="button" value="上传" name="upload">
    </p>
```





#### 搜索框滑块和简单验证

html中的简单验证实际上非常不智能，在实际开发过程种应使用正则表达式取进行验证，以下仅作为语法进行了解

```html
    <!--邮箱验证-->
    <p>邮箱：
        <input type="email" name="email">
    </p>
    <!--URL验证-->
    <p>URL:
        <input type="url" name="url">
    </p>
    <!--数字验证-->
    <p>数字：
        <input type="number" name="number" max="100" min="0" step="10">
    </p>


    <!--滑块-->
    <p>音量：
        <input type="range" name="voice" min="0" max="100" step="1">
    </p>


    <!--搜索框-->
    <p>搜索：
        <input type="search" name="search">
    </p>
```



#### 表单的初级验证

常用方法：

1. placeholder  提示信息
2. required  非空判断
3. pattern  正则表达式

```html
    <p>名字: <input type="text" name="username" value="xcosmosbox" maxlength="8" size="30" placeholder="请输入用户名"></p>

    <p>密码：<input type="password" name="password" required></p>
    
        <p>自定义邮箱：
        <input type="text" pattern="^\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$">
    </p>
```



