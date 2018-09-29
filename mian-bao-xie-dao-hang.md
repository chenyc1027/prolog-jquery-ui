### 面包屑导航组件

> 组件名称

```
PlgBreadCrumb
```

> 快速使用

```
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>


<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>


<script src="../../../modules/layer/layer.js" type="text/javascript" charset="utf-8"></script>


<script src="../../../modules/layui-master/dist/layui.js" type="text/javascript" charset="utf-8"></script>


<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>


<script src="../codebase/PlgBreadCrumb.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

方法一：

```
`
``
使用的方法::
<div id="testDemo">

</div>

<script>
var config = {
renderer: 'testDemo',
separator: '', // 分隔符，默认是‘/’
items: [
    {
        name: '藏青导航',
        href: '#'
    },
    {
        name: '产品',
        href: '#'
    },
    {
        name: '大数据',
        href: '#'
    },
    {
        name: '解决方案',
        href: '#'
    },
    {
        name: '社区',
        href: '#'
    }
]
};
```

方法一
```
var plg = new PlgBreadCrumb(config);
```

方法二：

```javascript
var grid = $("#testDemo").initPlgBreadCrumb(config);
```

> 图示

![](/assets/breadCrumb.png)

> 配置

| 属性 | 说明 | 示例 |
| :--- | :--- | :--- |
| elem | 挂载点，是id，不需要写\`\#\` | elem |
|separator | 中间的分割线默认是【/】 | 设置全局按钮的颜色 |
| items | 设置菜单的局部参数 | 同上 |
| items\[name\] | 菜单的名称 | 字符串 |
| items\[href\] | 点击跳转的目的地 | 同上 |