### 选项卡

> 组件名称

```
PlgTabs
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



    <!--PlgSidebar组件 JS-->
    <script src="../codebase/PlgTabs.js" type="text/javascript" charset="utf-8"></script>

<body style="background: #fff; ">


        <div style="padding: 20px">
             <div id="app"></div>
            <div id="app2"> </div>
            <div id="app3"></div>
        </div>
       <script  type="text/javascript">

    var config={
        filter:"add",//过滤选择器
        indexActive:0,//初始化默认选中项
        skin:"brief",
        allowClose:true,
        content:[
          {
              title:"网站设置1",
              layId:"1",
              template:`<div>我是网站设置1的内容</div>`

          },
          {
              title:"商品管理1",
              layId:"2",
              template:`<div>我是商品管理1的内容</div>`

          },
          {
              title:"订单管理1",
              layId:"3",
              template:`<div>我是订单管理1的内容</div>`
          },

         ]
    };
    var config2=
        {
        indexActive:0,//初始化默认选中项
        skin:"normal",
        content:[
            {
                title:"网站设置2",
                template:`<div>我是网站设置2的内容</div>`
            },
            {
                title:"商品管理2",
                template:`<div>我是商品管理2的内容</div>`
            },
            {
                title:"订单管理2",
                template:`<div>我是订单管理2的内容</div>`
            },
        ]
    };
    var config3=
        {
            indexActive:0,//初始化默认选中项
            skin:"card",
            content:[
                {
                    title:"网站设置3",
                    template:`<div>我是网站设置3的内容</div>`
                },
                {
                    title:"商品管理3",
                    template:`<div>我是商品管理3的内容</div>`
                },
                {
                    title:"订单管理3",
                    template:`<div>我是订单管理3的内容</div>`
                },
            ]
        };


    var tabs=plgTabs(config).renderTo("#app");
    console.log(tabs);

    tabs.on(function (ele) {
        console.log(ele)

    });


    var tabs2=plgTabs(config2).renderTo("#app2").on(function (ele) {
        console.log(this)

    });


    console.log(tabs2);

    var tabs3=$("#app3").plgTabs(config3).renderTo("#app3").on(function (ele) {
        console.log(this)

    });
    console.log(tabs3);





</script>


</body>
```

## 实例方法

```js
方法一：
  var tabs= plgTabs(options); //创建实例
      tabs.renderTo(element);//挂载点
      tabs.on(callback);//Click事件回调方法

方法二：

    $("#app3").plgTabs(config3).renderTo("#app3").on(function (ele) {
        console.log(this)
    });
```

## 基本参数

| 名称 | 类型 | 说明 |
| --- | --- | --- |
| indexActive | number | 初始化默认选中项下标，默认为0，\(可选\) |
| skin | string | 皮肤样式，"normal","brief","card",默认为normal，\(可选\) |
| filter | string | 过滤选择器，默认为plgTabs1231..."，\(可选\) |
| content | ArrryObject | \[{ title:"标题",template:内容模版，可以是html文档对象\]},\(必选\) |

## 方法

| 方法 | 说明 |
| --- | --- |
| renderTo\(id\) | 渲染节点挂载 |
| on | 点击选项卡Click事件回调方法 |



