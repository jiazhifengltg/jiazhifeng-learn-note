### 入口函数
	- $(function(){});

## 选择器

### 基本选择器

	- 属性名例如,边框,背景等

	- $('#ID').css('属性名','属性值')   id选择器   
	
	- $('.class').css('color','red')  class选择器

	- $('li').css('font','24px')  标签选择器

	- $('.class.class-1').css('margin','10px') 交集选择器

	- 等css的复杂 选择器


### 层级选择器    css样式的 选择器  和css选择器一样

	- $('.class1 .class2').css('属性名','属性值')  后代选择器  选择所有后代

	- $('.class1>.class2').css('属性名','属性值') 子代选择器  只选择儿子级后代

	- $('.class1+.class2').css('属性名','属性值') 下一个兄弟选择器

	- $('.class1~.class').css('属性名','属性值') class1后面的 所有的类名为.class

### 过滤选择器   就是选择多个 同一class名  过滤选择的所有相同的class

	- $('li:eq(x)').css('属性名','属性值')    选择 第x个 li标签  和数组下标一致
	
	- $('li:gt(x)').css('属性名','属性值')    选择 下标大于 x 的 所有 li 标签

	- $('li:lt(x)').css('属性名','属性值')  选择 下标小于 x 的所有 li 标签 包括0下标

	- $('li:odd').css('属性名','属性值') 选择 下标 为 奇数的 所有 li标签

	- $('li:even').css('属性名','属性值') 选择 下标 为 偶数的 所有 li标签 

	- $('li:first').css('属性名','属性值') 选择 第一个 li 标签

	- $('li:last').css('属性名','属性值') 选择 最后一个 li 标签

### 属性选择器    通过 标签的属性 选择

	- a[属性]  这里的属性指的是 在html文档中 a标签的 属性 比如 class name href  

	- $('a[属性]').css('属性名','属性值') 选择所有包含 [属性] 的a 标签

	- $('li[class="li-tiem"]').css('属性名','属性值') 选择所有class='li-tiem' 的li标签

	- $('li[class!="li-tiem"]').css('属性名','属性值') 选择所有 不是class='li-tiem'的li标签	

	- $('li[class^="xx"]').css('属性名','属性值') 选择所有class= 以'xx' 开头的li标签

	- $('li[class$="xx"]').css('属性名','属性值') 选择所有class= 以'xx' 结尾的li标签

	- $('li[class*="x"]').css('属性名','属性值') 选择所有class= 包含'x' 的li标签

	- $('li[class="li-tiem"][title="内容"]').css('属性名','属性值') 选择符合所有条件的li标签

### 筛选选择器'     方法   关系  先选中一个节点 对这个节点通过关系 来获取其他节点

	- $('#j-wrap').find('li').css('属性名','属性值') 

		+ 选择id为j-wrap的所有后代元素 li

	- $('#j-wrap').children('li').css('属性名','属性值')

		+ 选择id为j-wrap的所有子代元素 li

	- $('#li-item').siblings().css('属性名','属性值')

		+ 选择id为li-item的所有兄弟元素      不包括自己
	
	- $('#li-item').parent().css('属性名','属性值')

		+ 选择id为li-item的直接父级元素

	- $('.li-nav').eq(x).css('属性名','属性值')

		+ 选择class为.li-nav 的第x个 class='li-nav'


### jq操作 事件

	- jq节点.事件类型(function(){   xxxxxxxxxxxxxxxxxxxxxx   });       

	- 事件类型 如; 点击事件 click 

	- 和dom的区别 事件类型 不加 on了  function(){} 直接写在 事件类型(里)

	- jq节点.         如果jq节点是 伪数组 可以对 数组内所有 节点 添加 事件

### css设置

	- jq节点.css('属性名','属性值')      更改 jq选择器  选择的jq节点 css样式

### attr 属性操作

	- jq节点.arrt('属性')               获取 jq选择器  选择的jq节点 的属性  例如  class src 等

	- jq节点.arrt('属性','属性值')       更改或添加 jq选择器  选择的jq节点  属性的属性值     例如  li.arrt('class','li-temp')

	- jq节点.removeArrt('属性','属性值')        删除 jq选择器 选择的jq节点 属性的属性值     例如   li.removeArrt('class','li-temp')

### text() html() val()

	- jq节点.text()                  获取 jq节点 的text 文本内容

	- jq节点.text('xxxxxxxxxx')       添加或更改 jq节点 的text内容

	- jq节点.html()       			获取 jq节点 的 所有内容  包含 html标签

	- jq节点.html('<a>123</a>')       添加或更改 jq节点 的所有 内容  包括html标签

	- jq节点.val()                 表单专用 获取jq节点 的表单内文本内容

	- jq节点.val('xxxxxxxxxx')       添加或更改 jq节点 的表单 内文本内容

### 操作class类名

	- jq节点.addClass('类名 类名');     给这个节点 添加  两个class 类名

	- jq节点.removeClass('类名');       删除 这个节点 一个class 类名

	- jq节点.toggleClass('类名');       判断 这个节点  如果没有这个类名 则添加 否则删除

	- jq节点.hasClass('类名');          判断 这个 有没有 这个class类名

### 通过关系 获取节点

	- jq节点.siblings()              获取这个节点 除自己以外的所有兄弟节点  所有的 即使标签不一样 也会获取

	- jq节点.prevAll()				获取这个节点 之前的所有兄弟节点

	- jq节点.next()                获取这个节点的 下一个兄弟节点 

	- jq节点.nextAll()           获取这个节点 后面的所有兄弟节点

	- jq节点.nextUntil(jq节点)      获取这个节点 到 另一个节点 之间的 所有兄弟节点

	- jq节点.parent()			获取这个节点的 父节点

	- jq节点.parents()   		获取这个节点的 所有父节点  父级的父级 直到 <html></html>

	- jq节点.parentUntil(jq节点)    获取这个节点到另一个节点 之间的 父节点

### 操作节点  创建 插入

	- 创建节点  var 变量 = $('<span>内容内容</span>');

	- jq节点.append(变量)

		+ 如果这个 jq节点只有一个标签 则 把变量 追加在 这个节点里的最后面

		+ 如果这个 jq节点有多个标签 则 把这个变量 给这个节点里 的所有标签里 的最后面 插入

		+ 注意事项 这个方法的变量 只能 使用一次 再次使用这个变量时  会把之前使用了这个变量的 节点给顶替掉
	
	- 变量.appendTO(jq节点)

	- jq节点.after(变量)   把这个创建的节点(变量) 当做这个jq节点的兄弟节点 插在后面

	- jq节点.before(变量)   把这个创建的节点(变量) 当做这个jq节点的兄弟节点 插在前面

### 清空节点

	- jq节点.empty();    清除 这个节点下的 所有节点

	- jq节点.html('');      本来是用来给这个节点 更改所有内容的  但是如果给更改的值 为''  也起到清除作用  

	- jq节点.remove();        这个狠起来 连自己都给删除了

### 复制节点

	- jq节点.clone();     复制节点   等同于 创建了一个新节点   和dom相同仅仅是复制   还需要插入才能生效

### 获取表单的状态

	- jq表单节点.prop('checked')    或许jq表单节点 中 被选中的状态
 
##  动画

	- jq节点.show(毫秒,function(){动画结束后执行的操作})  	slow normal fast 分别代表 600毫秒 400毫秒 200毫秒 

		+ 在 多少毫秒内 显示

	- jq节点.hide(毫秒,function(){动画结束后执行的操作})	

		+ 在 多少毫秒内 隐藏

	- jq节点.slideDown(毫秒,function(){动画结束后执行的操作})

		+ 在 多少毫秒内 滑动显示

	- jq节点.slideUp(毫秒,function(){动画结束后执行的操作})

		+ 在多少毫秒内 滑动隐藏

	- jq节点.slideToggle(毫秒,function(){动画结束后执行的操作})

		+ 判断 如果 jq节点 现在是显示状态 则效果为 在多少毫秒内 滑动隐藏        反之 在多少毫秒内 滑动显示

	- jq节点.fadeIn(毫秒,function(){动画结束后执行的操作})

		+ 在多少毫秒内 淡入显示

	- jq节点.fadeOut(毫秒,function(){动画结束后执行的操作})

		+ 在多少毫秒内 淡出隐藏

	- jq节点.fadeToggle(毫秒,function(){动画结束后执行的操作})

		+ 判断 如果 jq节点 现在是显示状态 则效果为 在多少毫秒内 淡入显示        反之 在多少毫秒内 淡出显示

	- jq节点.fadeTo(毫秒,.5)

		+ 在多少毫秒内 从隐藏达到  0.5  这个透明度

## 自定义动画  节点.animate(styles,speed,easing,callback)

	- 第一个参数表示 : 要执行动画移动的css属性     必须

	- 第二个参数表示 : 在多少毫秒内完成				可选

	- 第三个参数表示 : 运行轨迹 swing linear		可选

	- 第四个参数表示 : 动画执行完成后立即执行的回调函数			可选

	- 动画会执行完一个后在执行下一个

### 暂停动画  stop(stopAll,goToEnd)

	- stopAll 是否全部停止，     默认false  默认停止队列中所有的动画 

	- goToEnd  是否将停止的动画  默认false  默认停止在当前动画的最后一个状态  

	- jq节点.stop(true,true) 

### bom 相关

	- jq节点.height()				获取 jq节点的高度 不包括padding heborder
	- jq节点.height(200)			更改 jq节点的高度 为200px

	- jq节点.width()				获取 jq节点的宽度 不包括padding border
	- jq节点.width(200)			 	更改 jq节点的宽度 为200px

	- jq节点.offset().left			获取这个节点的left 属性
	- jq节点.offset().top			获取这个节点的top 属性
	- jq节点.offset().offset({left:50,top:60})			设置这个节点的 相对于文档的位置

	- jq节点.position().left		获取相对于其最近的具有定位的父元素的位置
	- jq节点.position().top

	- jq节点.scrollTop()    		获取 垂直 滚动条 现在距离顶部的距离
	- jq节点.scrollLeft()			获取 水平 滚动条 现在距离右部的距离  用不到了
	- scrollTop:0					直接用 改成0 放在 自定义动画 或 动画加 点击事件里

### on 方式绑定事件  off 方式 解绑事件

	- jq节点.on('mouseenter',function(){执行内容})  可以添加多个相同类型的事件 事件按顺序执行

	- jq节点.off('mouseenter')          删除指定相同类型的 所有事件

### 事件委托     事件委托 即是利用 事件冒泡，只指定一个事件 处理程序，就可以管理某一类型的所有事件

	- 事件冒泡  例如 div > ul > li > a   当给div和a标签都添加点击事件时 点击a会出现 冒泡 且两个点击事件都触发 a>li>ul>div

	- 事件委托 就是不让冒泡进行 直接结束 点你就是你,你不要在向上层反应了

	- jq节点.click(function(event){						event.targrt  就是在这个节点里 被点击的   dom节点
		  $(event.targrt).css('color','red')			实现了 给父节点 添加一个事件 让 被点到的 子节点 执行
	  })

### 触发事件 trigger    用来 触发已经 存在的事件

	- 例如 点击 空白位置 触发 需要按钮的点击隐藏效果          或者 点击图片 隐藏  点击按钮 触发图片的click事件

	- jq节点.triggrr('click')                  触发这个节点的 click事件  

### 事件对象 event

	- jq节点.click(function(event){               	这个event就是事件对象
		   $(event.target).css('color','red')
	  })

	- 事件对象 有很多对象 可以监控 鼠标参数和键盘参数    

		+ event.keyCode       键盘上 每个键的 值

		+ event.target			鼠标点击的 目标节点

### 阻止冒泡   event.stopPropagation() 

	- jq节点.click(function(event){
		event.stopPropagation()
	})

	- jq节点.click(function(event){
		event.preventDefault()
	})

### each方法

	- jq节点.each(function(index,ele){               each  可以给函数内传两个参数

		if(index>3){								index  代表当前正在遍历的 dom 的下标

            ele.onclick = function(){				ele    代表当前正在遍历的 dom节点

            alert('点击事件')
            }
        }
	})

