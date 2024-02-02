
## 数据类型
数值型(Number)、字符串型、布尔型(Boolean)、未定义型(undefined)


## 输出语法
```javascript
document.write("页面文本输出")
alert("浏览器文本输出")
console.log("控制台文本输出")
```

## 输入语法
```javascript
// 浏览器输入
prompt("请输入文本")
```

## 变量声明
```javascript
// let可用于变量声明,不可重复声明，声明变量为局部变量
let age = 18
// var 声明变量为全局变量，可重复声明
// 基本已经弃用
var age = 18
```

## 常量声明
```javascript
// const,初始化赋值，不可更改
const pi = 3.14
```

## 模板字符串
```javascript
// 用``进行字符串包裹，用${}进行变量包裹
let age = 18
document.write(`今年${age}岁`)
```

## 类型检测
```javascript
// 用运算符号进行检测
typeof age
// 以函数形式进行检测
typeof(age)
```

## 类型转换
**隐式转换**
![Alt text](./md/隐式转换.png)
**显式转换**
```javascript
let age = "18"
// 数值转换
Number(age)
// 转换为整数，在文本中提取整数，必须是数据开头
ParseInt(age)
// 转换为浮点数，在文本中提取数据，必须是数据开头
ParseFloat(age)

```
## 运算符
```javascript
// 二元运算符
// == 比较值是否相等
// ===比较是否全等，值和类型是否相等
// 逻辑运算符
// && 与            ||或            ！非
```
## 表达式与语句
### 分支语句
```javascript
if(判断条件){
    执行语句
}
else{
    执行语句2
}

// 例子
if(num>2){
    console.log("语句执行")
}
else{
    console.log("语句2执行")
}


// switch分支语句，与break搭配使用，不然会出现数据穿透
switch (数据){
    case 数据1：
        执行代码1
        break
    case 数据2：
        执行代码2
        break
    default：
        执行语句
}

// 例子
switch (1){
    case 1:
        alert("执行语句1")
        break
    case 2:
        alert("执行语句2")
        break
    default:
        alert("执行语句")
}
```
### 三元运算符
常用于赋值
```javascript
条件 ？执行语句1 : 执行语句2

// 例子
num>3 ? alert("执行语句1") ： alert("执行语句2")
```

## 循环语句
```javascript
// while 循环
while (循环条件) {
    循环语句
}
// 例子
let num = 1
while(num<=3) {
    alert(`循环${num}次`)
    num++

// for循环
for(起始条件，终止条件，变化量){
    循环语句
}
// 例子
for(let i=1;i<=10;i++){
    alert(`循环${i}次`)
}

// 数组遍历
let arr = ["a","b","c"]
for(let i = 1;i<=arr.length-1;i++){
    console.log(arr[i])
}
```
##数组操作
```javascript
let arr = ["a","b","c"];
// 新增元素
push():在末尾增加元素,可以追加多个，且有返回值，返回值为增加后的数组长度
unshift():在开头插入元素，语法与`push()`一致
// 例子
arr.push("d")
arr.push("d","e")
result = arr.push("d")

// 删除元素
pop():删除末尾最后一个元素，返回值为删除值
shift():删除开头第一个元素
splice():删除指定元素
arr.splice(起始元素索引,元素个数)
// 例子
arr.pop()

arr.splice(2,2)
// 修改元素
arr[2] = 10

```

##函数
```javascript
function 函数名(){
    函数体
}
// 例子
function add(){
    alert("这是一个函数")
}
```


## 作用域
### 全局作用域
在script中声明的变量
### 局部作用域
在函数中声明的局部变量
**for循环中的i,j...为局部变量，不能直接访问**
```javascript
for(i=1;i<10;i++){
    console.log("局部作用域测试")
}
// 循环结束后，i无法在script中直接访问出10
```


## 匿名函数
用函数表达式的方式构建，区别与具名函数，`不存在函数名`
```javascript
let fn = function(参数){
    函数体
} 

// 例子
let fn = function(){
    console.log("匿名函数测试")
}
```
## 立即执行函数
当同事使用两个立即执行函数时，需要用";"进行分隔
```javascript
// 非同时两个立即执行函数无需使用';'进行分隔
(function(){alert("测试立即执行函数")})()
alert("分隔测试")
// 两个立即执行函数需要使用";"进行分隔
(function(){alert("测试立即执行函数")})()；
(function(){alert("测试立即执行函数")})()
```

## 对象
```javascript
// 对象构造
let 对象 = {
    属性名:属性值，
    方法名:函数
}

// 增删改查
// 增加
对象名.新属性 = 属性值
// 修改
对象名.属性 = 新属性值
// 删除
delete 对象名.属性
// 查找
对象名.属性
对象名["属性"]

// 对象遍历
let obj = {
    name:"jeck",
    age:18,
    gender:"man"
}
for(key in obj){
    console.log(obj[key])
}
// 遍历出来的值是带引号的字符串，因此不能用**.属性**进行获取值
```

## 内置对象
 [数学函数](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math)
```javascript
// 四舍五入
Math.round()
// π
Math.PI
```

## 随机数
生成m，n之间的随机整数
```javascript
Math.floor(Math.random()*(m-n+1))+n
```

## web Api
![Alt text](./md/web_api.png)

## dom
### dom 树
![Alt text](./md/dom树.png)
### dom对象
![Alt text](./md/dom对象.png)

### dom对象获取
css选择器获取对象
```javascript
// 选择匹配第一个元素，返回值为对象
document.querySelector("css选择器")
// 例子
// 容器
document.querySelector("div")
// class
document.querySelector(".main")
// id
document.querySelector("#id")
// 嵌套
document.querySelector("ul li:first-child")

// 选择匹配全部元素，返回值为对象数组
document.querySelectorAll("css选择器")

```
其他获取方式
![Alt text](./md/dom元素获取.png)

## 操作元素内容
### 对象.innerText
只识别文本内容，不解析标签

### 对象.innerHTML
不仅可以识别文本内容，还会解析标签

## 操作元素属性
### 常用属性操作
![Alt text](./md/操作元素常用属性.png)

### 样式属性操作
#### 操作样式修改css
对于如background-color 带分隔符的属性用小驼峰命名法获取属性
```javascript
const bgColor = document.querySelector("div")
bgColor.backgroundColor = "pink"
```
#### 操作类名修改css
![Alt text](./md/操作类名.png)
```javascript
<div class="wrapper">
        <strong>年会抽奖</strong>
        <h1>一等奖<span id="one"></span></h1>
        <h2>二等奖<span id="two"></span></h2>
        <h3>三等奖<span id="three"></span></h3>
</div>
<style>
        .wrapper {
            height: 500px;
            width: 600px;
        }
        .newClass{
            height: 300px;
            width: 500px;
            background: #000;
        }
</style>
<script>
        const div = document.querySelector("div.wrapper")
        {/* 修改新类名 */}
        div.className = "newClass"
        {/* 保留旧类名 */}
        div.className = 'wrapper newClass'
</script>
```
#### 通过classList操作css
![Alt text](./md/classlist操作css.png)

### 操作表单属性
#### 表单内容获取
```javascript
// 表单内容获取
const form = document.querySelector("input")
const value = form.value

// 按钮禁用
const buttom = document.querySelector("buttom")
const buttom.disabled = true

// 复选框选中
const check = document.querySelector(".checked")
const check.checked = true
```
### 自定义属性
自定义属性一律用`data-`开头
自定义属性的一律以`dataset`对象方式获取
```javascript
    <div class="box" data-id="10">盒子</div>
    <script>
        const box = document.querySelector('.box')
        console.log(box.dataset.id)
    </script>
```
![Alt text](./md/自定义属性.png)

## 定时器
### 开启定时器
```javascript
let n = setInterval(函数名,间隔时间)
// 间隔时间单位是毫秒
// 函数不加小括号
// 有一个返回值
```
### 关闭定时器
```javascript
clearInterval(n)
```

## 事件监听
```javascript
对象元素.addEventListener("事件类型",执行函数)
// 事件源
// 事件类型：触发方式，比如鼠标单击click
// 函数调用

// 鼠标事件
click:鼠标点击
// 两种鼠标经过/离开事件没有冒泡效果
mouseenter:鼠标经过
mouseleave:鼠标离开
// 两种鼠标经过/离开事件有冒泡效果
mouseover:鼠标经过
mouseout:鼠标离开

// 表单事件
focus:获得焦点
blur:失去焦点

// 键盘事件
keydown:键盘按下触发
keyup:键盘抬起触发

// 输入事件
input:用户输入事件
```

## 事件对象
对象里有事件触发时的相关信息
在事件绑定的回调函数里第一个参数，命名为`event`、`ev`、`e`
```javascript
元素.addEventListener("事件类型",function(e){
    执行语句
})
```
### 获取事件属性
```javascript
type:获取当前事件类型
clientX/clientY:获取光标相当于浏览器可见窗口左上角的位置
offerX/offerY:获取光标相当于当前dom元素左上角的位置
key:用户按下的键盘键的值
```
去除字符串左右两侧空格函数`trim()`

## 环境对象
指代函数内部的变量`this`，表示函数运行时所处的环境
**调用规则**：谁调用函数，this指向谁

>this与event区别

1、event是鼠标事件对象，代表事件的状态，比如事件在其中发生的元素、键盘按键的状态、鼠标的位置、鼠标按钮的状态。
2、this指向的是调用事件的元素对象。
`event.target`与`this`指向对象一致

## 回调函数
将函数A作为参数传递给函数B，称为函数A为回调函数

## 事件流
事件执行的完整执行过程中的流动路径
包括两个阶段**事件捕获**和**事件冒泡**
**事件捕获**：先调用父元素，再调用子元素
**事件冒泡**：当一个元素触发事件之后，会依次向上调用所有父级元素的同名事件(从子到父)`事件触发默认为事件冒泡`
```javascript
   <div class="father" style="width: 500px; height: 250px; background-color: pink;">
        <div class="son" style="width: 100px; height: 100px; background-color: blue;"></div>
    </div>
    <script>
        document.addEventListener("click", function(){
            alert("grandfather")
        })
        document.querySelector(".father").addEventListener("click", function(){
            alert("father")
        })
        document.querySelector(".son").addEventListener("click", function(){
            alert("son")
        })
    </script>
```

## 阻止冒泡
把时间限制在当前元素内
```javascript
事件对象.stopPropagation()
```
**实例**
```javascript
<div class="father" style="width: 500px; height: 250px; background-color: pink;">
        <div class="son" style="width: 100px; height: 100px; background-color: blue;"></div>
    </div>
    <script>
        document.addEventListener("click", function(){
            alert("grandfather")
        })
        document.querySelector(".father").addEventListener("click", function(){
            alert("father")
        })
        document.querySelector(".son").addEventListener("click", function(e){
            alert("son")
            e.stopPropagation()
        })
    </script>
```

## 事件解绑
`匿名函数无法接触事件绑定`
```javascript
对象元素.removeEventListener("事件类型",执行函数)
```

## 事件委托
利用`事件冒泡`实现，给`父元素注册事件`,触发子元素时，可以冒泡到父元素身上，从而触发父元素事件
优点：减少注册次数，提高性能
**实现**
```javascript
// 获取指定子元素
事件对象.target
// 获取子元素名称
事件对象.target.tagName

// 例子
// 获取的子元素要全部大写————"LI"
<div>
        <li class = "pointer">第1个标签</li>
        <li class = "pointer">第2个标签</li>
        <li class = "pointer">第3个标签</li>
        <li class = "pointer">第4个标签</li>
        <li class = "pointer">第5个标签</li>
        <p>特殊元素</p>
    </div>

    <script>
        const father = document.querySelector("div")
        father.addEventListener("click",function(e) {
            if(e.target.tagName === "LI"){
                e.target.style.color = "red"
            }
            
        })

    </script>
```
## 阻止默认行为
表单提交时，不满足条件时，不发生页面跳转
```javascript
e.preventDefault()
```

## 其他事件
### 页面加载事件
外部资源加载完毕时触发的事件，当`scrpit`位于`head`标签内部，dom未加载完毕，执行`script`代码无法找到dom元素
事件名：`load`
监听页面所有资源加载完毕：给`window`添加`load`事件
```javascript
// 等待窗口资源全部加载完毕
window.addEventListener("load",function(){
    执行函数
})
```
当初始的HTML文档被完全加载和解析完成之后，DOMContentLoaded事件被触发，而无需等待样式表、图像等完全加载
事件名：`DOMContentLoaded`
```javascript
// 等待窗口资源全部加载完毕
document.addEventListener("DOMContentLoaded",function(){
    执行函数
})
```

### 页面滚动事件
>页面平滑跳动方式
```css
<style>
    html{
        scrollbehavior:smooth;
    }
</style>
```

滚动条在滚动的时候持续触发的事件，通常给`window`添加滚动事件
监听某个元素滚动事件，给元素直接增加滚动事件即可
事件名：`scroll`
```javascript
    // 监听整个窗口滚动
    <script>
        window.addEventListener("scroll", function(e) {
            console.log("scroll")
        })
    </script>
```
#### 页面滚动事件——获取位置
`scrollLeft`和`scrollTop`属性：被卷去的大小，**值可读写,数值型不带单位**
**获取HTML**：`document.documentElement`
`scrollto(x,y)`:将页面滚动到指定坐标


### 页面尺寸事件
窗口尺寸改变的时候触发的事件`resize`
```javascript
window.addEventListener("resize",function(){
    执行函数
})
```
#### 获取元素宽和高
获取元素可见宽`clientWidth`和高`clientHeight`,**不包含边框和尺寸**
```javascript
<div></div>
    <script>
        const div = document.querySelector("div")
        console.log(div.clientHeight)
    </script>
```
**获取元素宽高**
获取包含`边框`的宽和高：`offsetWidth`、`offsetHeight`
**获取定位：**
距离左右的位置：`offsetLeft`、`offsetTop`
**子元素获取时要看父元素的定位，如果是相对定位，获取的框高是距离父元素的宽高，绝对定位获取的才是距离顶部的宽高**


## 日期对象
用来表示时间的对象
### 实例化
```javascript
// 获取当前时间
const data = new Date()

// 获取指定时间
const data1 = new Date("2022-5-1")
```

### 日期对象方法
```javascript
const date = new Date()
// 获取年份
date.getFullYear()
// 获取月份(0-11)
date.getMonth()
// 获取每天
date.getDate()
// 获取星期(0-6)
date.getDay()
// 获得小时
date.getHours()
// 获得分钟
date.getMinutes()
// 获得秒
date.getSecond()
// 获取当前时间(年-月-日 时-分-秒)
date.toLocaleString()
// 获取当前时间(年-月-日)
date.toLocaleDateString()
// 获取当前时间(时-分-秒)
date.toLocaleTimeString()
```

### 时间戳
```javascript
// 时间戳获取
const date = Date()
date.getTime()

// 方法二
+new Date()

// 方法三
// 仅可以返回当前时间戳
Date.now()
```

## 节点操作
### dom节点
dom树中的每一个内容都称为节点
**节点类型**：元素节点、属性节点、文本节点、其他

### 查找节点
根据节点关系查找目标节点
#### 父节点查找
```javascript
// parentNone属性
// 返回最近一级的父节点，找不到返回null
子元素.parentNode
```

#### 子节点查找
获取所有子节点，包括文本节点、注释节点
```javascript
// children属性
// 获得所有元素节点
// 返回伪数组
父元素.children
```

#### 兄弟关系查找
`nextElementSibling`:下一个兄弟节点
`previousElementSibling`:上一个兄弟节点


#### 实例
```javascript
    <div class="grandfather">
        <ul>
            <li>1</li>
            <li>2</li>
            <li>3</li>
            <li>4</li>
            <li>5</li>
        </ul>
        <ul>
            <li>1</li>
            <li>2</li>
            <li>3</li>
            <li>4</li>
            <li>5</li>
        </ul>
    </div>
    <script>
        // dom节点获取
        const div = document.querySelector(".grandfather")
        console.log(div)

        // 父节点获取
        const body = div.parentNode
        console.log(body)

        // 子节点获取(获取ul标签)
        const ul = div.children
        // console.log(ul[1].nodeName)
        console.log(ul[0])

        // 兄弟节点获取
        // 获取第一个ul标签下的第二个li标签
        const li1 = ul[0].children[1]
        console.log(li1)
        // 获取上一个兄弟标签
        const li0 = li1.previousElementSibling
        // 获取下一个兄弟标签
        const li2 = li1.nextElementSibling
        console.log(li0)
        console.log(li2)
        
    </script>
```
### 增加节点
1、创建一个新的节点:`document.createElement`
2、将新创建的节点放到指定元素的内部
**尾部追加：**`元素名.appendChild(新元素)`
**指定位置添加：**`元素名.insertBefore(新元素,添加位置)`
`添加位置的获取要通过获取元素名的子元素 最前面：ui.children[0]`
```javascript
const div = document.createElement("div")
// 新增节点
// 在第一个ul标签下新增一个li标签
const new_li = document.createElement("li")
new_li.innerHTML = "我是新增加的li标签"
div.children[0].appendChild(new_li)
// 指定位置插入标签
const new_li_insert = document.createElement("li")
new_li_insert.innerHTML = '我是插入的li标签'
div.children[0].insertBefore(new_li_insert,div.children[0].children[0])
```

### 克隆节点
`元素名.cloneNode(布尔值)`
true：深度克隆，子孙节点都克隆
false：只克隆子节点
>在轮播图中克隆后追加到后面
```javascript
const div = document.querySelector(".grandfather")
div.cloneNode(true)
```

### 删除节点
`父元素.removeChild(要删除的元素)`
只有父元素存在，才可进行删除

## M端事件
移动端事件——`touch`
```javascript
// 手指触摸dom元素触发
touchstart
// 手指在dom元素上滑动触发
touchmove
// 手指在dom元素上移开触发
touchend
```

## 插件使用
[swiper插件](https://www.swiper.com.cn/)

## BOM
浏览器对象模型

### 延时函数
`setTimeout(执行函数,时间)`
只执行一次
```javascript
// 设置延时函数
let timeId = setTimeout(function(){
    alert("延时函数")
},1000)
// 清除延时函数
clearTimeout(timeId)
```

### location对象
对`location.href`进行赋值，可以实现页面跳转
```javascript
location.href = "http://www.baidu.com"
```
`location.search`可以获得网址"?"后的内容
`location.hash`可以获得网址"#"后的内容
`location.reload()`页面刷新
`location.reload(true)`强制页面刷新

### history对象
`history.back()`:页面后退
`history.forward()`:页面前进
`history.go(-1)`:后退
`history.go(1)`:前进


## 本地存储
### localStorage
以对象的方式进行操作，**localStorage的存储数据均会转为字符串存储**
存储数据：`localStorage.setItem(key,value)`
获取数据：`localStorage.getItem(key)`
删除数据：`locakStorage.removeItem(key)`
修改数据：同存储数据

### 存储复杂数据
将复杂数据类型转换为JSON字符串存储到本地
`JSON.stringify(复杂数据类型)`
```javascript
const  obj = {
    name:"pink",
    age:18,
    gender:"man"
}
localStorage.setItem(JSON.stringify(obj))
```

### 取用复杂数据
将本地存储的JSON字符串转换为对象
`JSON.parse(取用对象)`
```javascript
const obj = localStorage.getItem("obj")
const objUse = JSON.parse(obj)
```
>在分支语句和循环语句中声明的变量，只能在分支语句中调用，无法在分支外调用
```javascript
const out = 1
if(true){
    const out = 2
}
console.log(out)
// 输出结果是1
```

### map 与 join
`map()`:有返回值，可以遍历列表，并返回索引
**主要用于数组与数组之间的映射**，可以拼接对应的数组元素
```javascript
const arr = ["red", "green", "yellow"]
const new_arr = arr.map(function(ele,index) {
    console.log(ele)
    console.log(index)
    return ele + "颜色"
})
console.log(new_arr)
```
`join()`：将数组元素拼接在一起，**可以传递分割参数,默认是逗号分隔**
```javascript
const arr = ["red", "green", "yellow"]
const new_arr = arr.join(" ")
console.log(new_arr)
```