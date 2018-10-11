### 按钮组件

> ```
> 组件名称
> ```

```
PlgButton
```

> 快速使用

```
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layer/layer.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
<script src="../codebase/PlgButton.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

```
使用的方法::
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
    <title>button组件</title>
    <style>
        body{padding: 10px;}
    </style>
</head>
<body>
  <div id="test1"></div>


  <script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
  <script src="../../../modules/layui-master/dist/layui.all.js" type="text/javascript" charset="utf-8"></script>
  <script src="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.js" type="text/javascript" charset="utf-8"></script>
  <script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
  <script src="../../../components/PlgButton/codebase/PlgButton.js" type="text/javascript" charset="utf-8"></script>
  <script>	
    // var grid = $("#test1").initPlgButton(config4);
    var config = {
        renderer: 'test1',
        items:[
            {text:"<i class='layui-icon'>&#xe642;</i>战神22<b>多个按钮的插槽<b>", type:'', size:"big"}  // 局部设置size
        ],
        type: 'danger',
        size: 'big',   // 全局设置size
        radius: 'radius'  // 全局设置是否是圆角
    }

    var config1 = {
        renderer: 'test1',
        items:[
            {text:"战神", type:'warn', size:"big", class: "k-1111"},   // 局部设置size
            {text:"<i class='layui-icon'>&#xe642;</i>战神22<b>多个按钮的插槽<b>", type:'', size:"big"}  // 局部设置size
        ],
        type: 'danger',
        size: 'big',   // 全局设置size
        radius: 'radius'  // 全局设置是否是圆角
    }
    var plg = new PlgButton(config1);
   

    plg.on("click", function(ind){
        console.log('点击第几个的时候做什么');
        console.log('ind::---' + ind);
    });


  </script>
</body>
</html>
```


方法一：
```
var grid = new PlgButton(config);
```
方法二：
```
var grid = $("#div1").initPlgButton(config);
```

![](/assets/plgbtn.png)

> 配置

| 属性 | 说明 | 示例 |
| :--- | :--- | :--- |
| renderer | 挂载点，是id，不需要写\`\#\` | elem |
| type | 设置全局的按钮type，主要是改变按钮的颜色，可选参数，默认参数为空【warn】【primary】【danger】【disabled】  【normal】 | 设置全局按钮的颜色 |
| size | 设置全局的size可选参数【big】【small】【mini】【danger】，默认为空 | 同上 |
| radius | 是否是圆角，默认值为空,可选参数【radius】 |  |
| items | 设置按钮的局部参数 |  |
| items\[type\] | 设置局部的按钮type，主要是改变按钮的颜色，可选参数，默认参数为空【warn】【primary】【danger】【disabled】  【normal】 | isGroup: true |
| items\[size\] | 设置局部的size可选参数【big】【small】【mini】【danger】，默认为空 | 同上 |
| items\[text\] | 设置局部的值，主要用来 | 同上 |
| items\[class\] | 用户自定义class名称 | 同上 |
| items\[radius\] | 按钮是否为圆角 | 同上 |

> 事件

| 名称 | 方法 | 描述 | 回参 |
| :--- | :--- | :--- | :--- |
| on 方法 | on\('click', callback\(ind\)\) | 用户点击按钮后返回当前的index值，目前只支持click事件 | 返回的是当前button的index的值 |



