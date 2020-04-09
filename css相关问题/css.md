#### ？问题
    如何实现一个div在父级div中垂直居中？
    文档超出，省略号怎么实现？
    块标签和内嵌标签（或行内标签）区别？都有哪些行标签，哪些块标签，举例？
    怎么消除浮动？
    有哪些选择器？选择器的优先级？

#### 实现元素垂直居中
    1 在父级元素中加入样式
        display:flex;
        justify-content: center;
        align-items: center;
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
        换行会产生间隔
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
        换行会产生间隙
        默认下方会有间隙（避免：vertical-align:top)
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
#### 消除浮动
    
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
            优先级： ！important > id   > class >   tag    >    *
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
             




            


    




