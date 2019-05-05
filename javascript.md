### 知识点
+ 输出方式
	- document.write('内容') 页面输出
	- console.log('内容') 控制台输出
	- alert('内容') 弹出提示框
	- prompt('内容') 接收用户输入信息弹框
+ 转化为数字类型
	- parseInt() 一般字符串转整数
	- Number()
	- parseFloat() 一般字符串转浮点数
+ 且 或 非
	- 且 &&
	- 或 ||
	- 非 !
+ date
	- 获取当前时间对象 var date = new Date();
 	-获取年 date.getFullYear();
 	-获取月 date.getMonth();
 	-获取日 date.getDate();
 	-获取星期 date.getDay();
 	-获取时 date.getHours();
 	-获取分 date.getMinutes();
 	-获取秒 date.getSeconds();
 	-获取毫秒 date.getMilliseconds();
 	-获取当前时间距离1970年1月1日0时的毫秒数date.getTime();
	-Date对象间的运算两个时间对象相减，得到的是两个对象间相差的毫秒数
+ Math
	-向上取整 Math.ceil();
	-向下取整 Math.floor();
	-最大值 Math.max();
	-最小值 Math.min();
	-伪随机 Math.random();
	-幂运算 Math.pow(x,y); x的y次方
	-四舍五入(不严格) Math.round();	