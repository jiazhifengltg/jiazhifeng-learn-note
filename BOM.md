## BOM

    ### 'ECMAScript' 是 'javascript' 的核心, 但是如果要在 'web' 中使用 'javascript' ,
        那么 'BOM'(浏览器对象模型)才是真正的核心.BOM提供了很多对象,用于访问浏览器的功能,这些功能与任何网页内容无关.

    ### 'BOM' 的核心对象是'window',它表示浏览器的一个实例. 在浏览器中'window'对象有双层角色,它既是通过'javascript'
        访问浏览器窗口的一个接口, 又是'ECMAScript'规定的'Global'对象.所有全局作用域中声明的变量,函数都会变成'window'对象的属性和方法.

## 三大家族其一 offset 家族

    ### offsetWidth 和 offsetHeight  检测获取 盒子的宽高
 
        + 绑定到所有的节点上 获取既用
        + offset 宽/高  =  盒子自身的宽/高(Width/Height) + padding + border

    ### offserLeft 和 offsetTop     检测获取 距离父盒子有定位的左/上 的距离

        + 从有定位的父亲的 padding开始算 
        + 父类没有定位 从body算
        + 只读属性 可以用但不能修改

    ### offserParent  检测获取 有定位的父盒子节点

        + 返回该对象的父级 直到body
        + 返回最近的有定位的父级节点

    ### pageX / pageY 

        + 鼠标当前位置 距离浏览器的距离

    ### offsetX / offsetY

        + 鼠标距离当前元素边界的距离

    ### style.top / left

        + 返回到 有定位 父级的距离 
        + 返回的是 字符串 带px单位
        + 可以修改
        + 只能获取行内样式 如果行内没有 则返回空

## 动画原理

    ### 物体运动 : 起点.终点.速度(距离/时间);

    ### 盒子位置 : 盒子本身所在的位置 + 步长;

### 匀速动画 

### 缓动动画 

    ### 步长 = (终点-起点)/10 

### 事件对象 Event 对象代表事件的状态 比如事件在其中发生的元素 键盘按键的状态 鼠标的位置 鼠标按钮的状态

    - 获取event对象的兼容写法  event || window.event
    - event.target          事件的目标 获取target 兼容写法 event.target || event.srcElement
    - e.pageX  e.pageY      获取鼠标点击的相对于页面的位置 
    - e.clientX e.clientY   获取鼠标点击的相对于可视区域的位置
    - e.screenX e.screenY   获取鼠标点击的相对于屏幕的位置
    - e.offsetX/Y           获取鼠标点击位置相对于 触发事件对象的位置
    - event.type            事件的类型
    - event.button          获取鼠标点击的按键 onmousedown 鼠标按下事件 测试 左中右 0 1 2 
 
### 事件委托

    - 通过监听一个父元素,来给不同的子元素绑定事件 减少监听次数 从而提升速度.
    - 由于事件的冒泡机制,可以使用事件委托的方式给元素添加事件,多用于ul监听事件更改li的情景
    - element.onclick = function(e){
        e = event || window.event;

        var target = e.target || e.srcElement;

        if(target.tagName === 'LI'){
        target.style.color = 'red'
        } 
    }
    - 获取事件对象的 target目标元素  父节点的子节点
    - 通过target 目标元素 的 tarName 属性 来完成事件委托 
    - target.tarName 的值 为 大写字母

### 阻止冒泡

    - event.stopPropagation();              存在兼容问题
    - IE <= 10 专用 event.cancelBubble = true 
    - 兼容写法 event.stopPropagetion ? event.stopPropagetion() : event.cancelBubble = true;

### 三大家族之一  scroll

    - scrollWidth / scrollHeight  检测盒子的宽高  盒子高度 + padding  如果盒子里的内容超过超出了 显示内容的高度 
    - scrollTop / scrollLeft  可以获取元素被浏览器卷入的部分 也可以修改

        + 获取 var scrollTop = document.document.scrollTop || window.pageYOffset || document.body.scrollTop;
        + 修改 写法 element.scrollTop/Left = xxx 

### onscroll 事件

    - 滚动事件 当滚动条 滚动时触发的事件
    - 必须有滚动条 才可以触发
    - element.onscroll=function(){}

### 关于window.scroll() window.scrollBy() window.scrollTo()

    - window.scroll(x,y)            让window滚动条 滚动到x,y坐标
    - window.scrollBy(-x,-y)        让window滚动条 滚动 x y 的距离
    - window.scrollTo(x,y)          同上

### 三大家族之一 client

    - clientWidth / clientHeight
        + 获取盒子的高度 client 宽/高 盒子自身高度 + padding
        + document.docunmentElement.clientWidth/clientHeight  获取浏览器可视区域宽高   没有兼容问题

    - clientTop / clientLeft 只读
        + 内容区域左上 相对于元素左上 的位置    实际就是border 的宽度
        + 内容区域指 内容+padding     那么对于一个盒子 内容+padding 之外就只剩下啊border了
        + 一个元素 顶部和左侧 的border宽度 

### 对比 offset scroll client

    - width/height

        + offsetWidth/offsetHeight 获取 盒子高度 + padding + border                 只读
        + scrollWidth/scrollHeight 获取 内容高度 + padding                          只读  
        + clientWidth/clientHeight 获取 盒子高度 + padding                          只读

        + document.documentElement.clientWidth  可以获取可视区域的 浏览器宽高
        

    - top/left

        + offsetTop/offsetLeft 获取 子盒子 到最近定位 父盒子 的距离                  只读
        + scrollTop/scrollLeft 获取 滚动条 被 卷入 的 距离                          读写 有兼容问题
        + clientTop/clientLeft 获取 盒子 的 上 左边框 宽度                          只读

        + window.scroll(x,y) 可以设置 滚动条的坐标 根据 x = left, y = top
        + window.scrollBy(x,y) 设置相对于 现在 让滚动条 移动多少px    可以是负数
        + window.scrollTo(x,y)  同上

    - x/y

        + offsetX/offsetY 获取 鼠标在  盒子里  距离  盒子        的距离
        + clientX/clientY 获取 鼠标在 浏览器里 距离 浏览器可视距   的距离   只包括浏览器可视距离

        + pageX/pageY    获取  鼠标在 浏览器里 距离 浏览器顶部的距离        还包括浏览器卷入距离

### 获取元素的样式

    - 获取行内样式 
        + ele.style.styleName                  节点.style.属性名
    
    - 获取 行内 内联 引入 样式   
        + 谷歌 火狐 window.getComputedStyle(element,[pseudoElt]).styleName              window 可省略

            * element     要获取样式的节点 
            * pseudoElt   获取伪元素 填上伪元素的名字  获取普通的元素 不填 或填 null

        + ie  element.currentStyle.StyleName 

        + 兼容 
        function getStyle(ele,styleName){
            if(ele.currentStyle){
                return ele.currentStyle[styleName]
            }else{
                return window.getComputedStyle(ele,null)[styleName]
            }
        }

### 获取对象的属性 如果该属性是变量,那么需要用[]的形式 包裹 不能用 . 

    - var abc = "name"
    - abc 变量    "name" 值
    - var user = { name:"张三", } 
    - 如果要获取张三 则两种方法              user.name /  user[abc]   

    