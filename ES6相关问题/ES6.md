#### 带的？，是可能会出现的问题
    ES6 特性，用过哪些？
    有没有用过promise？什么时候用的？
    let const 区别？
    箭头函数和普通函数的区别？
    箭头函数和普通函数中的this指向问题？




### 4 Promise
    异步回调的解决方案
    promise三种状态：pending、fulfilled、rejected（未决定，履行，拒绝），同一时间只能存在一种状态，且状态一旦改变就不能再变。promise是一个构造函数，promise对象代表一项有两种可能结果（成功或是失败）的任务，它还持有多个回调，出现不同结果时分别发出响应回调；
    1 初始化，状态：pending
    2 当调用resolve（成功），状态：pending = >fulfilled
    3 当调用reject（失败），状态：pending = > rejected
    
    

### 3 Template Literals 模板对象/字符串模板
    (超级字符串)
    var m = 'hui'
    var nn = 'ieii'
    var str = `woshishazine${m}${nn}`

### 2 Default Parameters 默认参数
        var lin = function(height = 50 ,color = 'red'){
        // var lin = function(height ,color ){
            // var height = height || 50 ;
            // var color = color || 'red' ;
            console.log(height,color)
        }
        // lin(0,'blue')  50 ， 'blue'
        lin(0,'blue')  //  0 , 'blue'

### 3 箭头函数
        #### 箭头函数和普通函数的区别?
            ##### 箭头函数：
            (1)箭头函数this指向问题，解决了this执行环境所造成的问题
            
            eg:
                var logUpper = function(){
                    var _this = this;
                    this.string = this.string.toUpperCase();
                    return function(){
                        return console.log(_this.string);
                    }
                }
                logUpper.call({string:"ES6 rocks"})();
            <!--用箭头函数的话，可以省略用_this 转换，直接用下面的写法-->
            eg:    
                var logLow = function(){
                    this.str = this.str.toLowerCase();
                    return ()=>{
                        console.log(this.str)
                    }
                }
                logLow.call({str:'heLLo'})()
            (2)书写简洁，可读性好；另外如果在一行中使用箭头函数的话，它就变成了一个表达式，暗地里会返回单个语句，就不需写 return
            ##### 普通函数
            （1）this是在函数执行过程中，自动生成的一个内部对象，是指当前的对象，只有在当前函数内部使用（this对象是在运行时基于函数的执行环境决定：在全局函数中，this指向的是window;当函数被作为某个对象的方法调用时，this就等于那个对象）
            eg:
               var myObject = {
                foo:'bar',
                func:function(){
                    var self = this; // this,self指向的是myObject
                    console.log(`outer this.foo=${this.foo}`);
                    console.log(`outer self.foo=${self.foo}`); 
                    (function(){
                        
                        console.log(`inner this.foo=${this.foo}`);
                        console.log(`inner self.foo=${self.foo}`);
                    }())
                }
            }
            myObject.func()
            // out this.foo= bar
            // out self.foo= bar
            // inner this.foo= undefined
            // out self.foo= bar
            
            
            eg:
             var logLow = function(){
                this.str = this.str.toLowerCase();
                return ()=>{
                    console.log(this.str)
                }
            }
            logLow.call({str:'heLLo'})()
            var b = 10;
            function a(c){
                console.log(this.b);
                console.log(c);
            }
            a(20);// 10 20
            a.call({b:20},30);// 20,30
    
            
            
            
### 1 let var const 区别 ？
    1. var 有变量提升
       let const 没有变量提升
       
    2. const 必须给变量赋予初始值
        var let 可不赋予初始值
    3. const 定义常量，是不可被需改的