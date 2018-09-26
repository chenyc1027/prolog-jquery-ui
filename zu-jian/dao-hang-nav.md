## 导航组件

> ```
> 组件名称
> ```

```
PlgNav
```

> 快速使用

```
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>

<script src="../../../modules/layui-master/dist/layui.all.js"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>

<script src="../../../components/PlgNav/codebase/PlgNav.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

```
使用的方法::
var config = {
renderer: 'testDemo',
skin: 'layui-bg-blue', // layui-bg-cyan（藏青）、layui-bg-molv（墨绿）、layui-bg-blue（艳蓝）
items: [
{
name: '藏青导航11',
href: '#',
defatuleSelected: false,
},
{
name: '产品',
href: '#',
defatuleSelected: false,
},
{
name: '大数据',
href: '#',
defatuleSelected: false,
},
{
name: '解决方案',
href: '#',
defatuleSelected: true,
childItems: [
{
name: '移动模块1',
href: '#',
isSelected: true
},
{
name: '移动模块2',
href: '#'
},
{
name: '移动模块2',
href: '#'
}
]
},
{
name: '社区',
href: '#',
defatuleSelected: false,
}
]};

var plg = new PlgNav(config);


方法一：
var grid = new PlgNav(config);
方法二：
var grid = $("div1").initPlgNav(config);
```

![](/assets/nav.png)

> 配置

| 属性 | 说明 | 示例 |
| :--- | :--- | :--- |
| renderer | 挂载点，是id，不需要写\`\#\` | elem |
| skin | 设置nav的颜色，可选参数，【layui-bg-blue】【layui-bg-cyan】【layui-bg-molv】 | 设置全局按钮的颜色 |
| items | 设置菜单的局部参数 | 同上 |
| items\[name\] | 菜单的名称 | 字符串 |
| items\[href\] | c | 同上 |
| items\[defatuleSelected\] | 默认是否选中，选中该文字下面会有小横线 | 同上 |
| items\[childItems\] | 二级菜单 | 同上 |
| items\[childItems\]\[name\] | 菜单的名称 | 同上 |
| items\[childItems\]\[href\] | 菜单的名称 | 同上 |
| items\[childItems\]\[defatuleSelected\] | 默认是否选中，选中该文字下面会有小横线 | 同上 |






