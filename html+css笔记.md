# html
	* html是构成网页的结构.
	* html是一种超文本标记语言.
	* html的结构布局对前端开发很重要.
	* html书写要规范.便于以后维护.
	* html的结构是由大量标签组成,标签的表现形式为<开始标签>属性名="属性值">内容</结束标签>.
	* 常见的标签有<h1>~<h6>,<p>,<br/>,<hr/>,<div>.等.
### 路径问题
	- 相对路径
		+ 同一级目录直接引用.
		+ 下一级目录:先引用同级目录在引用下一级.
		+ 上一级或多级:"../"代表返回上一级.
	- 绝对路径
		+ 网络路径与本地路径:直接引用文件的位置.
### 超链接标签 <a>
 	- href.内是跳转地址,暂时没有时用#号占位.
 	- target:blank.这个属性可以让超链接在新窗口打开.默认是当前页面跳转
 	- text-decoration:none.这个属性可以去除超链接默认的下滑线样式. 
### 列表标签 ol>li ul>li dl.dt.dd
	- ul>li 无序列表.最常用.
	- list-style:none 这个属性可也去除列表样式
### 字体标签
	- em/strong.斜体/加粗.em表示着重点.strong表示重要性.
	- i/b.斜体/加粗.单纯字体该变.没有语义化.
	- sub/sup.下标/上标 特殊表示.
	- ins/del.下划线/删除线.
### 转义字符
	- 空格 &nbsp; &#160;
	- 小于号 &lt; &#60;
	- 大于号 &gt; &#62;
	- 等等;
### 表格
	- table标签.
		+ align:left/center/right. 表格的位置属性.
		+ border:1px.表格的边框属性
		+ bgcolor:red.表格的背景颜色.
		+ cellspacing:1px.单元格与单元格之间的距离.
		+ cellpadding:1px.文字和单元格之间的距离.
	- th标签.
		+ 代表首行.	
	- tr标签.
		+ align:left/center/right.文字对齐方式.
		+ bgcolor:green.当前行的背景色.
	- td标签.
		+ colspan:2.单元格所占的列.
		+ rowspan:3.单元格所占的行.
### 表单

	- fieldset     legend     分隔框    legend 类似表头 名字

	- form标签.用于包括输入框,提交数据.
		+ action  提交地址
		+ method:get/post.默认是get方式.提交方式
			* get.
				- 参数放到地址栏提交.
				- 不安全.
				- 地址栏参数长度有限.
				- 一般都是用来获取数据的.
			* post.
				- 地址栏不显示提交内容.
				- 相对安全.
				- 提交的数量没有上限.
				- 一般用于提交保存数据.
	- input标签.单行输入框标签,根据type的类型不同.表现不同.
		+ type.必须要有的属性.
			* type:text. 单行文本输入框.
				- name.必须要有.提交的时候后台程序需要通过name属性获取表单的内容.
				- value.当前表单的内容.
			* type:password.密码输入框.	 				
				- name.必须要有.提交的时候后台程序需要通过name属性获取表单的内容.
				- value.当前表单的内容.
			* type:radio.单选框
				- name.必须要有,表示他们是一组的.
				- value.必须要有,提交的是value的值,一般用数字编写.
				- checked.默认选中状态.
			* type:checkbox.多选框.
				- name.必须要有,表示他们是一组的.
				- value.必须要有,提交的是value的值,一般用数字编写.
				- selected.默认选中状态. 	 	
			* type:submit.提交按钮.
				- value.按钮显示的内容.
				- 点击后表单被提交到form action:xxxx配置的地址.
			* type:file.上传框
				- 当选中的时候,市级文件并没有被上传上来.
				- multiple.可以实现多选.
	- select标签.下拉选框.
		+ option标签.选框中的选项.
	 		* name.需要设置.
	 		* value.需要设置.
	 		* selected.
	- textarea标签.多行文本框.
		+ cols/rows.可以设置框的宽度和高度.
		+ name.值需要设置.
		+ vlaue.标签内部的内容.
		+ readonly.只读属性.输入框的内容被锁定.
		+ disabled 禁用属性.表单的值在提交时.会被舍弃.
# css
	* 全称层叠样式表(cascading style sheets).用于实现页面的样式.
	* 层叠.简单来说就是一个元素可以多次对他设置同一个样式.但是具体生效要看谁得权重更高.
### 书写位置
	- 行内样式 
	- 内部样式. style
	- 外部样式.	link
### 选择器
	- 简单选择器
		+ 标签选择器
		+ id选择器
		+ class选择器
		+ *选择器(通配符)
	- 复杂选择器
		+ 并集选择器
		+ 交集选择器
		+ 后代选择器
### 继承性
	- css大多数字体样式都可以被继承(a标签除外)
### 层叠性
	- 样式冲突.必然有一个生效.
### 权重问题
	- 行内样式:1000
	- id选择器:100
	- class选择器 10
	- 标签选择器 1
	- *和继承属性 0
	- 相同权重.距离代码近的生效.
### css单位
	- px像素
	- em父元素字体大小的倍数.
	- %父元素的百分比.					
### 常用属性
	- width. 宽
	- height. 高	
	- color.字体颜色(前景)
	- font-size. 字体大小
	- font-family. 字体
	- font-weight. 字体加粗
	- font-style. 字体样式
	- text-align. 文本对齐方式
	- text-indent. 文本首行缩进
	- line-height. 文本行高
	- background. 背景
		+ background-color. 背景颜色. color
		+ background-image. 背景图片. rul()
		+ background-repeat. 平铺方式. no-repeat repeat-x
		+ background-position. 图片位置. top center
		+ background-attachment. 背景滚动. fixed
### 标签的表现形式
	- 块状标签.block
	- 行内块标签.inline-block
	- 行内标签.inline
### 盒子模型
 	- 页面中的所有元素都可以看做是一个盒子.
 	- 所有盒子都可以分为.
 		+ 内容区
 		+ padding区.
 		+ border区.
 		+ margin区.
 	- 盒子居中的方法.margin:0 auto;	
 	- border和padding会影响盒子的大小.
 	- display.该变元素的表现形式.none为隐藏
 	- visibility.隐藏后还会占着位置.	
### 文档流
	- 就是不使用浮动和定位.根据标签的特性从上到下排列下来的页面.
### 浮动 float:
	- 三个值.left.right.none.
	- 浮动的元素会脱离文本流,不在占据原本的位置,并上升到父类的边界,或其他浮动元素.
	- 浮动的元素(不设置宽高)会被内容撑起来.没有内容会变成一个点
	- 浮动的元素(其父类不设置宽高).不会撑起父类.解决父类加overflow:hidden.
### 定位 position:可以定位到页面中任意一个位置.
	- 4个属性.relative.absolute.fixed.static(默认).
		+ relatuve.相对自身原本的位置.没有脱离文档流
		+ absolute.绝对与最近的有定位元素的父级做定位.脱离文档流
		+ fixed.相对于浏览器做固定定位.不会随着浏览器变形改变位置.
	- left.top.优先级大于right.bottom.
	- left.表示子级左边距离父级左边的距离.right表示子级右边距离父级右边的	距离.其他同理.
	- z-index.指定被定位过后元素的显示层级,越高越优先显示.默认0.
### 简单布局思路
	- 文档流
	- 浮动(左侧并排)
	- 定位(右侧定位,个别小图标,个别hover效果,)
### 个人布局思路总结
	- 行状模块化布局
		+ 把整个页面拆分成一行一行.
		+ 相同样式同个class.
		+ 相同模块就可以拿了直接用.
	- 好处
		+ 思路更清晰.
		+ 出错更易查错.
### 难点
	- class命名.不清楚一个页面内某个部分叫什么名字.

### 表单

	- readonly 只读属性

	- disabled 不可用属性