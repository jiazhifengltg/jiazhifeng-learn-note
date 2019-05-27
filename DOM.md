# DOM 操作

## 概述

    - JS是以事件驱动为核心的一门语言。
    - js是采用事件驱动(event-driven)响应用户操作的。比如通过鼠标或者按键在浏览器窗口或者网页元素(按钮，文本框...)
    上执行的操作，我们称之为事件(Event)。由鼠标或热键引发的一连串程序的动作，称之为事件驱动(Event-Driver)。
    对事件进行处理程序或函数，我们称之为事件处理程序(Event Handler)。

### 事件 

    - 事件三要素   事件源,事件,事件处理程序
    - 事件源 ：要触发的对象  （一般是名词，事件发起者，比如开关按钮） 
    - 事件：怎么触发这个事情  （一般是动词，触发事件，比如点击开关）
    - 事件处理程序:发生了什么事情 （处理结果，比如灯亮了）

    - js做什么：获取事件源、绑定事件、书写事件驱动程序。


### dom节点 获取节点

    - 在HTML当中一切都是节点……
    - 由结构图中我们可以看到，整个文档就是一个文档节点。
    - 每一个HMTL标签都是一个元素节点（标签）。
    - 标签中的文字则是文字节点。（文本）
    - 标签的属性是属性节点。（属性）

    - 获取的节点因为是数组 所以想它的值就在 最后加[0]

    - 根据id获取    唯一 Element By                 Id
        var pEl = document.getElementById('p1');
    - 根据class获取   不唯一 Elements By 加s         ClassName
        var boxEl = document.getElementsByClassName('box')[0];
    - 根据标签名获取   不唯一 Elements By 加s          TagName
        var h1El = document.getElementsByTagName('h1')[0];

### 获取父节点      .paretNode                 先获取子节点   在通过子节点获取父节点   
     
    - 一个节点只有一个父节点 
    - var innerBox = document.getElementsByClassName('inner-box')[0];         获取子节点
    - var box = innerBox.parentNode                                          通过子节点 获取父节点        
    - innerBox.onclick = function(){                                        给子节点添加 点击事件.onclick      其中子节点就是事件源
        box.style.backgroundColor = 'red'                                   给子节点绑定事件  书写事件驱动程序
    }

### 众多的兄弟节点   .nextElementSibling  .previousElementSibling 先获取某个兄弟节点  在获取别的兄弟节点  

    - 获取 下一个兄弟的节点 
        + 节点2.nextSibling   嫡出 (文本,换行,空格,注释, 都算是节点) 获取的是紧挨着的下一个 节点 (ie8等 获取的是紧挨的下一个 元素节点)
        + 节点2.nextElementSibling  庶出                       获取的是紧挨的下一个  元素节点(标签) (ie 8等 不执行)
    - 获取 上一个兄弟的节点
        + 节点2.previousSibling  同上
        + 节点2.previousElementSibling 同上    不考虑ie8 的情况 就用这个
        + 兼容ie8 var nextEl = li2.nextElementSibling || li2.nextSibling;

### 单个孩子的节点     .firstElementChild     .lastElementChild      先获取父节点 在获取子节点  

    - 获取 第一个子节点
        +  父节点.firstChild    嫡出 (文本,换行,空格,注释, 都算是节点) 
        +  父节点.firstElementChild  获取元素节点(标签) 
    - 获取 最后一个节点
        + 父节点.lastChild    嫡出 (文本,换行,空格,注释, 都算是节点) 
        + 父节点.lastElementChild  获取元素节点(标签)

### 所有孩子的节点    .children 

    - 获取所有的孩子节点    获得的是一个数组    之前的获得的都是html标签
    - 通过父节点.children 来获取所有子节点      庶出  不考虑ie 678 
    - .childNodes     嫡出   
 
### 节点操作

    - var boxEle = document.getElementsByClassName('box')[0];  获取一个class名为box的标签节点

    - var pEle = document.createElement('p');               创建了一个p标签

    - pEle.innerText = '天气很热';                           给这个p标签添加内容


    - boxEle.appendChild(pEle);                             给box插入这个p标签
        + 默认从父节点的最后插入节点

    - boxEle.insertBefore(pEle,参考节点)                    
        + 把这个节点插在参考节点之前  参考节点也需要获取
        + 如果参考节点==null  则插在最后面

    - 节点操作后 仅仅只是执行了节点,没有放到页面中,所以需要插入节点操作
        才能在页面中显示 

    - boxEle.removeChild(pEle)                           
        + 根据父节点删除子节点

    - 如果不知道父节点 只知道自己这个节点 怎么删除   通过这个节点获取父节点在删除父节点的子节点

    - 子节点.parentNode.removChild(子节点)        通过自己删除自己

    - 克隆节点 cloneNode = boxEle.cloneNode(true)    
        + 参数 true，深层复制，如果是false，只复制节点本身。
        + 仅仅是克隆如果需要在页面显示 还需要插入
        + 需要新的变量接收

### 节点属性操作

    - 很少直接在js里设置css样式
    - 通常使用class名来控制样式的变化       例如导航栏的 当前页时导航栏的样式
    - 重新设值 class
    - 节点.style.color = 'red'               通过节点控制css样式

    - 节点.setAttribute('class','danger');   
        + 第一个值的意思的   确定要更改的属性名   如 class属性 id属性 等 style属性
        + 第二个值的意思的    添加变更后的属性值     对应的值

    - 节点.getAttribute('class')
        + 获取节点的这个('class')属性的值

    - 节点.removeAttribute('class')
        + 删除节点的这个('class')属性
        + 直接把class这个属性删除了  

### 节点内容操作

    - input节点.vallue = '今天天气热' //1-9的随机数
        + .vallue 只能给input节点  使用

    - .innerText  和   .textContent  功能一致  后者遗弃了
        + 节点.innerText = '内容' / 变量    变量= '内容'
        + .innerText 会把内容区的所有标签样式 都当做文本处理
        +  节点.innerText ='<p class="p2">不烦学院</p>'  这个内容会完整的 出现在页面中
    - .innerHTML 
        + .innerHTML 和 .innerText 的区别在于 前者可以把内容区的标签 样式 解析出来
        + 节点.innerHTML = '<p class="p2">不烦学院</p>'  结果为   不凡学院 

## js 补充

### arguments对象  是一个伪数组  当前函数的实参对象

    + function add(x,y){
        console.log(arguments)    // 返回 [x,y]
    } 
    + console.log(arguments instanceof Array);  返回false 说明
    + instanceof 用来判断 是不是某个构造函数的实例对象

### arguments.callee

    + argunments.callee 返回正在执行的函数本身 , 在使用函数 递归调用时 推荐 使用 arguments.callee代替函数本身.
    + function fb(n){         递归
        if(n<=2){
            return 1;
        }
        return arguments.callee(n-1)+arguments.callee(n-2);
    }

### 立即执行函数

    + ;(function(n,m){
        return n+m
    })(2,3);
    + 循环绑定 解决在需要 点击事件 发生 才能触发     更改 当循环开始时 就执行绑定事件
    + var lis = document.getElementsByClassName('li-item');            // 获取所有需要添加点击事件 的 节点  (数组形式)
		for (var i = 0; i < lis.length; i++) {                         // 循环开始 给每个 li 绑定点击事件  循环结束 此时i已经不是需要的值
			lis[i].onclick = (function(n){                             // 给绑定事件 添加立即执行函数 for每次循环 都触发立即执行函数
				return function(){                                     // 返回这个函数的结果 
					imgEl.src = 'img/' + imgArr[n];                    // 此时 n=i 给每个 li 都添加上了一个 新的img地址 
				}
			})(i);                                                     // 自执行函数 的参数i 这个参数 会在每次循环绑定的时候执行一次
		}
### addEvebtlistener 给同一个事件源 添加多个点击事件   添加事件监听器

    + 节点.onclick = function(){};     这种形式即使 控制的事件不同 但是节点相同(事件源) 也不能实现多个事件 后写的会顶替掉前写的

    + 节点.addevebtlistener('click',function(){
            alert('xxx')
      },true);

    + 括号内 三个参数
        - 第一个: 字符串形式 事件类型 '不带no'    'click'

        - 第二个: 函数(要执行的绑定事件)           function(形参){执行内容}  可以外部引入 只写函数名 

        - 第三个: 是否捕获,默认false              默认冒泡 默认 从内向外 执行   如果是 true 则从外向内的 执行顺序

            * 在事件源重叠时( 父子关系 ) 就要判断是不是要捕获, 默认冒泡  如果是 true 就先显示父 的点击事件 后显示 子的事件

            * 点击 子 的事件源时 会触发 父的事件 ,  这时候 设置  捕获 先显示父 后显示子 ;  设置  冒泡 先显示子 后显示父;

    + 在 点击 子事件源时 只触发 子事件 ( 阻止冒泡 )  

        - 形参.stopPropagation()      没有实参  形参只用来代表事件本身   形参(事件本身).stopPropagation();

        - innerBox.addEventListener('click',function(形参){
            执行程序;
            形参.stopPropagation();
        })

### 移除绑定 

    + 节点.onclick = null;

    + 只有外部引入的 节点.addEventListener('click',foo,true) 才可以通过 
        - 节点.removeEvaentListener('cllick',foo)  删除 这个节点的点击事件

    + 删除时   捕获 只能删除 捕获     冒泡 只能删除 冒泡

### 定时器 

    + 延时执行
        - var  time = setTimeout(function(){执行内容;},毫秒);

    + 清除延时执行
        - clearTinmeout(time);

    + 循环执行
        - var int = setInterval(function(){执行内容;},毫秒);

    + 清除循环执行
        - clearInterval(int);

    + 可以嵌套 比如延时执行 清除循环执行
