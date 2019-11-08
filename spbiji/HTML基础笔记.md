一、HTML基础
HTML定义：
HTML（HyperText Markup Language）超文本标记语言（超文本标签语言)，是一种制作网站的语
言。
HTML 语言不需要编译，由浏览器直接读取代码而渲染效果。
HTML5 到底是什么
HTML5 = HTML5 的标签 + CSS3 + JavaScript + api (浏览器提供的操作接口)，目前阶段我们只学习
HTML5 的基础标签。
二、颜色值的设置
大多数的浏览器都支持颜色名集合
颜色值是一个关键字或者是一个rgb格式的数字都可以
主要有两种 英文单词: yellow 黄色 red 红色 等
6位的十六进制颜色值： #FF 00 00

三、HTML的主题结构
(1) 最顶部的声明
告诉浏览器以什么样的标准解析这个网页的。
HTML5 标准老浏览器都兼容这个标准。
声明时文档的第一个部分位于最顶部
(2) 以 <html> 开始以 </html> 结束中间包含头部标签 <head></head> 和主体标签 <body></body>



(3)了解级别:

<html>

<head>
<!--
title标签 代表html文档的标题
meta标签 用于定义文件信息的名称、内容等信息
link标签 当在文档中声明使用外部资源（如css）时使用此标签
style标签 在文档中声明样式时使用
script标签 在文档中使用JavaScript脚本
base标签 将相对url转换为完整的绝对url
-->
<!-- 设置字符集 -->
<!-- html5 支持的html设置字符集-->
<meta charset="utf-8"/>
<!-- html 4.01 支持-->
<meta http-equiv="content-type" content="text/html; charset=utf-8">
<!-- 网站关键字 -->
<meta name="keywords" content="8-12个以英文逗号隔开的单词或者语句如:姓
名;name;age;中文;"/>
<!-- 网页的描述信息 -->
<meta name="description" content="80字以内的一段话，与网站相关"/>
<!-- 网站作者 -->
<meta name="author" content="Martin Lee" />
<!-- 网页版权 -->
<meta name="copyright" content="2008-2017 版权所有"/>
<!-- 3秒后自动跳转 -->
<!--<meta http-equiv="refresh" content="5;url=http://lol.qq.com"/>-->
<title>欢迎访问天地建射银行网站</title>
<!-- 外部链接样式表 -->
<!-- 可以多册重复引用不同的样式表 -->
<!-- <link rel="stylesheet" type="text/css" href="./css.css"/>
<link rel="stylesheet" type="text/css" href="./style.css"/>
<link rel="stylesheet" type="text/css" href="./a.css"/>-->
<!-- css 样式表 -->
<style >
body{background:yellow;}
</style>
<!-- javascript 脚本 -->
<script>
// alert('男人都是鳝变的');
</script>
<!-- 将 相对路径 转换为 绝对路径 -->
<!--<base href="http://www.baidu.com"></base>-->
</head>
<body>
<!-- a超链接标签 -->

<a href="链接地址"></a>

<!--
相对路径
只说你当前位置的内容
绝对路径
地球中国北京昌平回龙观育荣教育园区oto直播间
-->
</body>
</html>
四、body 中常用标签
body 常用属性
bgcolor
设定页面背景颜色
background
设置页面的背景图片
text
设定页面文字的颜色
五、列表标签
1、 <br/> 换行标签
2、 <hr/> 水平分割线标签
3、 <p></p> 段落标签，里面可以加入文字，列表，表格等
4、 <center></center> 居中对齐标签
5、 <pre></pre> 按原格式显示标签
6、 <li></li> 每个列表标签
7、 <ul></ul> 无序列表
8、 <ol></ol> 有序列表

六、文本标签
1、 <hn> 标题字标签 n为1-6 定义六级标题 而且 会自动换行插入一个空行
2、 <b> 粗体字标签
3、 <i> 斜体字标签
4、 <u></u> 下划线字体标签
5、 <sub> 文字下标字体标签
6、 <sup> 文字上标字体标签
7、 <font> 字体标签
8、 <em> 表示强调 通常为斜体字
9、 <strong> 表示强调 通常为粗体字
10、 <small> 小型字体标签
11、 <big> 大型字体标签
12、 <tt> 打字机文字
13、 <cite> 用于引证举例 通常为斜体字
14、 <del> 删除线
15、 <details> 定义元素细节 用户点击查看
16、 <summary> 为datails 标签定义标题
17、 <dialog> 聊天标签，属性：open=‘true’
七、图片标签
<img /> 单标签
常用属性:
src 代表一个资源地址(就是图片位置 )必须有
路径:
相对路径
./image/1.jpg
当前目录
./
上级目录
../
绝对路径 以http[https]开头的www远程站点的绝对路径
根目录
/
alt 如果无法显示图像，浏览器将显示替代文本
border 给图片加边框 单位像素 px
width 图片的宽度
height 图片的高度
注意: 宽度和高度 不能同时使用 否则图片失真 如果要效果改变 这两个属行 修改一个即可
title 提示字
八、超链接标签
a 标签
<a></a>
属性
href="" 跳转的连接(就是要跳转到什么地方)
target
_blank 新窗口打开
_self 当前窗口打开 (默认值)
九、多媒体标签
1、 audio 声音标签
	audio 声音标签，中间的文字是给不支持这个标签的浏览器使用的
	属性：
	autoplay 自动播放 不用写值，不想用直接删除，
	但直接打开有时候浏览器会抽风，火狐相对支持的比较好
	controls 播放插件
	str 声音来源地址
	loop 单曲循环
	preload 如果出现该属性，则音频在页面加载时进行加载，并预备播放。
	如果使用 "autoplay"，则忽略该属性。
2、 video 视频标签
	属性
	src 视频来源地址
	autoplay 自动播放
	controls 播放插件
	loop 视频循环播放
	width 视频宽度，根据视频大小，视频像素不高，定义无效
	height 视频高度，根据视频大小，视频像素不高，定义无效
	poster 定义视频点击播放前显示图片
3、 source 资源标签
	source 资源标签 浏览器可能不支持其中的声音格式，可以使用此标签多标注音源
	此标签必须配合声音或者视频标签使用
4、 embed 插件标签
	属性
	src 定义资源地址
	width 定义宽度
	height 定义高度

十、table表格

table 表格标签
	属性:
	border 边框 单位是像素 px 值为0 没有边框
	width 表格的宽度 单位可以使用像素或者百分比
	height 表格的高度 单位可以使用像素或者百分比
	align 表格的相对于周边的位置 left|center|right
	bgcolor 表格的背景颜色
	background 表格的背景图片
	cellspacing 单元格间距 是单元格之间的边距 单位为像素 默认为 2px
	cellpadding 单元格内边距 单元边沿与其内容之间的空白 单位为像素 默认值为 1px
	tr 代表html表格中的行
属性
	align 内容水平位置 left|center|right
	valign 内容垂直位置 top|middle|bottom
	bgcolor 背景颜色
	height 高度
注意 ：tr 没有宽度这个属性 切记 不要写width
	td 代表html中的表格中列，也可以称为单元格
	height/width 高度和宽度
	对齐
	align
	valign
	left|center|right
	top|middle|bottom
	th 代表html中的表格中的单元格
	但是他有特殊的样式 加粗字体 居中显示
	
十一、form 表单（重点）
	什么是表单？我们的网站中处处都有表单，它的目的是供用户填写资料，传递给服务器，让服务器给数
	据做处理。

11.1input 表单项
	form 表单
	属性
	aciton 必填，提交到的哪个地址，相对路径
	method 必填，用什么方式get，post
	get：默认，通过地址栏的方式把数据提交过去
	post：相对get脱离地址栏，通过类似隐藏的方式提交过去。
	通常数据过去以后通过PHP对应的方式会接收数据，我们暂时无法做到。
	input 表单项，隶属于form（想写input必须使用form表单包裹，要不无法提交）
	属性
	name 此表单项的名称
	value 此表单项的默认值
	type 此输入域的显示类型
	text：普通文本域
	password：密码域
	radio：单选框 只能选中一个而且必须选中一个
	注意: 单选框所有name名称保持一致，这样才会有相互排斥的效果。
	选中使用关键词checked
	checkbox:复选框可以选择零个也可以选择多个
	注意: 复选框name也要一致，并且在name名称后面加上[]（中括号）
	选中使用关键词checked
	file：可以选择一个文件路径
	reset：重置按钮，可以把表单的内容清空恢复默认值
	submit：提交按钮，表单填写的值传递给服务器
	button：普通按钮，多数用于js，后期会学
	image：自定义图像按钮
	hidden：隐藏域





