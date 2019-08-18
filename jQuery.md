#jQuery编程笔记

##配置
> 两个方式表示 jQuery
$ == jQuery 
> 释放/重命名 $
i = $.noConflict()

##选择器(css)
> 转换成jQuery对象 $(str)
> 获取节点列表 $(selector) 没有匹配的返回undefind 对其操作不会报错
> 获取单个节点 [] / .get() / .first() /.last() / .slice()
> 查找节点 向下.find() 向上.parent() 兄弟.next() .prev()
> 过滤节点 .filter(selector/fn) .map(fn)

###表单特殊选择器
> :input -> input/textarea/select/button 
> :file -> input[type=file]
> :checkbox -> input[type=checkbox]
> :radio -> input[type=radio]
> 伪元素 -> :focus/:checked/:enabled/:disabled

###DOM操作
> .text() .html 无参数获取，有参数赋值
> .css() 同上，两个参数。 background-color == backgroundColor
> .hasClass() .addClass() .removeClass() -> classList.add/has/remove
> .show() .hide() 对display操作，会还原display的原始值

###DOM属性
> $(window).height() /width() 
> $(document).height() /width() 
> $('div').height()/width() 有参数设置 '900px'==900

####页面结构
> .append(str/create/$/fn) 添加到尾部，已有DOM则移动 => .innerHtml+='xxx' fn对$列表操作
> .prepend() 与append对应，添加到头部
> .after()/.before() 同级，添加到后面
> .remove() 删除节点

####Attr属性
> .attr() 获取属性，第二个参数添加属性
> .removeAttr() 删除属性 == .attr('class','')
> .prop() 获取属性，与attr略为不同 -> .prop('checked') 返回 true/false

####表单操作
> .is() 是否选中.is(':checked') 返回true/false
> .val() 获取值，赋值 -> 统一各种情况的值



