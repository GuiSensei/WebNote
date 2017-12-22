CSS
===
### 简介
cascading style Sheet 层叠样式表，用于控制网页外观。
- 外部样式表：最理想的方式，将CSS与HTML放在不同的文件中；使用`<link>`标签进行引用（`<link>`标签在`<head>`中）。如：
    ```html
    <link rel="stylesheet" type="text/css"href="文件路径"/>
    ```
    - `rel`：reletive,取值是固定的即`sytlesheet`，表示引用的是CSS文件
    - `type`：也是固定的，表示这是标准的CSS
    - `href`：文件路径

- 内部样式表:把CSS代码与HTML代码放在同一个HTML文件中。CSS代码放在`style`标签内(`head`中)，如：
    ```html
    <style type="text/css">
    ......
    </style>
    ```
- 行内样式表：在标签的`style`属性中定义。如：
    ```HTML
    <div style="color:red">...... </div>
    ```
### CSS选择器
##### 元素的`id`和`class`
- `id`属性
id具有唯一性，在同一个页面中相同的`id`只能出现一次，如果出现多次，CSS和Javascript将无法识别。（不用页面中可以出现相同的id）
- `class`属性
同一类的元素可以使用相同的`class`属性
> `id`相当于身份证号，`class`相当于你的名字，id不同相同，名字可以重复

##### 选择器
 用一种方式将想要的元素选中即称之为选择器，这样就能为该元素添加CSS样式。
 - 选择器
    - 元素选择器
        ```CSS
        元素符号{属性:属性值;属性:属性值;...}
        div{width:100px;height:100px;}
        ```
    - id选择器
        ```CSS
        #id名称{属性:属性值;属性:属性值;...}
        #box{width:100px;height:100px;}
        ```
    - class选择器
        ```CSS
        .class名称{属性:属性值;属性:属性值;...}
        .box{width:100px;height:100px;}
        ```
    - 后代选择器
        ```CSS
        #父名 子名{属性:属性值;属性:属性值;...}
        #father div{width:100px;height:100px;}
        #father span{color:red}
        ```    
    - 群组选择器
        ```CSS
        选择器1,选择器2,...{color:red} <!--逗号分隔-->
        h3, div, p ,span{color:red}
        ```
### 字体样式
- `font-family:字体1,字体2,... `
    > 中文或多个英文单词需要加双引号
- `font-size:像素值`
    - `px`单位：
    - `em`单位
    - 百分比
- `font-weight:取值`，取值可以是数字，也可以是如下关键字：
    - `normal`正常（默认值）相当于100
    - `lighter`较细，相当于400
    - `bold`较粗，相当于700
    - `bolder`很粗，相当于900
- `font-style:取值`，取值如下：
    - `normal`：正常（默认）
    - `italic`：斜体
    - `oblique`：斜体（有些字体不能使用italic，可以使用这个）
- `color:颜色值`：关键字或者16进制RGB值
- 注释：`/*注释*/`

### 文本样式
- `text-indent:像素值`：首行缩进（两个字符一般是`font-size`的两倍）
- `text-align:取值`：水平对齐，仅对文本有效，取值如下：
    - `left`：左对齐
    - `center`：居中对齐
    - `right`：右对齐
- `text-decoration:取值`：文本修饰，取值如下：
    - `none`无划线效果（默认）
    - `underline`：下划线（强调文章的重点）
    - `line-throgh`：中划线（促销时）
    - `overline`：顶划线（基本不用）
- `text-transform:取值`：大小写，取值如下：
    - `none`：无转换（默认）
    - `uppercase`：转换为大写
    - `lowercase`：转换为小写
    - `capitalize`：将首字母大写
- `line-height:像素值`：行高
- `letter-spacing:像素值`：字母间距
- `word-spacing:像素值`：单词间距

### 边框样式
- `border-width:像素值`：边框宽度
- `border-style:取值`：边框的外观，取值如下：
    - `none`：无样式
    - `dashed`：虚线
    - `solid`：实线
- `border-color:颜色值`：边框的颜色，可以是关键字或者RGB
- 简写形式：`border:宽度值 样式值 颜色值`
- 局部样式：
    - 上边框：`border-top-width`、`border-top-style`、`border-top-color`
    - 下边框：`border-bottom-width`、`border-bottom-style`、`border-bottom-color`
    - 左边框：`border-left-width`、`-left-style`、`border-left-color`
    - 右边框：`border-right-width`、`border-right-style`、`border-right-color`
    > 可以简写

### 列表样式
- `list-style-type:取值`
    - 有序列表取值：
        - `decimal`：阿拉伯数字
        - `lower-roman`：小写罗马数字
        - `upper-roman`：大写罗马数字
        - `lower-alpha`：小写英文字母
        - `upper-alpha`：大写英文字母
    - 无序列表取值：
        - `disc`：实心圆
        - `circle`：空心圆
        - `square`：正方形
- 去除列表样式`list-style-type:none`
- 列表项图片：用图片代替列表项`list-style-image:url(图片路径)`（一般不用该方法）

### 表格样式
- `caption-side:取值`：表格标题位置，取值如下：
    - `top`：标题在顶部（默认）
    - `bottom`：标题在底部
- `border-collapse:取值`：表格边框合并，取值如下：
    - `seperate`：边框分开，有空隙
    - `collapse`：合并边框，无空隙
- `border-spacing:像素值`：表格边框间距

### 图片样式
- 图片大小：`width:像素值`、`height:像素值`
- 图片边框：`border:宽度值 样式值 颜色值`
- 图片对齐：
    - 水平对齐：`text-align:取值`：`left`、`center`、`right`
    - 垂直对齐：`vertical-align:取值`：`top`、`middle`、`baseline`、`bottom`
- 文字环绕：`float:取值`：`left`图片在左、`right`在右

### 背景样式
- `background-color:取值`：背景颜色（`color`是定义文本的颜色）
- `background-image:url(路径)`：背景图片，需要设置背景的高度和宽度
- `background-repeat:取值`：背景图片重复，取值如下：
    - `repeat`：在水平和垂直方向上平铺
    - `repeat-x`：在水平方向上平铺
    - `repeat-y`：在垂直方向上平铺
    - `no-repeat`：不平铺
- `background-position:水平像素 垂直像素/关键字`：背景图片位置，关键字如下：
    - `top left`
    - `top center`
    - `top right`
    - `left center`
    - `center center`
    - `right center`
    - `bottom left`
    - `bottom center`
    - `bottom right`
    > 使用关键字时需要同时设置背景的水平和垂直方向的值
- `background-attachment:取值`：背景图片固定，取值如下：
    - `scroll`：随着元素一起滚动（默认）
    - `fixed`：固定不动

### 超链接样式
- 超链接伪类
    - `a:link{...}`：定义a元素未访问时的样式
    - `a:visited{...}`：定义a元素访问后的样式
    - `a:hover{...}`：定义鼠标经过a元素时的样式（只需用这一个即可）
    - `a:active{...}`：定义鼠标点击激活时的样式
    > 实际使用时，只需要定义未访问时状态和鼠标经过时的状态即可。
        >   `a{} ` /*无需使用`a:link{}`*/
        >   `a:hover{}`

- 深入了解`hover`
`hover`可以定义任何一个元素，不仅仅时a标签，如：`div:hover{color:red}`、`img:hover{color:red}`
- `cursor:取值`：鼠标样式，取值如下：
    -  `default`：默认
    - `pointer`：手指
    - `text`：光标
    - `crosshair`：十字
    - `wait`：转圈
    - `help`：箭头加问号
    - `move`：箭头十字
    - `e-resize`、`w-resize`：左右箭头
    - `ne-resize`、`sw-resize`：↗↙箭头
    - `nw-resize`、`se-resize`：↖↘箭头
    - `n-resize`、`s-resize`：上下箭头
- 自定义鼠标样式`cursor:url(路径),属性值`，图片后缀一般为`.cur`，属性值一般为`default`、`pointer`、`text`三种类型。

### 盒子模型
- `content`：内容，可以是文本或者图片
    - `width`：盒子内容宽度
    - `height`：盒子内容高度
    - `overflow`：当超出高度和宽度时使用该属性处理溢出
- `padding`：内边距，用于定义内容与边框之间的距离（内部文本/图片到边框）
    - `padding:像素值`：四个方向都一样；`padding:像素值1 像素值2`：上下为1，左右为2；`padding:像素值1 像素值2 像素值3 像素值4`：上右下左；
    - `padding-top`
    - `padding-bottom`
    - `padding-left`
    - `padding-right`
- `margin`：外边距，用于定义当前元素与其他元素之间的距离（边框到外部其他元素）
    - `margin`：简写形式同`padding`
    - `margin-top`
    - `margin-bottom`
    - `margin-left`
    - `margin-right`
- `border`：边框，用于定义元素的边框
    - `border 宽度值 风格值 颜色值`:
    - `border-width`：边框宽度
    - `border-style`：边框风格
    - `border-color`：边框颜色

### 浮动布局
- 文档流
    - 正常文档流：将一个页面从上到下分为一行一行的，其中块元素独占一行，相邻行内元素在每一行中按照从左到右排列直到该行排满
    - 脱离文档流：脱离正常文档流，两种方法：浮动和定位
- 浮动`float:取值`：取值如下：
    - `left`：元素向左浮动
    - `right`：元素向右浮动
- 清除浮动`clear:取值`，取值如下：
    - `left`：清除左浮动
    - `right`：清除右浮动
    - `both`：同时清除左右浮动
    > 清除浮动还有`overflow:hidden`等

### 定位布局
```CSS
position:形式
top:像素值
bottom:像素值
left:像素值
right:像素值
```
形式取值如下：
- `fixed`：固定定位（如回到顶部），相对浏览器而言
- `relative`：相对定位，相对它的原始位置而言
- `absolute`：绝对定位，相对整个页面
- `static`：静态定位（默认值）
