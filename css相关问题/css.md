#### ？问题
    如何实现一个div在父级div中垂直居中？
    文档超出，省略号怎么实现？
    块标签和内嵌标签（或行内标签）区别？都有哪些行标签，哪些块标签，举例？
    怎么消除浮动？
    有哪些选择器？选择器的优先级？
    position的属性值？属性值的区别？
    关于盒模型了解多少？
    为什么在写html文件时，需要加文档申明？
#### 实现元素垂直居中
    1 在父级元素中加入样式
        display:flex;
        align-items: center;
    2 同级元素都是内嵌块（inline-block)情况下，会基于同级元素中最高的进行居中，并且每个元素添加vertical-align:middle;
    3 在父级元素添加display:table-cell;转换成单元格。再给父级添加vertical-align:middle;
        让子级在父级里居中，不管子级是块，内嵌还是块内嵌
    4 给父级设置position:relative; 子级设置：position:absolute; top:50%;margin-top:-50%子级的高度；
#### 省略号实现
    overflow:hidden;
    white-space:nowrap;
    text-overflow:ellipsis;

    如果是好几行，希望最后一行出现省略号：
        overflow: hidden;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-box-orient: vertical;
        -webkit-line-clamp:3;(第几行出现省略号，就写几)
#### 块标签和内嵌标签，内嵌块区别
    内嵌标签特点：
        一行显示
        换行会产生间隔(解决：去掉换行或者给父级元素添加样式：font-size:0;)
        不继承文字大小
        不接受宽高，宽高由内容撑开
    块标签特点：
        独占一行
        继承父级的所有样式
        不设置宽度，子级宽度撑满父级
    内嵌块特点：
        一行显示
        支持所有样式
        不设宽高，宽高有内容撑开
        换行会产生间隙（解决：去掉换行或者给父级元素添加样式：font-size:0;)
        默认下方会有间隙（避免：vertical-align:top)
    补充:
        display: block(块)；inline-block(内嵌块)；inline(内嵌)；
#### 举例有哪些块标签，内嵌标签，内嵌块标签
    块标签：
        div  h1~h6 p section header footer  nav aside   article 
        dl  dt  dd  ul  li  ol  li 
    内嵌标签：
        span    a   span    em  strong  mark    time    cite 
    内嵌块：
        img 
    补充：
        h1 用于主题标题（logo)
        h2 用于文本标题（板块标题）
        h3 用于文章中的标题
        h4 h5 h6 加粗
        p 用于文本段落
        section 用于划分板块
        footer 用于包含底部内容
        nav 用于导航栏
        aside 用于附属信息，侧边内容
        article 用于定义文章
        span 不带语义
        em 斜体
        strong 加粗 用于强调
        a 链接
        mark 高亮 自带有黄色
        time 定义时间，不带任何样式
        cite 引用
        img 图片标签，有自带属性。src 图片链接； title 提示信息； alt 当图片不显示时备用文字
            只定义一个方向（宽或高时，图片会等比缩放；定义两个方向时，宽或高可能会变形
        关于标签嵌套需要注意的事项：
            ul里面必须是li
            ol里面必须是li
            dl里面必须是dt dd
            dt里面不嵌套块元素
            内嵌里不嵌套块元素
            a里面不嵌套a
            h1~h6之间不要嵌套块
#### 消除浮动
    1 触发BFC
    2 在想清除浮动的元素（必须为块元素）后加一个div，
        <div class="clearfix"></div>
        .clearfix{ clear: both; }
    3 在需要清除浮动元素的父级添加上一个高度
    4 在需要清除浮动的元素后加上一个br标签，给一个行间属性 <br clear="all">
    5 给需要清除浮动元素的父级加上一个伪类after
        父级:after{ content:''; display:block; clear:both; }
    补充：
        float: left; right ; none(默认，不具有浮动)；
        浮动的特征：
            1 一行显示
            2 脱离文档流
            3 接受宽高设定，不设置宽高情况下由内容撑开
            4 解决margin上下值叠加问题
            5 宽度不够的话，子级元素会折行显示
            6 可控制浮动的方向，直至遇到父级边界或具有浮动的上一个元素
            7 触发BFC
        文档流： 
            从左上角开始，元素在页面中所占的位置
        脱离文档流：
            不在页面中占位置
        脱离文档流导致问题：
            无法撑开父级的高度
        BFC 块级格式化上下文
            Block formatting content
            是一种布局环境，盒子外面的不影响里面的，里面的不影响外面的
            作用：
                1 包含浮动元素，浮动子级元素会参与父级高度的激素
                2 margin传递的问题
                3 不被浮动元素覆盖
            触发BFC
                1 float不为none
                2 overflow 不为visible
                3 display: inline-block; table-cell; table-caption
                4 position: absolute;fixed;
        伪类 before after content
            before 在内部元素的前面加内容
            after 在内部元素的后面加内容
            content 添加内容
        行间属性clear： all;left;right;
        css样式clear: left; right ;both; none(默认)；
            清除指定方向的浮动时，元素会掉下来
            clear只对它前面的元素产生效果

#### 有哪些选择器，以及他们的优先级
    选择器：
        id选择器
        class选择器
        tag 标签选择器
        * 通配符
        优先级：行内样式  > 内部样式  > 外部样式
        包含选择器的优先级是叠加的（id除外）
    css3新增选择器
        伪类选择器
            first-of-type
            last-of-type
            nth-of-type
            first-child
            last-child
            nth-child
            伪类选择器用于标签选择器里：
                eg: .wrap p:first-of-type 找到class为wrap的元素，内部所有的p标签，并且这个p标签是他所在父级  的第一个p
                    .wrap div:first-child 找到class 为wrap的元素，找到他内部所有的div，并且这个div是他所在父级的第一个子元素
            优先级： ！important > style > id   > class >   tag    >    *
        属性选择器
            优先级： class > 属性选择器 > tag
            = 有且只含有一样的属性值
            ~= 词列表且含有一样的
            ^= 第一个字母是一样的
            $= 最后一个字母是一样的
            |= 只为 或以 - 为开头的
            *= 只要含有一样的
        结构选择器
            > 选择到父级下一级的子元素  父级选择器 > 子级选择器
            + 兄弟选择器    选择正好在其后面的同级元素
            ~ 兄弟选择器    是兄弟关系且为~后面的所有同级元素

    补充：
        id选择器：
            命名不可以重复
            开头不能有数字、中文、特殊符号（- _ 除外）
            有语义化
        class选择器：
            命名可以重复
            开头不能有数字、中文、特殊符号（- _ 除外）
            有语义化
            一个标签可用多个class
        * 选中页面中所以元素（一般不用,多用于审查或测试中）
        属性选择器：
            从选择器中筛选出具有这个属性名字的元素
                eg: input[name]
        属性值选择器：
            从选择器中筛选出具有这个属性名称并且属性值为指定值的元素
            =   从选择器中筛选具有这个属性，且属性值为= 一样的元素
            ~=  从选择器中筛选具有这个属性名称，且属性值为词列表，词列表中含有=   的元素
            ^=  从选择器中筛选属性具有这个属性名称，且属性值中以= 的为开头所以的元素
            $=  从选择器中筛选出具有这个属性的元素，且属性值中以=  后面为结尾的所以元素
            *=  从选择器中筛选出具有这个属性的元素，且属性值中有= 后面的所以元素
            |=  从选择器中筛选具有这个属性的元素，且属性值是= 后面的或以 = 后面加上- 为开关的元素
        关于nth-of-type:
            想要选中前3个，在30个中，可以：
                :nth-of-type(-n+3)
            另一个方法：
                :nth-of-type(1)
                :nth-of-type(2)
                :nth-of-type(3)
        伪类：LVHA
            :link 未点击
            :visited 点击过
            :hover 经过
            :active 点击时
#### position属性值，区别
##### 属性值
    relative 相对定位
    absolute 绝对定位
    fixed 固定定位
    static 静态（默认）
    inherit 从父级继承定位属性值（不兼容）
##### 区别
    relative absolute fixed 区别
    relative 使用场景：
        1 不希望当前元素改变位置
        2 提升层级
        3 给父级添加作为absolute定位的根据
        4 left top 不推荐加给relative，它会保留空白区域，也就是不脱离文档流
    relative特性：
        1 只写position是没有任何效果的
        2 在原来位置依旧占位，不脱离文档流
        3 元素加了定位后，层级会提升
         如果两个元素都具备定位，则写在后面的会覆盖前面的
        4 基于原来的位置进行计算定位
    absolute 特性
        1 定位不再基于初始位置（基于document寻找具有定位属性的父级进行定位，找到基于此父级定位，找不到基于document（可视区）定位）
        2 不再占位，脱离文档流
        3 层级在定位后会提升
        4 触发BFC
        5 给内嵌元素加absolute后，是内嵌元素支持宽高
        6 不设置宽度，宽度由内容撑开
    fixed 特性：
        1 不设置宽度，宽度由内容撑开
        2 层级提高
        3 触发BFC
        4 定位分两种，一种未加left，top，基于父级；一种加了left,top,基于可视区域定位


    补充：
        还有margin定位 margin-left  margin-top 
        margin 定位元素离开自己的位置，且元素在原来的位置不占位了
        z-index 层级
            接受正负值 ；数值越大，越在上面；只能加给定位元素；层级比较只针对于同级元素之间
#### 标准盒模型 怪异盒模型
    标准盒模型：
        可视宽高 = content + padding + border
    怪异盒模型
        content = 宽高 - padding - border
#### 文档申明
    文档申明： <! DOCTYPE html>
    如果不加文档申明，在低版本的浏览器中，当前的页面会陷入一个怪异盒模型状态
#### 补充
##### 添加样式的方式，以及其优缺点
    行间样式（在标签中通过style="")
        优点：
            优先级高
        缺点：
            不符合样式行为结构的分离标准
            代码可读性差
            不能复用
    内部样式（在head中添加style，然后通过选择器进行样式与标签的绑定）
        优点：
            代码可读性高
            可以进行单页面的复用
            代码不多余
        缺点：
            不可晋进行多页面的复用
            不利于维护
    外部样式 （通过link标签引入一个.css后缀的文件）
        优点：
            代码可读性高
            可以多页面复用
            利于维护与修改
        缺点：
            优先级低
            增加http请求
            第一次打开页面时会慢，后期会有缓存，打开速度正常
            当前页面下有多余代码

        
             




            


    




