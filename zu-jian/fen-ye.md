分

页组件

> 组件名称

```
PlgPage
```

> 快速使用

```
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layer/layer.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
<script src="../codebase/PlgPage.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

```
var config5 = {
        renderer: 'test1',
        items:[
            {text:"战神", type:'warn', size:"big", class: "k-1111"},   // 局部设置size
            {text:"战神22", type:'', size:"big", soltPos: 'after', tpl: '<b>多个按钮的插槽<b>'}  // 局部设置size
        ],
        type: 'danger',
        size: 'big',   // 全局设置size
}
var plg = new PlgButton(config5);


plg.on("click", function(ind){
    console.log('点击第几个的时候做什么');
    console.log('ind::---' + ind);
});
```

方法一：

```
var grid = new PlgPage(config5);
```

![img](blob:file:///d14b4fb4-c035-4803-9912-4fb9e678e9d6)

> 配置

| 属性     | 说明                                                   | 示例                                                         |
| -------- | ------------------------------------------------------ | ------------------------------------------------------------ |
| renderer | 挂载点，是id，不需要写`#`                              | elem                                                         |
| count    | 总的数据记录条数                                       | count: 50                                                    |
| click    | 获取用户当前点击的分页按钮的页码，是一个函数用来回掉的 | function getCurrPage(params){console.log('params::' +params)} |