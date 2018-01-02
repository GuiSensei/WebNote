Javascript基础
===

- 变量`var a = 10;`注意分号
- 输出`alert()`转义换行
- 输出`document.write()`换行`'<br/>'`

### 算术运算符
`+`、`-`、`*`、`/`、`%`、`++`、`--`
- 数字+数字=数字
- 数字+字符串=字符串
- 字符串+字符串=字符串

### 赋值运算符
`=`、`+=`、`-=`、`*=`、`/=`
### 比较运算符
`>`、`<`、`>=`、`<=`、`==`、`!=`
### 逻辑运算符
`&&`、`||`、`!`
### 条件运算符
`var a = 条件? 表达式1:表达式2`
### 强制类型转换
- 数字
    - `Number()`
    - `parseInt()`和`parseFloat()`字符串中提取数字
- 字符串
    - 与空字符串相加
    - `toString()`
### 转义
### 注释
- `//单行注释`
- `/*多行注释*/`

### 条件语句
```Javascript
if (条件)
{
    ...
}
```

```Javascript
if (条件)
{
    ...
}
else
{
    ...
}
```
```Javascript
if (条件)
{
    ...
}
else if(条件2)
{
    ...
}
else:
{
    ...
}
```
### 选择结构
```Javascript
swich (判断值)
{
    case 取值1:
        语句1;break;
    case 取值2:
        语句2;break;
    ...
    default:
        默认语句;        
}
```
### while循环
```Javascript
while(条件)
{
    条件为真时执行
}
```
```Javascript
do(条件)
{
    先执行一次再判断条件
}
while(条件)
```
### for循环
```Javascript
for(初始化表达式;条件表达式;循环后操作)
{
    循环体
}
```
### 函数
###### 函数的定义
```Javascript
function 函数名 (参数1,参数2,...)
{
    ...
    return 返回值;
}
```
###### 全局变量和局部变量
###### 函数的调用
- 直接调用
    `函数名(参数)`
- 在表达式中调用
- 在超链接中调用
    `<a href='javascript:函数名'></a>`
- 在事件中调用(后面介绍)
###### 函数的嵌套
###### 内置函数
- `parseInt()`
- `parseFloat()`
- `isFinite()`：是否有限小数
- `isNaN()`：是否NaN
- `escape()`：对字符串进行编码
- `unescape()`：对字符串进行解码
- `eval()`：把字符串当作表达式执行
### 字符串对象
- `str.length`：字符串长度
- `str.toLowerCase()`：换成小写
- `str.toUpperCase()`：换成大写
- `str.charAt(index)`：获取第index个元素
- `str.substring(start,end)`：切片，同python
- `str.replace(原字符串/正则表达式，替换字符串)`
- `str.split('分隔符',N)`：分割字符串，得到N个为止
- `str.indexOf(指定字符串)`：首次出现的index
- `str.lastIndexOf(指定字符串)`：最后出现的index
### 数组
###### 创建数组
`var 数组名 = new Array(元素1,元素2,...);`或`var 数组名 = new [元素1,元素2,...];`
- 空数组：`var arr = [];`
- 索引：`arr[index];`
- 赋值：`arr[index] = value;`
- 长度：`arr.length;`
- 切片：`arr.slice(start,end);`
- 开头添加：`arr.unshift(element1,element2,...);`
- 末尾添加：`arr.push(element1,element2,...);`
- 删除第一个元素：`arr.shift();`
- 删除最后一个元素：`arr.pop();`
- 数组比较：`arr.sort(函数名)`
- 反向：`arr.reverse();`
- 数组连成字符串：`arr.join('连接符')`
> 数组和字符串相互转换`split()`和`join()`

### 时间对象
`var adate = new Date();`
- `adate.getFullYear()`
- `adate.getMonth()`
- `adate.getDate()`
- `adate.getHours()`
- `adate.getMinutes()`
- `adate.getSeconds()`
- ...

### 数学对象
###### `Math.属性`
- `Math.PI`:pi
- `Math.LN2`:ln(2)
- `Math.LN10`:ln(10)
- `Math.LOG2E`:
- `Math.LOG10E`
- `Math.SORT2`
- `Math.SORT1_2`
###### `Math.方法`
- `Math.max(a,b,...)`
- ...
- `Math.floor()`向下取整、`Math.ceil()`向上取整
- `Math.rondom()*m`：生成0~m之间的随机数
- `Math.rondom()*m+n`：生成n~m+n之间的随机数
- `Math.rondom()*m-n`：生成-n~m-n之间的随机数
- `Math.rondom()*m-m`：生成-m~m之间的随机数

### DOM（Document Object Model）
###### DOM对象
###### DOM结构：树形结构
###### 节点类型（共12种，常见3种）
- 元素节点
- 属性节点
- 文本节点
> 1. 如`<div id="wrapper">文本</div>`整个是元素节点，其中`id="wrapper"`是属性节点，`文本`是文本节点。
> 2. 节点跟元素是不一样的概念，节点是包括元素的。
> 3. 不同节点可用nodeType属性来判断，会得到不同的值，其中元素节点的值为1，属性为2，文本为3
###### 获取元素
- `document.getElementById("id名")`：通过id选中元素，前面只能是document
    - 如`var oDiv = document.getElementById("div1")`
- `document.getElementsByTagName("标签名")`获取多个标签
    ```Javascript
    var oUl = document.getElementById("list")//先获取id为list的ul元素
    var oLi = oUl.getElementsByTagName('li')//获取ul下的li标签，如果只有这一句，会获取整个HTML页面的li标签
    ```
- `document.getElementsByClassName("类名")`，获取多个类数组，方法同上，不能操作动态DOM
- `document.querySelector("选择器")`和`document.querySelectorAll("选择器")`
    ```Javascript
    document.querySelector("#main");
    document.querySelector("#list li:nth-child(3)");//表示选取id为list下的第三个元素
    document.querySelectorAll("#list li");
    document.querySelectorAll("input:checkbox");
    ```
    > 对于id选择器，建议使用`getElementById()`，因为整个页面只有一个元素
- `document.getElementsByName()`
    - 用于表单的单选或复选按钮
    ```Javascript
    var oInput = document.getElementsByName("status");
    oInput[i].checked = true;//表示第i个点击之后值设为true
    ```
- `document.title`和`document.body`
> - 变量名一般以`o`开头（习惯用法,表示DOM对象）
> - `getElementById()`与`getElementsByTagName()`的区别
>   - `getElementById()`获取的是一个元素，`getElementsByTagName()`获取多个元素
>   - `getElementById()`前面只能是document，`getElementsByTagName()`可以是任何DOM对象
>   - `getElementById()`不可以操作动态创建的DOM元素，`getElementsByTagName()`可以操作动态创建的DOM元素

###### 创建元素




```Javascript
window.onload = function()//window.onload表示整个页面加载完后执行的代码块，否则内部div1标签无法识别
{
    var oDiv = document.getElementById("div1")
}
```
