# ajax
Ajax的相关知识

AJAX:全名Asynchronous JavaScript And XML;即异步 js 和 XML。

ajax并不难，难的是拿到数据之后该干嘛；ajax不是新的技术；而是由老技术组合而成的；最早期的使用是由google的**联想搜索**；

ajax是前后端数据交互的一种技术，可以动态的获取数据；

### 优点
1. 减轻服务器的压力，节约空间和宽带租用成本；
2. 不用刷新页面就能获取数据，优化用户体验；

### XML数据格式

XML长得有点像html，XML中可以自定义元素。

		'<person>
			<name>王露</name>
			<age>14</name>
		</person>

工作中,首先要明确以下几点：
1. 跟后端要字段，字段的意思是什么；
2. 跟后端要接口；
3. 请求的方式；
4. 把数据填好再运行一下确认没有错误。

**get:**
1. 以url的方式去传输的；
2. 相对来说不安全；
3. 体积小，无法上传大数据；

		get写法：
			1. 创建一个ajax:->let ajax = new XMLHttpRequest;
			2. ajax.open('git','/git?user=xxx')->第二项跟url地址;
			3. ajax.send()->向服务器发送请求；
			4. ajax.onload = function(){}->等待服务器请求
			5. ajax.responseText->请求的结果
**get存在的小问题：**
	在IE下，第二项的url地址信息里如果存在中文字符，那么最安全的写法就是通过URI码转换一下，encodURI（'中文'）

**post：**
1. 相对来说比较安全；
2. 一般用在用户信息、上传（传输一些较大的数据文件）
3. 体积很大（只要服务器支持可以无限大）
4. 后端一般会做一些限制。

		post写法：
			1. 创建一个ajax：->let ajax = new XMLHttpRequest;
			2. ajax.open('post','/post')
			3. ajax.setRequsetHeader('Content-Type','application/x-www-form-urlencoded')->抬头，可以理解为把数据转换成机器所能识别的语言；
			4. ajax.send('user=' + xxxxx)->向服务器发送请求；
			5. ajax.onload = function(){}->等待服务器请求
			6. ajax.responseText->请求的结果。
