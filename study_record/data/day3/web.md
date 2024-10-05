# web

### HTML

后缀：.html

名称：HTML--->超文本标记语言(HyperTextMarkupLanguage)

标签写法：成对出现，包裹内容(开始标签格式是<  >，结束标签是</  >)

标签种类：

​	双标签：成对出现的标签

​	单标签：只有开始标签，没有结束标签

标签关系：

​	父子关系（嵌套）

​	兄弟关系（并列）

标签属性：

​	格式：属性名="属性值"

​	属性写在<>中，标签名后，用空格隔开，多个标签间无顺序

路径：

 1. 相对路径

    从当前文件位置出发查找目标文件

    文件夹名/		表示进入某个文件夹中

    ./						表示当前文件所在文件夹

    ../						表示当前文件所在文件夹的上级文件夹

 2. 绝对路径

    从系统 根目录/盘符 出发查找目标文件

注释：

注释是对代码的解释和说明，目的是让代码更易懂，通过对代码的解释，提高可读性

同时方避免写了很多代码后忘记代码的功能

```html
<!-- -->
```

HTML骨架

```html
<html>
	<head>
        <title>网页标题</title>
	</head>
    <body>
        网页主体
    </body>
</html>
```

> html：整个网页
>
> head：网页头部，存放浏览器元素（给浏览器看的代码，css）
>
> body：网页主体，存放用户元素（给用户看的代码，图片文字）
>
> title：网页标题

标签：

```html
<br>
```

> 换行

```html
<hr>
```

> 水平线

```html
<h1></h1>
```

> 一级标签（一个网页建议使用1次）
>
> 修改数字会对应不同等级的标签（最高6级）

```html
<p></p>
```

> 段落标签
>
> 独占一行
>
> 段落之间有间隙

```html
<strong></strong>
```

> 文本格式化标签：
>
> 加粗：strong/b
>
> 倾斜：em/i
>
> 下划线：ins/u
>
> 删除线：del/s

```html
<img src="图片的URL" alt="">
```

> 图片标签
>
> 用scr指定位置和名称（必须）
>
> 其他属性：（非必须）
>
> ​	alt		替换文本（是图片无法显示时显示的内容）
>
> ​	title	  提示文本（鼠标悬停在图片上时显示的内容）
>
> ​	width   图片的宽度
>
> ​	height  图片的高度	

```html
<a href="需要跳转的链接"></a>
```

> 超链接
>
> 作用：点击跳转到其他页面
>
> 属性：
>
> ​	href		表示需要跳转的链接（必须）（约定填#表示空链接）
>
> ​	target	表示打开链接后窗口的属性（_blankb表示在新窗口打开）

```html
<audio src="音频URL"></audio>
```

> 音频标签
>
> 属性：
>
> ​	src		音频URL	支持mp3，ogg，wav
>
> 下面这些都是布尔类型的，有无属性值都行
>
> ​	controls	显示音频控制面板（就是进度条那些）
>
> ​	loop		循环播放
>
> ​	autoplay	自动播放（有些浏览器会禁用此功能）

```html
<video src="视频的URL"></video>
```

> 视频标签
>
> 属性：
>
> ​	src	视频的URL
>
> ​	controls	显示视频控制面板
>
> ​	loop			循环播放
>
> ​	muted		静音播放
>
> ​	autoplay	自动播放（有些浏览器只有在视频静音播放时会自动播放）

列表

无序列表

```html
<ul>
	<li></li>
    <li></li>
</ul>
```

> ul是无序列表（注意ul标签里面只能包裹li标签）
>
> li是列表条目

有序列表

```html
<ol>
	<li></li>
    <li></li>
</ol>
```

> ol是有序列表（ol标签里只能包裹li标签）

自定义列表

```html
<dl>
    <dt>列表标题</dt>
    <dd>列表描述/详情</dd>
</dl>
```

> dl表示自定义列表（dl里面只能有dt和dd）
>
> dt表示列表的标题
>
> dd表示列表项

表格

```html
<table>
    <tr>
    	<th></th>
        <th></th>
        <th></th>
    </tr>
    <tr>
    	<td></td>
        <td></td>
        <td></td>
    </tr>
</table>
```

> 这是一个2x3的表格
>
> table表示表格
>
> tr表示表格的行
>
> th表示表头单元格
>
> td表示内容单元格
>
> 表格默认没有边框线，用border属性可以给表格添加边框

表格结构标签

```html
<thead></thead>
<tbody></tbody>
<tfoot></tfoot>
```

>分别表示表格头部，表格主体，表格底部

合并单元格

属性：

​	跨行	rowspan属性，值为数字表示合并单元格的个数	

​	跨列	colspan属性，值为数字表示合并单元格的个数

合并时只需要保留最前面的单元格，其他的需要删除

表单

```html
<input type="">
```

> 用来输入内容
>
> type属性（必须）
>
> text		单行文本框
>
> password	密码框
>
> radio		单选框
>
> checkbox	多选框
>
> file		上传文件
>
> type专属属性
>
> 文本框	密码框
> placeholder		占位文本
>
> 单选框
> name	控件名称，用于分组，同组只能选择一个
> checked	默认选中	类型布尔
>
> 上传文件
> multiple	文件多选
>
> 多选框
> checked	默认选中

下拉菜单

```html
<select>
    <option></option>
    <option></option>
    <option></option>
</select>
```

> select是下拉菜单整体，option是其中的每一项
>
> 默认选中是第一个，也可以设置属性selected来默认选中需要的那个

文本域

```html
<textarea></textarea>
```

> 多行文本控件
>
> 属性
>
> cols 和 rows设置尺寸

label标签

```html
<label></label>
```

> 通常用于提示文字的显示
>
> 也可以用来增大点击范围
>
> 支持的表单控件：文本框，密码框，上传文件，单选框，多选框，下拉菜单，文本域等

```html
<input type="radio" id="man">
<label for="man"></label>
```

```html
<label><input type="radio">内容</label>
```

> 第一种写法：id和for相同的时候可以让点击label也能选中单选框

按钮

```html
<button type=""></button>
```

> 点击后干点什么
>
> type属性
> submit		提交按钮，点击后提交到后台
> reset		重置按钮，将表单恢复到默认
> button	普通按钮