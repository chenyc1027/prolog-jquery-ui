### 滑动导航菜单面析组件

组件名称

```
PlgSidebar
```

快速使用

```HTML
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

  
  
  
  
  
  
  </body>
```



