#### 问题
    vue如何自定义一个过滤器？
##### vue自定义一个过滤器

    html代码：

        <div id="app">
            <input type="text" v-model="msg" />
            {{msg| capitalize }}
        </div>
    JS代码：

        var vm=new Vue({
            el:"#app",
            data:{
                msg:''
            },
            filters: {
            capitalize: function (value) {
                if (!value) return ''
                value = value.toString()
                return value.charAt(0).toUpperCase() + value.slice(1)
            }
            }
        })
        全局定义过滤器

        Vue.filter('capitalize', function (value) {
        if (!value) return ''
        value = value.toString()
        return value.charAt(0).toUpperCase() + value.slice(1)
        })
        过滤器接收表达式的值 (msg) 作为第一个参数。capitalize 过滤器将会收到 msg的值作为第一个参数。