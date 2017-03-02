#指令是什么？

1.简单来说：


 指令: 扩展html标签功能,属性。

 v-model 一般表单元素(input) 双向数据绑定



# **循环:**

```
 v-for="name in arr"

 {{$index}}

 v-for="name in json"

 {{$index}} {{$key}}

 v-for="(k,v) in json"

```

# **事件:**

v-on:click="函数"

v-on:click\/mouseout\/mouseover\/dblclick\/mousedown.....（事件方法名称）

new Vue\({

el:'\#box',

data:{ \/\/数据

arr:\['apple','banana','orange','pear'\],

json:{a:'apple',b:'banana',c:'orange'}

},

methods:{

show:function\(\){ \/\/方法

alert\(1\);

}

}

}\);

# **显示隐藏:**

v-show=“true\/false”

# **事件简写:**

之前：v-on:click="函数"

现在：@click="" 推荐

# **事件对象:**

@click="show\($event\)"

# **事件冒泡:**

阻止冒泡:

a\\). ev.cancelBubble=true;

b\\). @click.stop 推荐

# **键盘:**

@keydown $event ev.keyCode

@keyup

# **常用键:**

回车

a\). @keyup.13

b\). @keyup.enter

# **上、下、左、右**

@keyup\/keydown.left

@keyup\/keydown.right

@keyup\/keydown.up

@keyup\/keydown.down

.....

---

# **属性:**

v-bind:src=""

width\/height\/title....

# **属性简写:**

:src="" 推荐

 效果能出来，但是会报一个404错误

 效果可以出来，不会发404请求

---

# **class和style:**

:class="" v-bind:class=""

:style="" v-bind:style=""

:class="\[red\]" red是数据

:class="\[red,b,c,d\]"

:class="{red:a, blue:false}"

:class="json"

data:{

json:{red:a, blue:false}

}

---

\# style:

:style="\[c\]"

:style="\[c,d\]"

注意: 复合样式，采用驼峰命名法

:style="json"

---

# **模板:**

{{msg}} 数据更新模板变化

{{\*msg}} 数据只绑定一次

{{{msg}}} HTML转意输出

---

# **过滤器:-&gt; 过滤模板数据**

系统提供一些过滤器:

{{msg\| filterA}}

{{msg\| filterA \| filterB}}

uppercase eg: {{'welcome'\| uppercase}}

lowercase

capitalize

currency 钱

{{msg\| filterA 参数}}

....

---

# **交互:**

$http （ajax）

如果vue想做交互

引入: vue-resouce

get:

获取一个普通文本数据:

this.$http.get\('aa.txt'\).then\(function\(res\){

alert\(res.data\);

},function\(res\){

alert\(res.status\);

}\);

# **给服务发送数据:√**

this.$http.get\('get.php',{

a:1,

b:2

}\).then\(function\(res\){

alert\(res.data\);

},function\(res\){

alert\(res.status\);

}\);

post:

this.$http.post\('post.php',{

a:1,

b:20

},{

emulateJSON:true

}\).then\(function\(res\){

alert\(res.data\);

},function\(res\){

alert\(res.status\);

}\);

jsonp:

[https:\/\/sug.so.360.cn\/suggest?callback=suggest\_so&word=a](https://sug.so.360.cn/suggest?callback=suggest_so&word=a)

[https:\/\/sp0.baidu.com\/5a1Fazu8AA54nxGko9WTAnF6hhy\/su?wd=a&cb=jshow](https://sp0.baidu.com/5a1Fazu8AA54nxGko9WTAnF6hhy/su?wd=a&cb=jshow)

this.$http.jsonp\('[https:\/\/sp0.baidu.com\/5a1Fazu8AA54nxGko9WTAnF6hhy\/su',{](https://sp0.baidu.com/5a1Fazu8AA54nxGko9WTAnF6hhy/su',%7B)

wd:'a'

},{

jsonp:'cb' \/\/callback名字，默认名字就是"callback"

}\).then\(function\(res\){

alert\(res.data.s\);

},function\(res\){

alert\(res.status\);

}\);

