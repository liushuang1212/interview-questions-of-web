#### BOM
    BOM browser model 浏览器对象模型，处理浏览器的方法和接口
	是关于浏览器的方法，属性和事件

##### window.open()
	
	1 指定要打开的页面地址
		window.open('http://www.baidu.com')
		如果不写http,代表打开的是本地地址，eg: window.open('pleaseOpenMe.html')
	2 打开的方式
		_blank	在新页面打开网页
		_self	在当前页面打开网页	eg:window.open('pleaseOpenMe.html','_self')
	3 设置浏览器的窗口特性（宽，高，位置等）
		当设置第三个参数时，第二个参数必须是“_blank”
		window.open('pleaseOpenMe.html','_blank','width=300px,height=100px')
	4 不传参数的话，打开的是空白页面
		默认打开的是新的页面
		返回值是打开的新窗口
##### window.close()
	chrome 可以关闭自身
	Firefox（当前版本下）只能关闭由open打开的窗口，不能关闭自身
##### window.navigator.userAgent
	用户代理信息
	操作系统， 浏览器内核 浏览器版本等
##### window.location.href
	字符串版的地址栏信息
##### window.location.search
	地址栏查询信息（问号到#号之间的所有内容）
	可以读，写，但是为search赋值时会刷新页面
	注意：设置search，最好通过事件来实现（比如加在点击事件中）
##### window.location.hash 
	锚点信息（#号后面的所有内容)
	可以读写
	为hash赋值，不会刷新页面
##### window.onhashchange
	onhashchange 事件在当前 URL 的锚部分(以 '#' 号为开始) 发生改变时触发
		
		