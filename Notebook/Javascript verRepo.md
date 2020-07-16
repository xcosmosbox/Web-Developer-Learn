# Web Developer Learn Notebook For JavaScript

## JavaScript

### 快速入门

------

#### 引入JavaScript

1. 内部标签引入

   ```html
       <!--script标签内，写JavaScript代码-->
       <script>
           alert('hello world');
       </script>
   ```

   

2. 外部引入

   ```html
       <!--外部引入-->
       <!--不用显性的去写出type，因为默认会自动写入 type=‘text/javascript’-->
       <script src="demo1.js"></script>
   ```

   

#### 基本语法入门

JavaScript严格区分大小写

var 是全局变量

条件控制的语法和Java一样

打印的语句是

```html
alert(信息)
```

console.log(变量) 在浏览器的控制台打印变量

示例代码：

```html
    <!--JavaScript严格区分大小写-->
    <script>
        // 1.定义变量   变量类型  变量名=变量值;
        // let 是局部变量
        // var 是全局变量
        // const 是常量
        var  score = 70;

        // 2.条件控制
        if (score>10 && score<70){
            alert('1');
        }
        else if (score>70) {
            alert("2")
        }
        else {
            alert('3')
        }

        // console.log(变量) 在浏览器的控制台打印变量
    </script>
```



#### 数据类型

数值、文本、图形、音频、视频……都属于数据类型



##### number

js不区分小数和整数，小数、整数和科学计数法都统称和Number



##### 字符串

与python一致



##### 布尔值

与Java一样



##### 逻辑运算

```
&&  两个都为真，结果为真
||  一个为真，结果为真
！  取反
```



##### 比较运算符

```
=
==  等于（类型不一样，值一样，也会判断为true，例如数字1和字符串“1”，用等于符号判断是相等的）
===  绝对等于（类型和数值都必须一样，所以在JavaScript中常用绝对等于）
```

这是JavaScript的一个缺陷，为了避免错误，在JavaScript中要坚持使用绝对等于

注意：

- NaN === NaN 的结果是false，这是因为NaN与所有的数值都不相等，包括它自己。
- 只能通过`inNaN(NaN)`来判断这个数是不是NaN



##### 浮点数问题

```
（1/3）===（1-2/3） 的结果是false
```

尽量避免使用浮点数进行运算，存在精度问题。



#####  null和undefined

- null 空
- undefined 未定义



##### 数组

一个数组中可以存储多个不同类型的值

```javascript
//保证代码的可读性，尽量使用[]
var arr = [1,3,4,"2","s",true,3.3];

new Array(1,3,4,"HELLO",'hey');
```

在JavaScript中，如果取数组下标越界了，不会报越界的异常，而是会返回undefined



##### 对象

数组是中括号，对象是大括号。每个属性之间使用逗号隔开，最后一个不需要添加。

```javascript
        var person = {
            name:"zhangsan",
            age:18,
            tags:['js','java','javascript','python']
        }
```

取对象中的值

```javascript
person.age
>> 18
person.name
>> "zhangsan"
```



##### 严格检查模式

`use strict`：严格检查模式，必须写在JavaScript的第一行

let 是局部变量

var 是全局变量

const 是常量



### 数据类型

------

#### 字符串

1. 正常字符串我们使用单引号，或者双引号

2. 注意转义字符 \

   ```javascript
   \'
   \n
   \t
   \u4e2d  //Unicode字符
   ```

3. 多行字符串编写（就是tab建上面）

   ```javascript
           var msg = `
               你好啊
               啊
               哈哈
               231
               name
               true
               嘿
               ！
           `
   ```

4. 模板字符串（同样需要使用tab键上面那个键） 

   ```javascript
           let name = "zhangsan";
           let age = 18;
           let str = `你好啊，${name}`;
           
          	>> 你好啊，zhangsan
   ```

5. 字符串长度

   ```javascript
   console.log(str.length)
   ```

6. 字符串的可变性：不可变

7. 大小写转换的方法

   ```javascript
   //注意，这里是方法，不是属性
   str.toUpperCase() //变大写
   str.toLowerCase() //变小写
   ```

8. `str.indexOf(’t‘)`

9. substring

   ```javascript
   作用域：[，)
   str.substring(1) //从第一个字符串截取到最后一个字符串
   str.substring(1，3) // [1,3)
   ```

   

#### 数组

Array可以包含任意的数据类型

1. 长度

   ```
   arr.length
   ```

   注意：加入给arr.length赋值，数组的大小就会发生变化，被扩展的部分的值是undefined，如果赋值过小（小于原来的长度），元素就会丢失

2. indexOf，通过元素获得下标索引。注意，在查询的过程中，查询数组中的数字1和数组中的字符串“1”，结果是不同的

3. `slice()`：截取Array的一部分，返回一个新数组，类似于String中的substring方法

4. `push()`：在数组的尾部加入新的值。`pop()`：弹出尾部的一个元素

   ```
   push：压入尾部
   pop：弹出尾部的一个元素
   ```

5. `unshift`，`shift` 头部

   ```
   unshift：压入到头部
   shift：弹出头部的一个元素
   ```

6. `sort()`：排序，前提是要排序的数组中，类型必须一致

7. `reverse()`：元素反转

8. `concat()`：并没有修改数组，而是在原数组的后面拼接一个数组，并将新数组返回

9. `join()`：连接符，打印拼接的数组，使用特定的字符串连接

   ```
   ["A","B","C"]
   arr.join('-')
   
   >> "A-B-C"
   ```

10. 多维数组

    ```
    arr = [[1,2],[3,4],["5","6"]]
    arr[1][1]
    
    >> 4
    ```



#### 对象

若干个键值对。

```javascript
var 对象名 = {
	属性名：属性值，
	属性名：属性值，
	属性名：属性值，
	……
	……
	属性名：属性值
}
```

JavaScript中，{……}表示一个对象，键值对描述属性，多个属性之间使用逗号隔开，最后一个属性不加逗号。

> :star:注意：JavaScript中的所有的键都是字符串，值是任意对象！:star:

1. 对象赋值

   ```
   对象名.对象的属性 = 将要赋的值
   ```

2. 使用一个不存在的对象属性，不会报错，而是返回undefined

3. 动态的删减属性，通过`delete`删除对象的属性

   ```
   delete 对象名.对象的属性
   ```

4. 动态的添加，直接给新的属性添加值即可

   ```
   对象名.新增加的属性 = 赋值
   ```

5. 判断属性值是否在这个对象中： xxx in xxx

   ```
   'age' in person
   >> true
   
   //继承
   'tostring' in person
   >> true
   ```

6. 判断一个属性是否是这个对象自身拥有的：`hasOwnProperty()`



### 流程控制

if判断（与Java没区别）

```javascript
        if (score>10 && score<70){
            alert('1');
        }
        else if (score>70) {
            alert("2")
        }
        else {
            alert('3')
        }
```

while循环（与Java没区别）

for循环（与Java没区别）



forEach 循环（这是JavaScript的原生for each循环，跟Java的不一样）

```javascript
var age = [12,3,47,32,19,20]

age.forEach(function (value){
	console.log(value)
})
```



for……in…… 循环（JavaScript中的for循环类似于Java的for each循环的python的for循环的结合体）：

```
var age = [12,3,47,32,19,20]

for(let num in age){
	console.log(age[num])
}
```



### Map和Set

> Map和Set是Es6新特性

Map：

```javascript
        //学生的map成绩
        var map = new Map([['tom',100],['jack',90]]);
        var name = map.get('tom'); //通过key获得value
        map.set('admin',12345);//向map集合的尾部添加一个键值对(也可以用于修改，如果其中有一个相同的键)
        map.delete('tom');//删除一个键值对
        console.log(name);
```

Set：

```javascript
        //创建一个set集合
        //注意：Set集合是一个无序不重复的集合
        var set = new Set([3,1,1,1,1]);
        set.add(2); //添加
        set.delete(1); //删除
        console.log(set.has(3)); //判断是否包含某个元素
```





### iterator

用迭代器遍历Map集合：

1. 遍历数组

   ```javascript
           //通过for of遍历数组
           var arr = [3,4,5];
           for(let x of arr){
               console.log(x);
           }
   ```

   

2. 遍历Map

   ```javascript
           var map = new Map([['tom',100],['jack',90]]);
           //遍历map
           for (let x of map){
               console.log(x);
           }
   ```

   

3. 遍历Set

   ```
           var set = new Set([3,1,1,1,1]);        			//遍历set
           for (let x of set){
               console.log(x);
           }
   ```

   



### 函数



#### 定义函数

所有的函数都是用`function`关键字定义的

> 定义方式一：(推荐)

```javascript
//绝对值函数
        function abs(x) {
            if (x>=0){
                return x;
            }
            else
            {
                return -x;
            }
        }
```

一旦执行到return代表函数结束，返回结果！

如果没用执行return，函数执行完也会返回结果，会返回一个undefined



> 定义方式二：

```javascript
	var abs = function(x){
	        if (x>=0){
                return x;
            }
            else
            {
                return -x;
            }
	}
```

用方式二定义的函数是一个匿名函数，但是可以把结果赋值给abs，通过abs就可以调用函数了。



#### 调用函数

```javascript
abs(10)
abs(-10)
```

参数问题：在JavaScript中可以传递任意个参数，也可以不传递参数

假设不存在参数，如何进行规避：

```javascript
        function abs(x) {
            //手动抛出异常来判断
            if (typeof x!= 'number'){
                throw 'Not a number!'
            } 
            if (x>=0){
                return x;
            }
            else
            {
                return -x;
            }
        }
```



> arguments

`arguments`是一个JS内置的关键字。代表传递进来的所有参数，`arguments`是一个数组。

```javascript
        function abs(x) {
            //手动抛出异常来判断
            if (typeof x!= 'number'){
                throw 'Not a number!'
            }
            
            //当传递了多个参数进来时，可以使用arguments来打印多余的参数
            for (let i=0; i<arguments.length; i++){
                console.log(arguments[i]);
            }
            
            if (x>=0){
                return x;
            }
            else
            {
                return -x;
            }
        }
```

但此时会出现一个问题：arguments包含了所有的参数，我们有时候需要使用多余的参数来进行额外的操作，此时就需要排除已有的参数。但问题在于，假如程序运行多次的过程中，每次传递过来的多个参数顺序是不固定的话，我们就无法正确知道已有参数在那个位置，自然也就无法正常的排除那个参数了。



> rest

为了解决上述的问题，新特性中出现了`rest`关键字。

以前：

```javascript
if(arguments.length>2){
	for(let i=2; i<arguments.length; i++){
		//……
	}
}
```

现在，新特性允许我们获取已经定义的参数之外的所有参数：

```javascript
        // ...rest是固定写法
        function example(a,b,...rest) {
            console.log("a=>"+a);
            console.log("b=>"+b);
            console.log(rest);
        }
```

rest参数只能写在最后面，必须用`...rest`标识



### 变量的作用域

在JavaScript中，var定义变量实际是有作用域的。

假设在函数体中声明，则在函数体外不可以使用（如果一定要使用的话，就需要用`闭包`来实现了）

```javascript
        function f1() {
            var x = 1;
            x = x + 1;
        }
        console.log(x);  //Uncaught ReferenceError: x is not defined

```



如果两个函数使用了相同的变量名，只要在函数内部，那就不冲突。

内部函数可以访问外部函数的成员，反之则不行

```javascript
        function f2() {
            var x = 1;
            
            //内部函数可以访问外部函数的变量
            function f3() {
                var y = x + 1;
            }
        }
```



假设，内部函数变量和外部函数的变量重名：

```javascript
        function q1() {
            var x = 1;
            function q2() {
                var x = 'A';
                console.log('inner'+x); //innerA
            }
            console.log('outer'+x); //outer1
            q2();
        }
```

假设在JavaScript中函数查找变量从自身函数开始，由内向外查找，假设外部存在这个同名的函数变量，则内部函数会屏蔽外部函数的变量。



> 提升函数的作用域

```javascript
        function q3() {
            var x = "x" + y;
            console.log(x);
            var y = 'y';
        }
```

结果： x undefined

说明：js执行引擎，自动提升了y 的声明，但是不会提升变量y的赋值。

为了避免出错，所以需要养成将所有的变量定义在函数内部的最前面这样一个良好的习惯。



> 全局函数

```javascript
        //全局变量
        var m = 1;
        function f5() {
            console.log(m);
        }
        f5();
        console.log(m);
```



> 全局变量window

```javascript
        var n = 'nnn';
        alert(n);
        alert(window.n); //默认所有的全局变量，都会自动绑定在window对象下
```

`alert()`这个函数本身也是一个window下的变量



综上：JavaScript实际上只有一全局作用域，任何变量（函数也可以视为变量），假设没用在函数作用范围内找到，就会自动向外查找，如果在全局作用域都没用找到，则会报`RefrenceError`错误



> 规范

由于我们所有的全局变量都会自动绑定在window上，如果不同的js文件，使用了相同的全局变量，那么该如何解决或减少冲突？

解决方法：将自己的代码全部放入自己定义的唯一空间名字中，降低全局命名冲突的问题。

```javascript
        //唯一全局变量
        var V  = {};

        //定义全局变量
        V.name = "zhangsan";
        V.add = function (a,b) {
            return a+b;
        }
```



> 局部作用域 let

虽然var的作用域不能在函数外调用，但是在函数内的同级调用是允许的，所以为了避免这种情况的出现，例如只让变量的作用域作用于一个for循环中，那么就需要使用`let`函数



> 常量 const

常量的常量名要全部大写（与Java一样），常量在JavaScript中被称为只读变量。





### 方法的定义和调用

> 定义方法

方法就是把函数放在对象的里面，因为对象只含有两个东西：属性和方法。（记得调用方法的时候要带`()`）

```javascript
        var java = {
            name:'zhangsan',
            birth:2000,

            //这个就叫方法
            age:function () {
                //今年减去出生年
                var now = new Date().getFullYear();
                return now-this.birth;
            }
        }
```

`this.`代表什么？将上面的代码拆开看就好明白了

```javascript
        var java = {
            name:'zhangsan',
            birth:2000,

            //这个就叫方法
            age:getAge
        }
        
        function getAge() {
            //今年减去出生年
            var now = new Date().getFullYear();
            return now-this.birth;
        }
        
>>> java.age() 这是正确的调用方法的方式
```

this是无法改变指向的，是默认指向调用它的那个对象。



> apply

在js中，可以用apply控制this的指向

```javascript
        // 此时，this. 指向了java，且参数为空。
        getAge.apply(java,[]);
```





### 常见的内部对象

> 标准对象

```javascript
typeof 123
"number"
typeof '123'
"string"
typeof true
"boolean"
typeof NaN
"number"
typeof []
"object"
typeof {}
"object"
typeof Math.abs
"function"
typeof Symbol
"function"
typeof undefined
"undefined"
```



#### Date

基本使用：

`getFullYear()`：返回现在的年份

`getMonth()`：返回现在的月份

`getDate()`：返回现在的日份

`getDay()`：返回现在是星期几

`getHours()`：返回现在的时

`getMinutes()`：返回现在的分

`getSeconds()`：返回现在的秒

`getTim()`：返回现在的时间戳（时间戳全球统一，是以1970年一月一日的格林威治时间开始计算的）



转换：

`toLocaleString()`：返回现在的本地时间

`toGMTString()`：返回现在的北京时间



#### JSON

JSON是一种轻量级的数据交换格式。它的层次结构非常简洁清晰，且易于人们阅读和编写，同时也易于及其解析和生成，并有效的提升网络传输效率。

在JavaScript中一切皆为对象，任何js支持的类型都可以用JSON来表示。

格式：

- 对象用{}
- 数组用[]
- 所有的键值对都用key:value



JSON字符串和JS对象的转换：

```javascript
        var user = {
            name:"zhangsna",
            age:18,
            sex:"男"
        };

        //将对象转换为json字符串
        var jsonUser = JSON.stringify(user);

        //json字符串转换为对象
        var obj = JSON.parse('{"name":"zhangsna","age":18,"sex":"男"}')
```



很多人搞不清楚JSON和JS对象的区别：

```
var js = {a:"a",b:"b"}; //js里面是个键值对
var json = {'{"a":"a","b":"b"}'} //json里面全部都是字符串
```



#### Ajax

- 原生的js写法，xhr异步请求
- jQuery封装好的方法
- axios请求



### 面向对象编程

类：模板

对象：具体的实例

原型：对象示例化之前的模板

```javascript
        //人类原型
        var Person = {
            name:"renlei",
            age:18,
            state:"run",
            run:function () {
                console.log(this.name + " run......");
            }
        };

        //小明首先创建了自己的名字，并将自己的原型指向人类（这个时候就同时实现了继承和多态）
        var xiaoming = {
            name: "xiaoming"
        };
        xiaoming.__proto__ = Person; //此时就完成了对于原型的实例化，此时才能被称作为一个对象
```



##### class继承

`class`关键字，利用`extends`关键字继承对象，其构造方法的名字必须写成`constructor`，同时，继承的类也需要用`super`去实现父类的构造方法

```javascript
        class Student{
            constructor(name){
                this.name = name;
            };

            hello(){
                alert("hello "+this.name);
            };
        }

        //初始化小明
        var xiaoming = new Student("xiaoming");

        //大学生类继承学生类
        class collegeStudent extends Student{
            constructor(name,grade){
                super(name);
                this.grade = grade;
            }

            myGrade(){
                alert("我叫"+this.name+" 我的年级是 "+this.grade);
            }
        }

        //初始化小红
        var xiaohong = new collegeStudent("xiaohong",14);
```



> 原型链

在JavaScript中，每个函数都有一个prototype属性，这个属性指向函数的原型对象。所有对象的原型最终都会指向Object，而Object的原型也会指向Object，此时就形成了原型链。



### 操作BOM对象（重点）:star:

> 浏览器介绍

JavaScript和浏览器的关系？

JavaScript的诞生就是为了能够让他在浏览器中运行。

BOM：浏览器对象模型

- IE浏览器
- Chrome
- Safari
- FireFox
- Opera



> window

window代表 浏览器窗口

`window.innerHeight`：内部窗口高度

`window.innerWidth`：内部窗口宽度

`window.outerHeight`：浏览器窗口高度

`window.outerWidth`：浏览器窗口宽度



> Navigator

Navigator封装了浏览器的基本信息

```javascript
navigator.appName
"Netscape"
navigator.appVersion
"5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36"
navigator.userAgent
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36"
navigator.cookieEnabled
true
```



> screen

```javascript
screen.width
1280
screen.height
800
```



> location（重要）

location代表当前页面的URL信息。

以百度的网页为例：

```javascript
host: "www.baidu.com"
href: "https://www.baidu.com/"
protocol: "https:"
reload: ƒ reload() //刷新网页
location.assign('url') //重定向网页
```



> document

document代表当前的页面，HTML DOM文档树

```
document.title
“百度一下“
```



获取具体的文档树节点：

```html
<body>

<dl id="app">
    <dt>java</dt>
    <dd>javaee</dd>
    <dd>javase</dd>
    <dd>javascript</dd>
</dl>

<script>
    var dl = document.getElementById('app');
</script>

</body>
```

好处，能动态的修改网页。



获取cookie：

```java
document.cookie
"BIDUPSID=1C2CDD4B66BF4F836A6218381F897A84; PSTM=1565155053; BD_UPN=12314753; BAIDUID=227104D47D3C80EEA5F34CAC017CD675:FG=1; MCITY=-%3A; BDORZ=B490B5EBF6F3CD402E515D22BCDA1598; COOKIE_SESSION=20_1_5_3_4_9_1_1_4_3_3_1_92490_0_0_0_1594648683_1594648682_1594689623%7C9%23528072_20_1594648682%7C9; __yjsv5_shitong=1.0_7_fb0865d64a4a7c6c0f421194eba4afdeaa2d_300_1594866706966_222.209.63.189_01b2d815; BD_HOME=1; H_PS_PSSID=32219_1426_32139_32045_32230_32258_26350; sugstore=0"
```



> history（不建议使用）

history代表浏览器的历史记录

```javascript
history.back() //网页后退
history。forward() //网页前进
```



### 操作DOM对象（重点）:star:

DOM：文档对象模型

> 核心

浏览器网页就是一个DOM树形结构

- 更新：更新DOM节点
- 遍历DOM节点：得到DOM节点
- 删除：删除一个DOM节点
- 添加：添加一个新的DOM节点

要操作一个DOM节点，就必须要先获得这个DOM节点



> 获取DOM节点

```html
<div id="father">
    <h>title</h>
    <p id="p1">p1</p>
    <p class="p2">p2</p>
</div>


<script>
    
    //对应css中的选择器
    var h1 = document.getElementsByTagName('h1');
    var h1 = document.getElementById('p1');
    var h1 = document.getElementsByClassName('p2');
    var father = document.getElementById('father')

    var childrens = father.children; //获取父节点下所有的子节点
    // father.firstChild 获取父节点下第一个子节点
    // father.lastChild 获取父节点下最后一个子节点

</script>
```

以上是原生代码，之后会学习到更简单的jQuery()；，并尽量都使用jQuery。



> 更新节点

```javascript
<div id="id1"></div>

<script>

    //得到id1中的内容并将结果返回给变量
    var id1 = document.getElementById('id1');
    
</script>
```

操作文本

- `id1.innerText = '456';`修改文本的值
- `id1.innerHTML = '<strong>123</strong>'`可以解析HTML文本标签

操作css

```javascript
    //操作css
    id1.style.color = 'red'; //属性使用字符串包裹
    id1.style.fontSize = '20px';
    id1.style.padding = '2em';
```



> 删除节点

删除节点的步骤：先获取父节点，再通过父节点才能删除自己。

```javascript
<div id="father">
    <h>title</h>
    <p id="p1">p1</p>
    <p class="p2">p2</p>
</div>

<script>
    //创建p1的选择器
    var p1 = document.getElementById('p1');
    //通过p1的指针得到p1的父节点
    var father = p1.parentElement;

    //通过父节点删除p1
    father.removeChild(p1)
</script>
```

注意：删除多个节点的时候，children是在时刻变化的，每个节点对应的下标是在实时变动的。（例如三个节点删除了一个还剩两个，那么原本小标为2的节点，现在下标就是1了）



> 插入节点

我们获取某个DOM节点，假设这个DOM节点是空的，我们通过`innerHTML`就可以增加一个元素了，但是这个DOM节点已经存在元素了，我们就不能这么干了！因为会产生覆盖！

追加：

方法一：将已存在的标签插入

```javascript
<p id="js">JavaScript</p>
<div id="list">
    <p id="ee">javaee</p>
    <p id="se">javase</p>
    <p id="me">javame</p>
</div>

<script>
    <!-- 方法1
        将已存在的节点插入
    -->
    //获取指针
    var js = document.getElementById('js'); //这个是一个已存在的节点
    var list = document.getElementById('list');

    //追加标签
    list.appendChild(js);
</script>
```



方法二：创建一个新节点并插入

```javascript
<p id="js">JavaScript</p>
<div id="list">
    <p id="ee">javaee</p>
    <p id="se">javase</p>
    <p id="me">javame</p>
</div>

<script>
   <!-- 方法2
        创建一个新的节点并插入
    -->
    //通过JS创建一个新的节点
    var newP = document.createElement('p') //创建一个p标签
    newP.id = 'newP';
    newP.innerText = "hello,world";

    //追加标签
    list.appendChild(newP);
</script>
```



练习：用JavaScript来创建一个导入外部JavaScript的新标签并插入

```javascript
    //通过这样的属性，就能设置任意的值了。
    var myScript = document.createElement('script');
    myScript.setAttribute('type','text/javascript'); //键值对
```





### 操作表单

> 表单是什么？ form标签 、 DOM树

- 文本框  text
- 下拉框  <select>
- 单选框  radio
- 多选框  checkbox
- 隐藏域  hidden
- 密码框  password
- ……

表单的目的：提交信息



> 获取提交的信息

```javascript
<form action="post">
    <p>
        <span>用户名：</span><input type="text" id="username">
    </p>

    <p>
        <span>性别：</span>
        <input type="radio" name="sex" value="man" id="boy"> 男
        <input type="radio" name="sex" value="woman" id="girl"> 女

    </p>
</form>

<script>
    //获取指针
    var inputText = document.getElementById('username');
    var boy_radio = document.getElementById('boy');
    var girl_radio = document.getElementById('girl');

    //得到输入框的值
    inputText.value;
    //修改输入框的值
    inputText.value = '123';

    //对于单选框，多选框等等，用value只能拿到当前的值
    boy_radio.checkbox; //查看返回的结果，是否为true，如果为true，则被选中
    girl_radio.checked = true; //赋值
</script>
```



### jQuery

jQuery库中存在大量的JavaScript函数

> 获取jQuery

```html
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--导入jQuery，因为是导入的微软的，所以还存在CDN加速-->
    <script src="http://ajax.aspnetcdn.com/ajax/jQuery/jquery-2.1.1.min.js"></script>

</head>
```



jQuery公式：`$(selector).action()`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--导入jQuery，因为是导入的微软的，所以还存在CDN加速-->
    <script src="http://ajax.aspnetcdn.com/ajax/jQuery/jquery-2.1.1.min.js"></script>

</head>
<body>

<a href="" id="test-jquery">点击此处</a>

<script>
    //jQuery公式的本质其实就是css的选择器
    $('#test-jquery').click(function () {
        alert('hello jQuery!');
    })
</script>

</body>
</html>
```



> 选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--导入jQuery，因为是导入的微软的，所以还存在CDN加速-->
    <script src="http://ajax.aspnetcdn.com/ajax/jQuery/jquery-2.1.1.min.js"></script>
</head>
<body>

<script>
    //jQuery中的标签、id、class选择器
    $('p').click(); //标签选择器
    $('#id').click(); //id选择器
    $('.class').click(); //class选择器
</script>

</body>
</html>
```



> 事件

节点文本操作

```html
    $('#test-ul li[name=python]').text(); //获得值
    $('#test-ul li[name=python]').text('123'); //设置值
    $('#test-ul').html(); //获得值
    $('#test-ul').html('<strong>123</strong>'); //设置值
```

css操作

```html
    $('#test-ul li[name=python]').css('{"color","red"}');
```

元素的显示和隐藏（本质其实就是修改`display：none`）

```html
    $('#test-ul li[name=python]').show();
    $('#test-ul li[name=python]').hide();
```



代码演示：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--导入jQuery，因为是导入的微软的，所以还存在CDN加速-->
    <script src="http://ajax.aspnetcdn.com/ajax/jQuery/jquery-2.1.1.min.js"></script>
</head>
<body>

<ul id="test-ul">
    <li class="js">js</li>
    <li name="python">python</li>
</ul>

<script>
    //节点文本操作
    $('#test-ul li[name=python]').text(); //获得值
    $('#test-ul li[name=python]').text('123'); //设置值
    $('#test-ul').html(); //获得值
    $('#test-ul').html('<strong>123</strong>'); //设置值

    //css操作
    $('#test-ul li[name=python]').css('{"color","red"}');

    //元素的显示和隐藏
    $('#test-ul li[name=python]').show();
    $('#test-ul li[name=python]').hide();

</script>

</body>
</html>
```

