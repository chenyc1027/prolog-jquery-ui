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

```
使用的方法::
    <div id="test"></div>
    <div id="test1"></div>
    <script>
        var config = {
            renderer: 'test',
            separator: '',  // 分隔符，默认是‘/’ 
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
            ]};

        var plg = new PlgBreadCrumb(config);


        var config1 = {
            renderer: 'test1',
            separator: '--',  // 分隔符，默认是‘/’ 
            items: [
                {
                    name: '藏青导航111',
                    href: '#'
                },
                {
                    name: '产品111',
                    href: '#'
                },
                {
                    name: '大数据111',
                    href: '#'
                },
                {
                    name: '解决方案111',
                    href: '#'
                },
                {
                    name: '社区111',
                    href: '#'
                }
            ]};

        var plg1 = $('#test1').initPlgBreadCrumb(config1);
      </script>
```

方法一

```
var plg = new PlgBreadCrumb(config);
```

方法二：

```
var grid = $("#testDemo").initPlgBreadCrumb(config);
```

> 图示

![](/assets/breadCrumb.png)

> 配置

| 属性 | 说明 | 类型 | 默认值 |
| :--- | :--- | :--- | :--- |
| elem | 挂载点，是id，不需要写\`\#\` | String | id |
| separator | 中间的分割线默认是【/】 | String | / |
| items | 设置菜单的局部参数 | ArrayObject |  |
| items\[name\] | 菜单的名称 | String | - |
| items\[href\] | 点击跳转的目的地 | String | - |



