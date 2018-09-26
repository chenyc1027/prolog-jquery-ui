### 弹出框

组件名称

```
PlgDialog
```

快速使用

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

  <body>





  </body>
```

![](/assets/001.jpg)

构造方法

```js
方法一：
var Sidebar1= plgSidebar(
        {
            url:"data.json",  
            menuClick:function (data) {
                var mid=data.meneId
                    ,othis=data.$this
                    ,getData=data.data.mapAll;

                var obj=getData[othis.attr("menu-id")];

            }
        }
    ).renderTo("#app");

方法二：
var Sidebar2=$("#app").plgSidebar(
        {
            url:"data.json", 
            menuClick:function (data) {
                var mid=data.meneId
                    ,othis=data.$this
                    ,getData=data.data.mapAll;
                var obj=getData[othis.attr("menu-id")];

            }
        }

    );
```



> 配置


| 配置项 | 类型 | 说明 |
| --- | --- | --- |
| url | string | 数据接口 |
| menClick | Function\(data\) | 点击二级或三级菜单的事件回调;回调参数data:{meneId:string,$this:object,data:objec } |

> 方法

| 方法 | 说明 |
| --- | --- |
|renderTo("#id \|\|.calss")|渲染节点挂载





