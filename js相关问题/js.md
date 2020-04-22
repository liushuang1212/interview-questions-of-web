#### ? 问题
    this指向
    定时器中this指向？定时器在Vue中应用有没有什么问题？
    数据类型？object为什么是复合数据类型？
    如何检测数据类型？
    关于数据类型转换，字符串和数组如何进行转换？
    undefined和null区别？
    什么时候用==，什么时候用===？
    怎么判断一个对象是{}？ 
    闭包？
    

##### 数据类型
    String Number Boolean Undefined Null（前面五种都是简单或是基本数据类型） Object(复合数据类型)
    Object 为什么是复杂数据类型？
        复合类型是由简单和复合的数据类型组成的。对象是由一对{}包起来的，0对或多对键名和键值组成的对，每对键值对之间用","隔开，最后一个不要加","
    String
        由成对的单引号或者双引号包起来的0个或者多个字符组成的串
    Number 
        -Infinity ~ Infinity 之间
        分为小数（浮点数）和整数
##### 判断一个对象是{}
    1   for(...in...)
        for(var i in obj){
            return true; // 如果不为空，返回true
        } 
        return false; //如果为空，返回false
        JSON.stringify()
        if(JSON.stringify(data) === '{}'){
            return false; //如果为空，返回false
        }
        return true; // 如果不为空，返回true
    3   ES6 新增Object.keys()
        if(Object.keys(object).length === 0 ){
            return false;   // 如果为空，返回false
        }
        return true; //如果不为空，返回true
    4   Object对象的getOwnPropertyNames方法，获取到对象中的属性名，存到一个数组中，返回数组对象，通过判断数组的length来判断此对象是否为空
        let aa = Object.getOwnPropertyNames(a);
        let bb = Object.getOwnPropertyNames(b);
        console.log(aa.length == 0 ); //true 
        console.log(bb.length == 0 ); //false



##### 数据类型检测
    1   typeof 
        返回值是小写的，number,string,function,boolean,undefined,object
    2   
##### 字符串和数组之间相互转换
    1 数组转换成字符串
        1 join
            arr.join("")
        2 
    2 字符串转换成数组
        

##### this 指向
    this js中的关键字，js内部已经定义好
    this的指向问题：
        在函数外部使用，this指向的是window
        在函数内部使用，有名函数，直接调用的话，this指向的是window；通过事件调用，事件是谁触发的，this指向就是谁。
        在函数内部使用，匿名函数，通过事件调用，事件是谁触发的，this指向就是谁
    经常出的题：
        1   var m = 'hola';
            var obj={
                m: "inner",
                ti:function(){
                    var m = 'inTi';
                    // console.log(this.m) // "inner"
                    var timer = setTimeout(function(){
                        console.log(this.m) // "hola"
                    },0)
                    console.log(typeof( timer));
                },
                jian:()=>{
                    var m = 'inJian';
                    // console.log(this.m) // "hola"
                    setTimeout(()=>{
                        console.log(this.m) // "hola"
                    },0)
                }
            }
            obj.ti();
            obj.jian();
##### 运算符 == 与 === 区别
    === 全等
        用于判断数据类型；用于判断数值
    逻辑运算符 &&  ||  ！
    && 与（并且）
        如果左边为真，则返回右边；如果左边为假，则返回左边
    || 或（或者）
        如果左边为真，则返回左边；如果左边为假，则返回右边
    ！否
        将后面的运算符转换成布尔值然后取反
    算术运算符
        + - * / % ++ --
    赋值运算符
        =   +=  -=  *=  /=  %=
        只有在a = a+b 的格式下，才能简写成 a += b
    关系运算符
        >   <   >=  <=  ==  ===     !=  !==
        返回值都是布尔值
    == 判断值是否相等
    ==== 不仅判断值是否相等，还判断数据类型是否一样
    三目运算符
        判断条件 ？ 语句1   ： 语句2
        判断条件成立，执行语句1；判断条件不成立，执行语句2
    
    

##### 补充
    变量命名规范：
        不可以数字开头
        不可以用关键字eg:var , for , name
        不可以用保留字eg: class
    变量命名推荐
        驼峰式命名法 + 语义化单词
        1 小驼峰    getElement 从第二个单词开始，每个字母首字母大写
        2 大驼峰    GetElement 从第一个单词开始，每个字母首字母大写
    js三大组成部分：
        ECMAScript js的语言规范和标准
        DOM
        BOM
    数据类型转换
        把一种数据类型转换成另一种数据类型。js支持将任何一种数据类型转换成这三种数据类型：Number String Boolean
        Number
            Number() 可以将数据转化成数字，返回这个数字，不会改变括号中的数据的类型。
            只有纯粹的数字才可以转换成数字，否则会转成NaN
        String 
            String() 将数据转换成字符串,返回这个字符串，但是不会把括号中的数据类型改变，
            数据转成字符串简单方法：  "" + 数据
        Boolean
            Boolean() 将数据转变成布尔值，并返回这个布尔值，但不会改变括号内数据的类型
            undefined ，null ，空字符串（长度为0），0，NaN 会转成 false；其余的会转成true
            数据转成布尔值简单方法： !!数据
        parseInt 
            将数据转成整数，舍去小数位，取整数
        parseFloat
            将数据转变成小数（浮点数）
    显式类型转换
        使用一些方法使数据类型发生改变
        eg:Number(), parseInt(), parseFloat(), String(), Boolean()
    隐式类型转换
        不调用方法使数据的类型发生改变
        eg: "" + 数据 （将数据转化成字符串）     !!2 (将数据转化成布尔值)
##### 拓展
###### 对象的遍历
			
		for(var a in obj){
				console.log(obj[a]) //a为obj的键名，obj为对象，打出的是键值
				console.log(a) //打出的是键名
		}


###### NaN
    NaN 
        不是数字
        用于检测一个数值是不是NaN
        NaN 和任何数组都不相等，也不等于它自己
        isNaN() 方法用于判断是不是NaN。使用时，先用Number()进行转换，然后再进行判断是不是NaN
    !!| 将|变成布尔值为true

##### undefined null 区别
    undefined
        当一个变量被定义，但是未被赋值时会出现undefined
        typeof（undefined) ,是一个undefined
    null
        值只有一个null，是一个对象
        typeof(null) ,是一个对象
    按规定null == undefined ,但是null !== undefined
##### 闭包
    是指有权访问另一个函数作用域的变量的函数
##### 定时器
    setInterval
        间隔型定时器    每隔一段时间执行一段代码，代码一般会重复执行
        语法    setInterval(函数，时间间隔) setInterval(fn,20) 每隔20毫秒执行函数fn
        定时器开启的时候，内部执行的函数不是立即执行的，要等待第一次时间间隔
    
    clearInterval
        清除定时器
        定期器开启的时候会返回一个数值作为这个定时器的编号
        关闭定时器， clearInterval(定时器的编号)    当开启定时器时将返回的编号存储到变量中，清除时，只需要找到这个变量就可以了。

    setTimeout()
        延迟性定时器，  每隔一段时间执行一段代码（只执行一次）
        语法    setTimeout(函数，时间间隔)  setInterval(fn, 20) 等待20ms执行一段函数

    clearTimeout
    当我们需要隔一段时间再执行一段代码，或者每隔一段时间执行一段代码的时候，需要使用定时器

    关于定时器中this问题：
        在setInterval和setTimeout中传入函数时，函数中的this会指向window对象
        在setTimeout()调用的代码运行与所在函数完全分离的执行环境上，这回导致这些代码中包含的this关键字会指向window（或全局）对象；
    如何解决定时器中this指向问题：
        1 将当前对象的this存为一个变量，定时器内的函数利用闭包来访问这个变量
            var num = 0;
            function Obj(){
                var that = this;
                this.num = 1;
                this.getNum = function(){
                    console.log(this.num);
                }
                this.getNumLater = function(){
                    setTimeout(function(){
                        console.log(that.num); // 利用闭包访问that，that是伊特指向obj的指针
                    },1000)
                }
            }
            var obj = new Obj;
            obj.getNum();   // 1
            obj.getNumLater(); //1

