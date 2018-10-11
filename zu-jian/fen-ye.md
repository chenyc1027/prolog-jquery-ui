### 分页组件

> 组件名称

```
PlgPage
```

> 快速使用

```
<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layer/layer.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
<script src="../codebase/PlgPage.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

```
var config = {
renderer: 'test1',
items:[
{text:"战神", type:'warn', size:"big", class: "k-1111"}, // 局部设置size
{text:"战神22", type:'', size:"big", soltPos: 'after', tpl: '<b>多个按钮的插槽<b>'} // 局部设置size
],
type: 'danger',
size: 'big', // 全局设置size
}
var plg = new PlgButton(config5);


plg.on("click", function(ind){
console.log('点击第几个的时候做什么');
console.log('ind::---' + ind);
});
```

方法一：

```
var grid = new PlgPages(config);
```

方法二：
```
var grid = $("#div1").initPlgPages(config);
```
![](/assets/page.png)

> 配置

| 属性 | 说明 | 数据类型 | 默认值 |
| :--- | :--- | :--- | :--- |
| renderer | 挂载点，是id，不需要写\`\#\` | 字符串 | - |
| count | 数据总数。一般通过服务端得到 | Number | - |
| groups | 连续出现的页码个数 | Number |  |
| limit | 每页显示的条数。laypage将会借助 count 和 limit 计算出分页数。 | Number | 10 |
| limits | 每页条数的选择项。如果 layout 参数开启了 limit，则会出现每页条数的select选择框 | Array | \[10, 20, 30, 40, 50\] |
| groups | 连续出现的页码个数 | int | 5 |
| prev | 自定义“上一页”的内容，支持传入普通文本和HTML | String | 上一页 |
| next | 自定义“下一页”的内容，支持传入普通文本和HTML | String | 下一页 |
| first | 自定义“首页”的内容，同上 | String | 1 |
| last | 自定义“尾页”的内容，同上 | String | 总页数值 |
| layout | 自定义排版。可选值有：count（总条目输区域）、prev（上一页区域）、page（分页区域）、next（下一页区域）、limit（条目选项区域）、refresh（页面刷新区域。注意：layui 2.3.0 新增） 、skip（快捷跳页区域） | Array | \['prev', 'page', 'next'\] |
| theme | 自定义主题。支持传入：颜色值，或任意普通字符。如： 1. theme: '\#c00' 2. theme: 'xxx' //将会生成 class="layui-laypage-xxx" 的CSS类，以便自定义主题 | String | - |
| hash | 开启location.hash，并自定义 hash 值。如果开启，在触发分页时，会自动对url追加：\#!hash值={curr} 利用这个，可以在页面载入时就定位到指定页 | String/Boolean | false |
| jump | 获取用户当前点击的分页按钮的页码，是一个函数用来回掉的 | function | - |

```
// 当分页被切换时触发，函数返回两个参数：obj（当前分页的所有选项值）、first（是否首次，一般用于初始加载的判断）
jump: function(obj, first){
if(!first){
layer.msg('第 '+ obj.curr +' 页');
}
}
```



