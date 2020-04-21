##### DOM
    DOM document object model 文档对象模型，处理网页内容的方法和接口
	常用节点类型
		元素节点 1
		属性节点 2
		文本节点 3
		注释节点 8
		文档节点 9
	查看节点类型
		node.nodeType (返回的是数字)
	元素节点
		元素.nodeType
		元素.nodeName
	属性节点
		元素.attributes 获取的是集合
		元素.attributes[0]
	文本节点
	注释节点
		通过元素.childNodes 获取子节点
	文档节点
		document
	父节点
		定位父级
		offsetLeft  offsetTop 到定位父级几点的距离
		node.offset Parent 
		offsetParent 定位父级 	会查找该node的定位父级：
			首先如果父级有定位（position属性不为static），则定位父级就是父级节点，如果父级没有定位，则继续寻找父级的父级，一层一层往上找，如果都没有定位父级，则找到body为止
		getBoundingClientRect() 到可视区，获取元素身上的属性是一个方法
			left 元素左边界到可视区左侧距离
			top 元素上边界到可视区上侧距离
			right	元素右边界到可视区左侧距离
			bottom 元素下边界到可视区上侧距离
		getBoundingClientRect().left
		自定义属性
			元素行间的自定义属性不能通过.和[]获取，可以通getAttribute('')获取
			setAttribute(''，0) 添加自定义属性， 2个参数, 自定义属性名字， 自定义属性的值
			removeAttribute('') 删除自定义属性的名称，删除自定义属性，
		getElementsByTagame	是动态获取元素的，实时更新
		document.createElement('')返回值是你创建出的div元素
		appentChild 插入元素
			如果插入的是已有节点（DOM中存在的），则会做剪切操作
			parentNode.appendChild.childNode
			父节点（需要放入到哪个节点里） 子节点（需要被放入的节点）
		insertBefore
			2个参数
			如果没有第二个参数，会报错
			如果第二个参数是Null，则相当于appendChild
			
			parentNode.insertBefore( childNode1, childNode2 ) 把1插入到2前面
		removeChild 从一个节点中删除一个节点
			parentNode.removeChild(childNodes)
			返回值是删除的节点
		replaceChild
			parentNode.replaceChild(Node,childNode)
			Node 替换的节点
			childNode 被替换的节点
		replaceChild 2个参数，如果只写一个参数，会报错
		cloneNode
			node.cloneNode(boolean)
			boolean: 是否深度克隆
				true：深度克隆
				false：
				boolean 不写的话，默认false
				
		
		
		
		
			
			
	
    