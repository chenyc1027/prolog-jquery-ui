### 滑动导航菜单面析组件

> 组件名称

```
PlgSidebar
```

> 快速使用

```js

 <link rel="stylesheet" type="text/css" href="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.css"/>
 <link rel="stylesheet" type="text/css" href="../../../modules/dhtmlx/grid/skins/web/dhtmlxgrid.css"/>
 <link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
 <link rel="stylesheet" type="text/css" href="../../../globalCss/global_style.css"/>
 <script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
 <script src="../../../modules/layui-master/dist/layui.all.js" type="text/javascript" charset="utf-8"></script>
 <script src="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.js" type="text/javascript" charset="utf-8"></script>
 <script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>

 <body>

 <!--PlgSidebar组件css\js-->
 <link rel="stylesheet" type="text/css" href="../codebase/PlgSidebar.css"/>
 <script src="../codebase/PlgSidebar.js" type="text/javascript" charset="utf-8"></script>
 <div id="app"></div>

 <script type="text/javascript">
 var Sidebar= plgSidebar(

 {
 url:"data.json",
 isTrigger:true,
 menuClick:function (data) {
 var mid=data.meneId
 ,othis=data.$this
 ,getData=data.data.mapAll;
 var obj=getData[othis.attr("menu-id")];

 }

 }

 ).renderTo("#app");

 </script>

 </body>

```

![](/assets/001.jpg)

> 构造方法

```js

方法一：

var Sidebar1= plgSidebar(
 {
    url:"data.json",
    menuClick:function (data) {
      data.getCurrent// 获取点击当前数据对象 
 }).renderTo("#app");

方法二：

var Sidebar2=$("#app").plgSidebar(
 {

          url:"data.json",
          menuClick:function (data) {
             data.getCurrent// 获取点击当前数据对象 
        

 }
});

```

> 对象参数

| 配置项 | 类型 | 说明 |
| --- | --- | --- |
| url | string | 数据接口 |
| menClick | Function\(data\) | 点击二级或三级菜单的事件回调;回调参数 data.getCurrent 获取点击当前数据对象 |

> 方法

| 方法 | 说明 |
| --- | --- |
| renderTo\("\#id \|\|.calss"\) | 渲染节点挂载 |

