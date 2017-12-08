Web前端开发
===
###### 前端开发（静态网页）
- 核心技术
    - HTML：Hyper Txet Markup Language，网页的结构
    - CSS：Cascading Style Sheet，控制网页外观
    - Javascript：脚本语言，由浏览器一边解释一边执行
- 其他技术
    - jQuery
    - Vue.js
    - SEO
    - 性能优化

###### 后端开发（动态网页）
是否与服务器进行数据交互。带有视频或音频、flash动画、css动画、js特效都不叫动态网页。
- 后端技术
    - PHP
    - JSP
    - ASP.Net

###### 学习路线
HTML → CSS → Javascript → jQuery → CSS3 → HTML5 → Vue.js

## HTML
标记性语言
```HTML
<标签符>内容</标签符>
```

## 基本标签
- 注释`<!--注释文字-->`
- `<!DOCTYPE html>`文档声明，表示这是一个html页面
- `<html></html>`html标签对，这个页面从`<html>`开始
- `<head></head>`head标签对，这是网页的头部，定义一些特殊的内容：
    1. title标签`<title>网页的标题</title>`
    2. meta标签`<meta 网页是用来干嘛的 />`
        - name属性
            - `<meta name="keywords" contend="关键字,可以多个"/>`
            - `<meta name="description" contend="网页描述"/>`
            - `<meta name="author" contend="作者"/>`
            - `<meta name="copyright" contend="版权信息"/>`
        - http-equiv属性：定义网页所使用的编码和网页自动刷新跳转
            - `<meta http-equiv="Contend-Type" contend="text/html; charset=utf-8"/>`告诉浏览器该网页使用编码为utf-8，html5中可简写为`<meta charset=utf-8"/>`,网页乱码时可能时缺少该代码。
            - `<meta http-equiv="refresh" contend="6;url=http://www.baidu.com"/>`6秒后自动跳转到百度首页。
    3. link标签
        引入外部样式CSS文件
        `<link type="text/css" rel="stylesheet" href="css/link.css">`
    4. style标签
        用于定义元素的CSS样式。
        ```HTML
        <style type = "text/css">
            /*CSS样式*/
        </style>
        ```
    5. script标签
        用于定义Javascript代码
        ```HTML
        <script>
            /*Javascript代码*/
        </script>
        ```
    6. base标签
        无意义标签

- body标签对`<body></body>`，网页的大部分内容在此


## 文本
#### 标题
- `<h1>一级标题</h1>` 只能有一个，其他可多个
- `<h2>二级标题</h2>`
- `<h3>三级标题</h3>`
- `<h4>四级标题</h4>`
- `<h5>五级标题</h5>`
- `<h6>六级标题</h6>`
#### 段落
- `<p>文字</p>`会自动换行，并且会有一定的间距
- `<br/>`break的缩写，自闭合标签，没有间距
#### 文本
- 粗体`<srong>粗体</strong>`(尽量使用)、`<b>粗体</b>`
- 斜体`<i>斜体</i>`、`<em>斜体</em>`(emphasize尽量使用)、`<cite>斜体</cite>`
- 上标`<sup>上标</sup>`superscripted
- 下标`<sub>下标</sub>`subscripted
- 中划线`<s>中划线</s>`
- 下划线`<u>下划线</u>`
- 大字号`<big>大字号</big>`
- 小字号`<small>小字号</small>`
#### 水平线
`<hr/>`

#### div标签（division）
用于划分结构，使得网页更具有逻辑性，可以放入所有其他标签。

#### 自闭合标签
其他需要一对来关闭，自闭合标签只需要一个。
- `<br/>`
- `<hr/>`
- `<meta />`


#### 块元素block
- 包括：标题、段落、div、水平线标签、有序列表、无序列表
- 作用：再浏览器显示状态下将占据一整行，并且排斥其他元素；可以容纳其他块元素和行内元素。

#### 行内元素
- 包括粗体、斜体、超链接、span等

#### 特殊符号


## 列表
#### 有序列表ordered list
```html
<ol type="属性值">
    <li>列表项</li>
    <li>列表项</li>
</ol>
```
- `type="属性值"`可省略，默认为数字，其取值有：1、a、A、i、I
- 可用CSS的list-style-type替代type属性

#### 无序列表unordered list（更加实用）
```html
<ul>
    <li>列表项</li>
    <li>列表项</li>
</ul>
```
- `type="属性值"`可省略，默认为disc，其取值有：disc(实心圆)、circle（空心圆）、square(正方形)
- 可用CSS的`list-style-type`替代`type`属性
- `ul`中的元素只能时`li`不能是其他元素
- 文本不能直接放在`ul`内，只能在`li`内部添加

#### 定义列表（较少使用）
```html
<dl>
    <dt>名词</dt>
    <dd>描述<dd>
        ...
</dl>
```

## 表格
```html
<table>
    <caption>表格标题</caption>
    <!--表头-->
    <thead>
        <tr>
            <th>表头</th>
            <th>表头</th>
        </tr>
    </thead>
    <!--表身-->
    <tbody>
        <tr>
            <td>单元格</td>
            <td>单元格</td>
        </tr>
        <tr>
            <td>单元格</td>
            <td>单元格</td>
        </tr>
    </tbody>
    <!--表脚-->
    <tfoot>
        <tr>
            <td>单元格</td>
            <td>单元格</td>
        </tr>
    </tfoot>
</table>
```
- 表格默认无边框，需要CSS辅助才会有边框。
- 标题只能有一个，默认位于整个表格的第一行居中显示。
- 表头会粗体居中显示。
- 表脚一般用于统计数据，很少用
- 加上`thead`、`tbody`、`tfoot`标签是为了更有逻辑性

#### 合并行：rowspan
```html
<table>
    <tr>
        <td>单元格</td>
        <td>单元格</td>
    </tr>
    <tr>
        <td rowspan= "2">单元格</td>
        <td>单元格</td>
    </tr>
    <tr>        
        <td>单元格</td>
    </tr>
</table>
```
- 让rowspan行td标签跨两行

#### 合并列：colspan
```html
<table>
    <tr>
        <td>单元格</td>
        <td>单元格</td>
    </tr>
    <tr>
        <td colspan= "2">单元格</td>        
    </tr>
    <tr>
        <td>单元格</td>       
        <td>单元格</td>
    </tr>
</table>
```
- 让colspan行td标签跨两列

## 图片
`<img src="" alt="" title="" />`
- src：文件路径（最好相对路径）（必须）。网页中，可用`../`表示上一级目录，用于子网页。
- alt：描述图片文字，给搜索引擎看的，当图片无法显示时，显示该文字（必须）。
- title：描述图片文字，给用户看的，鼠标悬浮会显示（可选）。


## 超链接
`<a href="链接地址" target="打开方式">文本或图片</a>`
- `target`四种属性：
    - `_self`：默认值，在原来窗口打开超链接
    - `_blank`：在新窗口打开超链接
    - `-parent`：在父窗口打开超链接
    - `_top`：在顶层窗口打开超链接
- 内部链接
    直接写`file.html`或`fold/file.html`
- 锚点链接
    - 设置`id`
    - `a`标签中的`href`属性指向该`id`
    ```html
    <div id = "aa">
        ...
    <a href="#aa" target="打开方式">文本或图片</a>
    ```


## 表单
- `form`标签
    - 格式
        ```html
        <form>
            //表单标签
        </form>
        ```
    - 标签属性
        - `name`：表单名称，仅为区分`<form name="myform"></form>`
        - `method`：提交方式
            - `<form method="get"></form>`安全性差，一般不用
            - `<form method="post"></form>`安全性好，一般用post
        - `action`：表单数据提交地址`<form action="index.php"></form>`
        - `target`：打开方式，与`a`标签相同
        - `enctype`：编码方式，一般不用设置，除非用到上传文件功能。
- `input`标签
大多数表单都是用`input`标签，格式：`<input type="表单类型">`，其中表单类型有：
    - `text`：单行文本框，其属性有：
        - `value`：文本框默认值
        - `size`：文本框长度
        - `maxlength`：文本框最多可输入字符数
    - `password`：密码文本框，属性同`text`
    - `radio`：单选框`<input type="radio" name="" value="" checked />`
        - `name`同一组只能设置相同的名字，否则可多选
        - `value`的作用是方便服务器操作，页面显示加不加都一样
        - `checked`默认项需添加
    - `checkbox`：复选框，属性与单选框完全相同
    - `button`、`submit`、`reset`：按钮，
        - `button`普通按钮，配合Javascript操作`<input type="button" value="" />`，`value`是按键上的值
        - `submit`提交按钮，给服务器提交数据，作用范围只是当前form标签中。
        - `reset`重置按钮，清除用户在表单中输入的内容，作用范围只是当前form标签中。
        - 还有一种按钮是用`<botton></botton>`标签设置的，但实际开发中基本不会使用。
    - `file`：文件上传`<input type="file"/>`

- 多行文本框
`<textarea rows="行数" cols="列数" value="取值">默认内容</textarea>`

- 下拉列表
    ```html
    <select multiple size="取值">
        <option>下拉列表1</option>
        <option selected value="取值">下拉列表2</option>
        <option>下拉列表3</option>
    </select>
    ```
    - `multiple`表示可以多选
    - `size="取值"`表示显示的项数
    - `selected`是否选中
    - `value="取值"`选项值，javascript中使用
```html
<!DOCTYPE HTML>
<html>
<head>
<title>实验</title>
</head>
<body>
<form method = "post">
	<input type="reset" value="全部重置"/><br/>
    用户名：<input type="text" value="用户名" size=10 maxlength=10 /><br/>
	密码：<input type="password" value="password" size=10 maxlength=10/>	<br/>
	性别：<input type="radio" name ="gender" value="男" checked />男
			<input type="radio" name ="gender" value="女"/>女<br/>
	年龄：<input type="radio" name ="age" value="80" checked />80后
			<input type="radio" name ="age" value="90"/>90后
			<input type="radio" name ="age" value="00"/>00后
			<input type="radio" name ="age" value="10"/>10后<br/>
	年收入：<select multiple size="1">
				<option>1w</option>
				<option selected>2w</option>
				<option>3w</option>
			</select><br/>
	你喜欢的水果：<input type="checkbox" name ="fruit" value="apple" checked />苹果
			<input type="checkbox" name ="fruit" value="banana"/>香蕉
			<input type="checkbox" name ="fruit" value="watermelon"/>西瓜
			<input type="checkbox" name ="fruit" value="pear"/>梨子<br/>
	上传照片：<input type="file"/><br/>
	个人简介：<br/><textarea rows="10" cols="20" value="0">默认内容</textarea><br/>
</form>
</body>
</html>
```

## 框架
使用`iframe`实现一个内嵌框架，也就是在当前网页再嵌入另外一个网页
```html
<!DOCTYPE HTML>
<html>

<head>
<title>实验</title>
</head>
<body>
	<iframe src="http://www.baidu.com" width="1200" height="1200"></iframe>
</body>
</html>
```
