## 弹出框

> 组件名称

```
PlgDialog
```

> 快速使用

```js
<link rel="stylesheet" type="text/css" href="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.css" />
<link rel="stylesheet" type="text/css" href="../../../modules/dhtmlx/grid/skins/web/dhtmlxgrid.css" />
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css" />
<!--全局样式-->
<link rel="stylesheet" type="text/css" href="../../../globalCss/global_style.css" />

<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layui-master/dist/layui.all.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>



<!--PlgDialog组件 JS-->
<script src="../codebase/plgDialog.js" type="text/javascript" charset="utf-8"></script>

<body style="background: #fff; ">


<div style="padding: 20px">


<button id="dom_01" class="layui-btn">询问框</button>
<button id="dom_02" class="layui-btn">消息层</button>
<button id="dom_03" class="layui-btn">自定页</button>
<button id="dom_04" class="layui-btn">tab页</button>
<button id="dom_05" class="layui-btn">loadn层</button>
<button id="dom_06" class="layui-btn">tips</button>
</div>

<script type="text/javascript">

plgDialog.ready(function () {
plgDialog.msg('很高兴一开场就见到你');
});

//询问框
document.querySelector("#dom_01").onclick = function () {
console.dir(plgDialog);
//询问框
plgDialog.confirm(`是否删除吗？`, {
title: '删除提示',
btn: ['确定', '取消']
}, function (index) {
plgDialog.close(index)

});

}

//消息层
document.querySelector("#dom_02").onclick = function () {
plgDialog.msg('我是消息层');

}

document.querySelector("#dom_03").onclick = function () {
plgDialog.open({
title: '自定页',
shadeClose: true,
area: ['640px', '480px'],
content: `<div >这里存放HTml内容</div>`, //iframe的url
yes: function (index, layero) {

plgDialog.close(index); //如果设定了yes回调，需进行手工关闭

},
success: function (layero, index) {
//当你需要在层创建完毕时即执行一些语句，可以通过该回调。success会携带两个参数，分别是当前层DOM当前层索引。如：
console.log(layero, index);

}
})

}

//自定页
document.querySelector("#dom_03").onclick = function () {
plgDialog.open({
title: '自定页',
shadeClose: true,
area: ['640px', '480px'],
content: `<div >这里存放HTml内容</div>`, //iframe的url
yes: function (index, layero) {

plgDialog.close(index); //如果设定了yes回调，需进行手工关闭

},
success: function (layero, index) {
//当你需要在层创建完毕时即执行一些语句，可以通过该回调。success会携带两个参数，分别是当前层DOM当前层索引。如：
console.log(layero, index);

}
})

}

//tab页
document.querySelector("#dom_04").onclick = function () {
plgDialog.tab({
area: ['600px', '300px'],
tab: [{
title: 'TAB1',
content: '内容1'
}, {
title: 'TAB2',
content: '内容2'
}, {
title: 'TAB3',
content: '内容3'
}]
});

}

//loading加载
document.querySelector("#dom_05").onclick = function () {

plgDialog.loading(); //0代表加载的风格，支持0-2
//1秒后自动关闭加载层
setTimeout(function () {
plgDialog.closeAll("loading")
}, 1000)


}
// tips提示层
document.querySelector("#dom_06").onclick = function () {

plgDialog.tips('默认就是向右的', this);

}


</script>


</body>
```

> # 基础参数

### type - 基本层类型

> 类型：Number，默认：0

plgDialog提供了5种层类型。可传入的值有：0（信息框，默认）1（页面层）2（iframe层）3（加载层）4（tips层）。 若你采用layer.open\({type: 1}\)方式调用，则type为必填项（信息框除外）

###  title - 标题

> 类型：String/Array/Boolean，默认：'信息'

title支持三种类型的值，若你传入的是普通的字符串，如title :'我是标题'，那么只会改变标题文本；若你还需要自定义标题区域样式，那么你可以title: \['文本', 'font-size:18px;'\]，数组第二项可以写任意css样式；如果你不想显示标题栏，你可以title: false

### content - 内容

> 类型：String/DOM/Array，默认：''

content可传入的值是灵活多变的，不仅可以传入普通的html内容，还可以指定DOM，更可以随着type的不同而不同。

### area - 宽高

>类型：String/Array，默认：'auto'

在默认状态下，layer是宽高都自适应的，但当你只想定义宽度时，你可以area: '500px'，高度仍然是自适应的。当你宽高都要定义时，你可以area: \['500px', '300px'\]

### btn - 按钮

>类型：String/Array，默认：'确认'

信息框模式时，btn默认是一个确认按钮，其它层类型则默认不显示，加载层和tips层则无效。当您只想自定义一个按钮时，你可以btn: '我知道了'，当你要定义两个按钮时，你可以btn: \['yes', 'no'\]。当然，你也可以定义更多按钮，比如：btn: \['按钮1', '按钮2', '按钮3', …\]，按钮1的回调是yes，而从按钮2开始，则回调为btn2: function\(\){}，以此类推。如：

```js
layer.confirm('纳尼？', {
btn: ['按钮一', '按钮二', '按钮三'] //可以无限个按钮
,btn3: function(index, layero){
//按钮【按钮三】的回调
}
}, function(index, layero){
//按钮【按钮一】的回调
}, function(index){
//按钮【按钮二】的回调
});
//eg2
layer.open({
content: 'test'
,btn: ['按钮一', '按钮二', '按钮三']
,yes: function(index, layero){
//按钮【按钮一】的回调
}
,btn2: function(index, layero){
//按钮【按钮二】的回调
//return false 开启该代码可禁止点击该按钮关闭
}
,btn3: function(index, layero){
//按钮【按钮三】的回调
//return false 开启该代码可禁止点击该按钮关闭
}
,cancel: function(){
//右上角关闭回调
//return false 开启该代码可禁止点击该按钮关闭
}
});
```

### btnAlign - 按钮排列

>类型：String，默认：r

你可以快捷定义按钮的排列位置，btnAlign的默认值为r，即右对齐。该参数可支持的赋值如下：

| 值 | 备注 |
| --- | --- |
| btnAlign: 'l' | 按钮左对齐 |
| btnAlign: 'c' | 按钮居中对齐 |
| btnAlign: 'r' | 按钮右对齐。默认值，不用设置 |

### closeBtn - 关闭按钮

>类型：String/Boolean，默认：1

layer提供了两种风格的关闭按钮，可通过配置1和2来展示，如果不显示，则closeBtn: 0

### shade - 遮罩

>类型：String/Array/Boolean，默认：0.3

即弹层外区域。默认是0.3透明度的黑色背景（'\#000'）。如果你想定义别的颜色，可以shade: \[0.8, '\#393D49'\]；如果你不想显示遮罩，可以shade: 0

### shadeClose - 是否点击遮罩关闭

>类型：Boolean，默认：false

如果你的shade是存在的，那么你可以设定shadeClose来控制点击弹层外区域关闭。

### time - 自动关闭所需毫秒

>类型：Number，默认：0

默认不会自动关闭。当你想自动关闭时，可以time: 5000，即代表5秒后自动关闭，注意单位是毫秒（1秒=1000毫秒）

### id - 用于控制弹层唯一标识

>类型：String，默认：空字符

设置该值后，不管是什么类型的层，都只允许同时弹出一个。一般用于页面层和iframe层模式

### maxmin - 最大最小化。

>类型：Boolean，默认：false

该参数值对type:1和type:2有效。默认不显示最大小化按钮。需要显示配置maxmin: true即可

### fixed - 固定

>类型：Boolean，默认：true

即鼠标滚动时，层是否固定在可视区域。如果不想，设置fixed: false即可

## resize - 是否允许拉伸

>类型：Boolean，默认：true

默认情况下，你可以在弹层右下角拖动来拉伸尺寸。如果对指定的弹层屏蔽该功能，设置 false即可。该参数对loading、tips层无效

### resizing - 监听窗口拉伸动作

>类型：Function，默认：null

当你拖拽弹层右下角对窗体进行尺寸调整时，如果你设定了该回调，则会执行。回调返回一个参数：当前层的DOM对象  
scrollbar - 是否允许浏览器出现滚动条  
类型：Boolean，默认：true

默认允许浏览器滚动，如果设定scrollbar: false，则屏蔽

### maxWidth - 最大宽度

>类型：Number，默认：360

请注意：只有当area: 'auto'时，maxWidth的设定才有效。

## maxHeight - 最大高度

>类型：Number，默认：无

请注意：只有当高度自适应时，maxHeight的设定才有效。

### zIndex - 层叠顺序

>类型：，默认：19891014（贤心生日 0.0）

一般用于解决和其它组件的层叠冲突。

### move - 触发拖动的元素

类型：String/DOM/Boolean，默认：'.layui-layer-title'

默认是触发标题区域拖拽。如果你想单独定义，指向元素的选择器或者DOM即可。如move: '.mine-move'。你还配置设定move: false来禁止拖拽

### moveOut - 是否允许拖拽到窗口外

>类型：Boolean，默认：false

默认只能在窗口内拖拽，如果你想让拖到窗外，那么设定moveOut: true即可

### moveEnd - 拖动完毕后的回调方法

>类型：Function，默认：null

默认不会触发moveEnd，如果你需要，设定moveEnd: function\(layero\){}即可。其中layero为当前层的DOM对象

tips - tips方向和颜色  
类型：Number/Array，默认：2

tips层的私有参数。支持上右下左四个方向，通过1-4进行方向设定。如tips: 3则表示在元素的下面出现。有时你还可能会定义一些颜色，可以设定tips: \[1, '\#c00'\]

### tipsMore - 是否允许多个tips

>类型：Boolean，默认：false

允许多个意味着不会销毁之前的tips层。通过tipsMore: true开启

### success - 层弹出后的成功回调方法

>类型：Function，默认：null

当你需要在层创建完毕时即执行一些语句，可以通过该回调。success会携带两个参数，分别是当前层DOM当前层索引。如：

```js
plgDialog.open({
content: '测试回调',
success: function(layero, index){
console.log(layero, index);
}
});
```

### yes - 确定按钮回调方法

>类型：Function，默认：null

该回调携带两个参数，分别为当前层索引、当前层DOM对象。如：

```js
plgDialog.open({
content: '测试回调',
yes: function(index, layero){
//do something
plgDialog.close(index); //如果设定了yes回调，需进行手工关闭
}
});
```

### cancel

cancel - 右上角关闭按钮触发的回调  
>类型：Function，默认：null

该回调携带两个参数，分别为：当前层索引参数（index）、当前层的DOM对象（layero），默认会自动触发关闭。如果不想关闭，return false即可，如；

```js
cancel: function(index, layero){
if(confirm('确定要关闭么')){ //只有当点击confirm框的确定时，该层才会关闭
plgDialog.close(index)
}
return false;
}
```

## end - 层销毁后触发的回调

>类型：Function，默认：null

无论是确认还是取消，只要层被销毁了，end都会执行，不携带任何参数。

> # 实例方法

## plgDialog.ready\(callback\) - 初始化就绪

由于我们的plgDialog内置了轻量级加载器，所以你根本不需要单独引入css等文件。但是加载总是需要过程的。当你在页面一打开就要执行弹层时，你最好是将弹层放入ready方法中，如：

```js
//页面一打开就执行弹层
plgDialog.ready(function(){
plgDialog.msg('很高兴一开场就见到你');
});
```

## plgDialog.open\(options\) - 原始核心方法

基本上是露脸率最高的方法，不管是使用哪种方式创建层，都是走plgDialog.open\(\)，创建任何类型的弹层都会返回一个当前层索引，上述的options即是基础参数，另外，该文档统一采用options作为基础参数的标识例子：

```js
var index = plgDialog.open({
content: 'test'
});
//拿到的index是一个重要的凭据，它是诸如plgDialog.close(index)等方法的必传参数。
```

## plgDialog.alert\(content, options, yes\) - 普通信息框

它的弹出似乎显得有些高调，一般用于对用户造成比较强烈的关注，类似系统alert，但却比alert更灵便。它的参数是自动向左补齐的。通过第二个参数，可以设定各种你所需要的基础参数，但如果你不需要的话，直接写回调即可。如

```js
//eg1
plgDialog.alert('只想简单的提示');
//eg2
plgDialog.alert('加了个图标', {icon: 1}); //这时如果你也还想执行yes回调，可以放在第三个参数中。
//eg3
plgDialog.alert('有了回调', function(index){
//do something
plgDialog.close(index);
});
```

## plgDialog.msg\(content, options, end\) - 提示框

我们在源码中用了相对较大的篇幅来定制了这个msg，目的是想将其打造成露脸率最高的提示框。而事实上我的确也在大量地使用它。因为它简单，而且足够得自觉，它不仅占据很少的面积，而且默认还会3秒后自动消失所有这一切都决定了我对msg的爱。因此我赋予了它许多可能在外形方面，它坚持简陋的变化，在作用方面，它坚持零用户操作。而且它的参数也是自动补齐的。

```js
//eg1
plgDialog.msg('只想弱弱提示');
//eg2
plgDialog.msg('有表情地提示', {icon: 6});
//eg3
plgDialog.msg('关闭后想做些什么', function(){
//do something
});
//eg
plgDialog.msg('同上', {
icon: 1,
time: 2000 //2秒关闭（如果不配置，默认是3秒）
}, function(){
//do something
});
```

## plgDialog.confirm\(content, options, yes, cancel\) - 询问框

类似系统confirm，但却远胜confirm，另外它不是和系统的confirm一样阻塞你需要把交互的语句放在回调体中。同样的，它的参数也是自动补齐的。

```js
//eg1
plgDialog.confirm('is not?', {icon: 3, title:'提示'}, function(index){
//do something
plgDialog.close(index);
});
//eg2
plgDialog.confirm('is not?', function(index){
//do something
plgDialog.close(index);
});
```

## plgDialog.load\(icon, options\) - 加载层

load并不需要你传太多的参数，但如果你不喜欢默认的加载风格，你还有选择空间。icon支持传入0-2如果是0，无需传。另外特别注意一点：load默认是不会自动关闭的，因为你一般会在ajax回调体中关闭它。

```js
//eg1
var index = plgDialog.load();
//eg2
var index = plgDialog.load(1); //换了种风格
//eg3
var index = plgDialog.load(2, {time: 10*1000}); //又换了种风格，并且设定最长等待10秒
//关闭
plgDialog.close(index);
```

## plgDialog.tips\(content, follow, options\) - tips吸附层

它拥有和msg一样的低调和自觉，而且会智能定位，即灵活地判断它应该出现在哪边。默认是在元素右边弹出

```js
//eg1
plgDialog.tips('只想提示地精准些', '#id');
//eg 2
$('#id').on('click', function(){
var that = this;
plgDialog.tips('只想提示地精准些', that); //在元素的事件回调体中，follow直接赋予this即可
});
//eg 3
plgDialog.tips('在上面', '#id', {
tips: 1
});
```

## plgDialog.close\(index\) - 关闭特定层

关于它似乎没有太多介绍的必要，唯一让你疑惑的，可能就是这个index了吧。事实上它非常容易得到。

```js
//当你想关闭当前页的某个层时
var index = plgDialog.open();
var index = plgDialog.alert();
var index = plgDialog.load();
var index = plgDialog.tips();
//正如你看到的，每一种弹层调用方式，都会返回一个index
plgDialog.close(index); //此时你只需要把获得的index，轻轻地赋予plgDialog.close即可
//如果你想关闭最新弹出的层，直接获取plgDialog.index即可
plgDialog.close(plgDialog.index); //它获取的始终是最新弹出的某个层，值是由layer内部动态递增计算的
```

## plgDialog.closeAll\(type\) - 关闭所有层

如果你很懒，你不想去获取index你只想关闭。那么closeAll真的可以帮上你。如果你不指向层类型的话，它会销毁掉当前页所有的plgDialog层。当然，如果你只想关闭某个类型的层，那么你可以

```js
plgDialog.closeAll(); //疯狂模式，关闭所有层
plgDialog.closeAll('dialog'); //关闭信息框
plgDialog.closeAll('page'); //关闭所有页面层
plgDialog.closeAll('iframe'); //关闭所有的iframe层
plgDialog.closeAll('loading'); //关闭加载层
plgDialog.closeAll('tips'); //关闭所有的tips层
```

## plgDialog.style\(index, cssStyle\) - 重新定义层的样式

该方法对loading层和tips层无效。参数index为层的索引，cssStyle允许你传入任意的css属性

```js
//重新给指定层设定width、top等
plgDialog.style(index, {
width: '1000px',
top: '10px'
});
```

## plgDialog.setTop\(layero\) -置顶当前窗口

非常强大的一个方法，虽然一般很少用。但是当你的页面有很多很多layer窗口，你需要像Window窗体那样，点击某个窗口，该窗体就置顶在上面，那么setTop可以来轻松实现。它采用巧妙的逻辑，以使这种置顶的性能达到最优

```js
//通过这种方式弹出的层，每当它被选择，就会置顶。
plgDialog.open({
type: 2,
shade: false,
area: '500px',
maxmin: true,
content: 'http://www.layui.com',
zIndex: layer.zIndex, //重点1
success: function(layero){
plgDialog.setTop(layero); //重点2
}
});
```

## plgDialog.prompt\(options, yes\) - 输入层

prompt的参数也是向前补齐的。options不仅可支持传入基础参数，还可以传入prompt专用的属性。当然，也可以不传。yes携带value 表单值index 索引elem 表单元素

```js
//prompt层新定制的成员如下
{
formType: 1, //输入框类型，支持0（文本）默认1（密码）2（多行文本）
value: '', //初始时的值，默认空字符
maxlength: 140, //可输入文本的最大长度，默认500
}
//例子1
plgDialog.prompt(function(value, index, elem){
alert(value); //得到value
plgDialog.close(index);
});
//例子2
plgDialog.prompt({
formType: 2,
value: '初始值',
title: '请输入值',
area: ['800px', '350px'] //自定义文本域宽高
}, function(value, index, elem){
alert(value); //得到value
plgDialog.close(index);
});
```

## plgDialog.tab\(options\) - tab层

tab层只单独定制了一个成员，即tab: \[\]，这个好像没有什么可介绍的，简单粗暴看例子

```js
plgDialog.tab({
area: ['600px', '300px'],
tab: [{
title: 'TAB1',
content: '内容1'
}, {
title: 'TAB2',
content: '内容2'
}, {
title: 'TAB3',
content: '内容3'
}]
});
```

## plgDialog.photos\(options\) - 相册层

这个用的不多，就不介绍了

