## 面板

> 组件名称

```
PlgPanel
```

> 快速使用

```js
 <link rel="stylesheet" type="text/css" href="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.css"/>
    <link rel="stylesheet" type="text/css" href="../../../modules/dhtmlx/grid/skins/web/dhtmlxgrid.css"/>
    <link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
    <!--全局样式-->
    <link rel="stylesheet" type="text/css" href="../../../globalCss/global_style.css"/>



    <script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../modules/layui-master/dist/layui.all.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>


 <!--PlgPanel组件 JS-->
    <script src="../codebase/PlgPanel.js" type="text/javascript" charset="utf-8"></script>




<body style="background: #fff; ">


      <div id="app"></div>
      <div id="app2" style="margin-top:10px"></div>

       <script  type="text/javascript">

        var config={
            title:"面板标题",
            content:"测试内容",
            style:"width:200px;height:300px"   
            }
    }
        var panel= plgPanel(config).renderTo("#app");
         console.log(panel)

        $("#app2").plgPanel(config);

    </script>

</body>
```

## ![](/assets/panel.png)

## 实例方法

```js
  //方法一
   plgPanel(config).renderTo("#app");

  //方法二

    $("#app2").plgPanel(config);
```

## 基本参数

| 名称 | 类型 | 说明 |
| --- | --- | --- |
| title | string | 面板标题 |
| content | string | 面板内容 |
| style | string | style 样式 |

## 方法

方法 \| 说明 \|  
\| --- \| --- \|  
\|renderTo\("\#id"\)\|渲染节点挂载

