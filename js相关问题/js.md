#### ? 问题
    this指向
    数据类型？object为什么是复合数据类型？
    如何检测数据类型？
    关于数据类型转换，字符串和数组如何进行转换？

##### 数据类型
    String Number Boolean Undefined Null（前面五种都是简单或是基本数据类型） Object(复合数据类型)
    Object 为什么是复杂数据类型？
        复合类型是由简单和复合的数据类型组成的。对象是由一对{}包起来的，0对或多对键名和键值组成的对，每对键值对之间用","隔开，最后一个不要加","

##### 数据类型检测
    1 typeof 
        返回值是小写的，number,string,function,boolean,undefined,object
    2 
##### 字符串和数组之间相互转换
    1 数组转换成字符串
        1 join
            arr.join("")
    2 字符串转换成数组
        
#### this 指向
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
            可以将数据转化成数字，返回这个数字，不会改变括号中的数据的类型。
            只有纯粹的数字才可以转换成数字，否则会转成NaN
        String 
            将数据转换成字符串