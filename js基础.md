### js引入方式
    - 外链式 <script src="地址"> </script>
    - 内嵌式 在<scrirt></script> 内直接写
    - script 标签对可以写多个, 按顺序执行
### js输出方式
    - document.write('') 页面输出
    - console.log('') 控制台输出
    - alert('') 页面弹框 输出
    - prompt('') 页面弹框 接收用户输入 
### js变量
    - 存储数据的容器
### 声明变量并赋值
    - var a = 5;    
### 命名规则 
    - 字母,数字,下划线,$,组成
    - 不能是纯数字,或数字开头
    - 不能是关键字
    - 区分大小写
    - 驼峰命名法
    - 易懂
## 数据类型
### 基本数据类型
    - Number 数字型  1,2,3
    - String 字符串型 '2'
    - Boolean 布尔值 true,false(0,NaN,''undefined,null,false)
    - Undefined 代表没有定义变量
    - Null 代表定义变量了,但是没有值
### 复杂数据类型 
    - Object 对象 无序 var a = {xxx:xx}    调用  a.xxx
    - Array 数组  有序 var a = [x,x,x,x]   调用  a[y]  y下标
### 判读数据类型
    - typeof a    var age=23  console.log(typeof age);
    - isNaN(a) NaN判断专用
## 基本类型的转换
### 其他转Number
    - Number()  
    - parsrInt() 一般用来 数字字符串 转 整数
    - parseFloat 一般用来 数字字符串 转 浮点数  
### 其他转String
    - xxxxx.tosting() 作用很广泛
    - arr.join('/') 数组转String 专用 可以改分隔符
    - console.log(''+2)  直接+一个空字符串
### 其他转Boolean
    - Boolean()
### 比较(关系)运算符
    - >, <, >=, <=, ==(只比数值,不必类型), ===(比数值,有比类型),
    - 隐式转换 根据字符编码值对比,
    - 成立为ture 不成立为false
### 算数运算符
    - +, -, *, /, %(取余),
    - + 还可以是字符的拼接关系
    - i++; i--; i**; i+=1; i*=1;                     
### 赋值运算
    - a%=1 === a=a%1
    - a+=1 === a=a+1
### Date对象的属性 时间运算 (只是获取 用的话需要赋值给新的变量)
    - var date = new Date(); 创建一个空的Date对象    Date(是构造函数) date(实例对象)
        + 获取当前时间对象 var date = new Date();
        + 获取年 date.getFullYear();
        + 获取月 date.getMonth();
        + 获取日 date.getDate();
        + 获取星期 date.getDay();
        + 获取时 date.getHours();
        + 获取分 date.getMinutes();
        + 获取秒 date.getSeconds();
        + 获取毫秒 date.getMilliseconds()
        + 获取当前时间距离1970年1月1日0时的毫秒数 date.getTime();
        + Date对象间的运算 两个时间对象相减，得到的是两个对象间相差的毫秒数
    - var year = date.getFullYear();  获取date的年份 并赋值给year  
### Math对象用法   数学运算 (只是获取 用的话需要赋值给新的变量)
    - Math.ceil(2.3); 向上取整
    - Math.floor(2.3); 向下取整
    - Math.round(2.4); 不严格的四舍五入 因为2.79999999999999 会被认为是2.8    
    - Math.max(2,3,4,5); 获取最大值
    - Math.min(2,3,4,5); 获取最小值
    - Math.random(); 伪随机 获取一个0~1的随机值
    - Math.pow(x,y); 计算x的y次方
    - Math.abs(x); 取x的绝对值
### 逻辑运算符
    - && 且 两个都满足才为 true
    - || 或 有一个满足即为 true
    - ! 取反向 !0(true), !undefined(true)  !==,   !===
### if(表达式){执行内容}else{执行内容}  存在隐式转换  判断语句
    - if(表达式){
        执行内容
        }else if(表达式){
            执行内容
        }else if(表达式){
            执行内容
        }else{
            执行内容
        } 
    - if 可以嵌套                 
    - else 可以不写
### 三元运算符  (唯一的)   if else的简写
    - ?:
    - var a = 5>3?'5大于3':'5不大于3'  
    - console.log(a);  
### for循环  循环语句
    - for(var i=0;i<x;i++);{
        声明了 循环变量 i=0; 
        循环某件事,直到i=x后,退出循环
    }
    - for循环可以嵌套
    - for(var i=0;i<x-1;i++);{
        循环 循环体内所有事件,直到i=x后,退出循环
        for(var j=0;j<x;j++){
        循环 循环体内所有事件,直到i=x后,退出循环
        }
        循环 事件  按顺序某件事完成后 开始下一项,结束后开始新的循环,
        直到i 满足退出条件;
    }
### switch 判断语句
    - 只能判断固定的 少量的值
    - switch(表达式){
         case 值1：   判断表达式是否==值1
            语句体1;    返回值
            break;      结束判断
         case 值2：   判断表达式是否==值2
            语句体2;    返回值
            break;      结束判断
         default：      如果没有相应的值 则输出这个
            语句体 n+1;  输出这
            break;     结束判断 
      }   
### while循环 和 do...while
    - while(条件表达式){    先判断条件表达式,ture就循环,false就退出循环
        循环内容           可以使用break 强制退出
    }
    - do{               先执行一次循环的内容 在判断 ture就继续执行 false就退出
        循环内容        
    }while(条件表达式)
### break 和 continue
    - break 直接退出循环, 循环结束 
    - continue 跳过本轮的循环, 开始下轮循环
## 数组 
### 创建数组
    + var arr=[x,x,x,x];   直接赋值
    + var arr=new Array;   空数组
    + var arr=[];          空数组
    + 通常数组表示的都是同一类数据的集合
### 下标的概念
    + 数组中每个数都对应一个下标
    + 下标从 0 开始,有序的排列到数组的最后一个值;
    + 数组的最后一个值得下标为,  arr.length-1;
### length 属性
    + 数组的属性之一,
    + 代表数组的值的个数,(长度)
### 通过下标给数组赋值 修改 查找
    + arr[0]='张三';  arr[arr.length.-1]='李四';
### 遍历数组
    + 通过for循环遍历数组
    + 循环变量的值i  为数组的下标
    + 判断 结束条件  i<arr.length    可以遍历到数组的最后一位 因为 < 
### 数组合并       属性
    + concat()     var newArr = arr1.concat(arr2)
    + 没有改变原数组  所以需要一个新的变量去接收它
### 数组 转 字符串  属性 
    + join('分隔符')
    + 不写默认分隔符为逗号 
       + arr.join('/')
### 字符串 转数组   属性
    + split('分隔符',数组长度)
    + 通过制定的分隔符,将字符串变为数组,默认逗号
    + 数组长度不写 默认全部 
### 数组 添加 值
    + arr.push(值)   从后插入 改变原数组  arr.push()的返回值是新数组的长度
    + arr.unshift(值)  从前插入  改变原数组   返回值是新数组的长度
### 数组 删除 值
    + arr.pop(值)   从后删除 改变原数组 返回值是删除的值
    + arr.shift(值)  从前删除 改变原数组 返回值是被删除的值
### 冒泡排序  两两比较 直接交换位置 
    + 外循环控制 轮次 总控需要比 arr.length-1 轮 最后一个不需要比较
    + 内循环控制 本轮 第一个值和第二个值比较 并判读是否交换 
        由于第二个值为 循环变量值+1 所以 循环变量 最大值为 arr.length-2
    + 循环变量都代表着下标          
### 选择排序  一对多 传递比较 交换下标 新下标的值在继续往后比较 
    + 外循环 设置 起始值下标 控制轮数 循环变量最大取值 arr.length-2 
        因为内循环的 对比值下标 是起始值下标+1 
        所以外循环的循环变量最大取值 为arr.length-2
    + 定义 假设值下标 是 起始值下标 暂时 赋予的
        因为 假设值 要与 对比值 做比较,条件成立会赋予 假设值 新的 下标
    + 内循环 设置 对比值的下标 为 起始值下标+1 
        判断 对比值 与 假设值 的条件是否成立 
        成立则把 对比值的下标 赋予假设值 
        并继续判断 获得新的下标的假设值 与 下一个对比值 循环
    + 内循环结束 
        把 获得新的下标的假设值 与 起始值 交换位置   
        外循环  起始值下标+1 再次开始外循环 直至结束 
## 函数
### 函数 声明 调用
    - 函数就是封装一些成品的代码 需要时直接调用 ====> 就是运行一遍函数内的代码
    - 声明函数  function 函数名字(形参){} 具名函数  直接用function 声明函数
        var sing = function (){}  匿名函数    需要声明一个变量去接收这个函数
    - 调用函数   函数名字(实参);   就可以调用了
        但是 调用函数 仅仅只是运行一遍函数内的代码 并没有值
    - return  可以返回函数里的一个值  函数外还需要一个变量来接收它
    - 函数 不调用 是不会执行的
### 函数 参数
    - 函数名字(实参);
    - function 函数名字(形参){
        s = 形参 + 形参
    };
    - 形参 用来占位置  实参用来 赋予 值 
    - 类似数学公式
### 返回值
    - 函数调用后 ,仅仅只是执行了一遍函数内的代码
        并没有 返回值 
    - return sum 可以返回函数内的这个值
    - 但是return 后面的代码就不会执行
    - return a-b  如果是个表达式 返回的是这个表达式的 布尔值
### 参数 数据类型
    - 如果实参是 基本类型   则不改变 原来的变量
    - 如果实参是 复杂类型   则 改变 原来的变量        
### 变量 作用域
    - 全局变量 在开头用 var声明   在函数体内直接声明不使用var(不常用)
        作用所有整个页面
    - 局部变量 在函数体内用 var声明        
        作用 这个函数内 包括 嵌套的下级
    - 变量和函数 的声明 会被提升到所有代码开头
        + 函数可以 先调用在声明
        + 变量不建议 先使用在声明(会出错)
            变量的声明提升 但是赋值没有提升
### 立即执行函数 (自执行函数)
    - 具名函数
        function  add (x,y) {
        	return x+y;
        }
    - 匿名函数
        var sub = function (x,y) {
        	return x-y;
        }
    - 自执行函数
        (function () {
        	alert('Hi,你好!');
        })();
## 递归思想
    - 简单说 就是 自己调用了自己, 
    - 计算时,从后往前想, 用 - 的办法
    - 因为 自己调用自己 用的 - 所以会出现无限 - 
    - 必须需要一个结束 调用  的 if 条件                           
        求 5的阶乘
        5!=5*4!
        4!=4*3!
        3!=3*2!
        2!=2*1!
        1!=1
        console.log(factorial(5));

        function factorial(n){
            if(n===1){
                return 1;
            }
            return n*factorial(n-1);
        }

        factorial(n); ===>
        n*factorial(n-1); ===> 
        n*[(n-1)*factorial((n-1)-1)]

        有一对兔子，从出生起后第3个月起每个月都生一对兔子，
        小兔子长到第三个月后每个月又生一对兔子， 
        假如兔子都不死，问第二十个月的兔子对数为多少？ 不死神兔
        1 1 2 3 5 8 13 21... 
        第三个数开始 n=(n-1)+(n-2)

        console.log(tuzi(8));
        function tuzi(n){
            if(n<=2){
                return 1;
            }
            return tuzi(n-1)+tuzi(n-2);
        } 
## 对象
### 对象简介
    - 对象具有属性和方法
    - 对象的作用 封装信息 各种信息 所有对象里面的值 都是不同类型的好多
    - 对象的值 保存在 堆内存中 , 对象的引用(变量) 保存在栈内存中
### 对象分类
    - 内置对象 Math Date Number String Boolean 
    - 宿主对象 由JS的运行环境提供的对象, 目前来讲主要指由浏览器提供的对象。
        + BOM DOM console document
    - 自定义对象 自己创建的对象 
### 创建对象 
    - new Object() 顶级对象
        + var obj = new  Object()   创建一个空对象       
        + obj.name = '张三'         给这个空对象添加 属性 也可以修改
        + obj.say = function(){ alert('我是李四') } 
    - 通过字面量创建一个对象
        + var obj = {
            name:'张三',
            age:'20',
            say:function(){ alert(''我是张三) },
            child:{
                name:'小明',
                age:3
            }
        }
        + 在创建的时候 直接指定对象中的属性和方法              
        + 追加和修改 同上 
    - 自定义构造函数
        + function person(){        this 指针 指向实例对象
            this.name = '张三';         如果没有实例对象 则指向调用者
            this.age = 20;
            this.child = {
                name: '小明',         通过这种方法创建对象 类似提取公因式
                age: 3
            };
            this.say = function(){
                alert(this.name)
            }
        }
        var obj3 = new person;   通过自定义的构造函数 new 一个带属性的函数
### JSON
    - javaScript Object Notation 是一种轻量级的数据交换格式
    - JSON 是js对象的字符串表示法 它使用文本表示一个js对象的信息,
        本质是一个字符串
    - var obj = {a: 'hello', b: 'world'}   这是一个对象
    - var json = {"a": "hello", "b": "world"} 这是一个JSON对象 
            里面只能用""
### window.JSON
### stringify : 把JSON格式/普通格式的对象 装换为 JSON格式的字符串
    - var obj = {a: "hello", b: "world",c:9 }    普通对象
    - var json = {"a":"hello","b":"world","c":9}  JSON对象
    - var str = JSON.stringify(obj); 
        ====>
         str = '{"a":"hello","b":"world","c":9 }'   JSON格式的字符串

### parse : 把JSON格式的字符串 转换为 JSON格式的对象
    - var str = '{"a":"hello","b":"world","c":9 }'  JSON格式的 字符串
    - json = JSON.parse(str);
    - var json = {"a":"hello","b":"world","c":9 }    JSON格式的 对象
### 遍历对象 for in
    - for(var key in json){
        key是变量  需要 json[key] 获取对象属性值    
        对象[变量]    如果属性是变量 就只能通过这种方式获得属性    
    }
## 数组高级API .属性
    - toSting() 数组转换成字符串 用逗号 隔开    未改变原数组      
        + arr.toSting(',')

    - reverse()  反转数组   改变原数组
        + arr.reverse()

    - sort() 给数组排序   按字符集编码排序  改变原数组
        + arr.sort(function(a,b){return a-b});   按数字大小排序   

    - indexOf()  从0下标开始 查找某个值的下标 返回下标
        + arr.indexOf('小明')

    - lastindexOf() 从 arr.length-1 (数组最后一个下标)开始 查找一个值的下标  
        + arr.lastindexOf(9)

    - slice(start,end) 复制一段原数组的 不会影响原数组 所有需要变量接收
        + arr.slice(1,5) 从下标1开始 复制到 下标4   复制范围不包括后面的值
        + arr.slice(0) 从下标0开始 复制到 所有arr数组

    - splice() 删除或替换当前数组的某些项目   修改原数组
        + arr.splice(2,3,'张三',3,'4')     返回值是被删除的或替换的值
            * 第一个值 意思是 从下标 2 开始;
            * 第二个值 意思是 删除或替换的个数;
            * 第三个值往后 意思是 替换的内容 
            * 如果 删除的个数是 2 但替换的内容 却只有1个 则1个替换删除的2两     
            * 如果 没写替换则意思是 从x下标开始删除y个元素
    - 清空数组  
        + arr.length = 0;    长度归零;
        + arr = [];          赋予数组空值;      
    - 数组合并       属性
        + concat()     var newArr = arr1.concat(arr2)
        + 没有改变原数组  所以需要一个新的变量去接收它
    - 数组 转 字符串  属性 
        + join('分隔符')
        + 不写默认分隔符为逗号 
           + arr.join('/')
    - 字符串 转数组   属性
        + split('分隔符',数组长度)
        + 通过制定的分隔符,将字符串变为数组,默认逗号
        + 数组长度不写 默认全部 
    - 数组 添加 值
        + arr.push(值)   从后插入 改变原数组  arr.push()的返回值是新数组的长度
        + arr.unshift(值)  从前插入  改变原数组   返回值是新数组的长度
    - 数组 删除 值
        + arr.pop(值)   从后删除 改变原数组 返回值是删除的值
        + arr.shift(值)  从前删除 改变原数组 返回值是被删除的值        
## 字符串对象的常用方法    都没有改变原 值
    - 字符串也有长度 str.length      
        + console.log(str.length);   21

    - var str = 'how are you? and you?'
    
    - charAt() 获取相应位置的字符    
        + console.log(str.charAt(5)); r
        + 空格也占位置   

    - charCodeAt() 获取指定位置的字符 的 Unicode 编码   
        + console.log(str.charCodeAt(5)); 114 

    - indexOf() 返回字符在字符串中的位置   从左往右
        + console.log(str.indexOf('y')); 8 

    - lastindexOf()  返回字符在字符串中的位置    从右往左
        + console.log(str.lastindexOf('y'));  17 

    - concat() 连接字符串
        + var str2 = ' me too';
        + console.log(str.concat(str2)); 

    - slice() 提取字符串的某个部分      
        + str.slice(0,9)   从第1位开始 复制到第9位 
        + str.slice(0)  复制所有

    - substr()  提取字符串的某个部分 
        + str.slice(2,9)   从第3位开始 往后复制9位 

    - toUpperCase()    
        + str.toUpperCase() 转换为大写
    - toLowerCase()
        + str.toLowerCase() 转化为小写

