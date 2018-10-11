### 按钮组件

> ```
> 组件名称
> ```

```
PlgButton
```

> 快速使用

```
使用的方法::
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
    <title>Plgbutton按钮的封装</title>
    <style>
        body{padding: 10px;}

        div {
            margin-top: 10px;
        }
        
    </style>
    <script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../modules/layui-master/dist/layui.all.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../components/PlgButton/codebase/PlgButton.js" type="text/javascript" charset="utf-8"></script>
    
</head>
<body>

    <h4>button普通调用</h4>
    <div id="test"></div>
    <hr />

    <h4>button普通调用</h4>
    <div id="test1"></div>
    <hr />

    <h4>button普通调用</h4>
    <div id="test2"></div>
    <hr />

    <script>
        var config = {
            renderer: 'test', //注意，这里的 test1 是 ID，不用加 # 号
            items: [
                { 
                    text: '天上有漂亮的星星',
                    type: 'primary',
                    size: 'big',
                    class: 'big',
                    radius: 'radius'
                }
            ]
        }
        var plg = new PlgButton(config);

        plg.on("click", function(ind){
            console.log('点击第几个的时候做什么');
            console.log('ind::---' + ind);
        });

        var config1 = {
            renderer: 'test1', //注意，这里的 test1 是 ID，不用加 # 号
            items: [
                { 
                    text: '天上有漂亮的星星',
                    type: 'primary',
                    size: 'big',
                    class: 'big',
                    radius: 'radius'
                },
                { 
                    text: '<i class="layui-icon">&#xe603;</i>月亮',
                    type: 'danger',
                    size: 'big',
                    class: 'big',
                    radius: 'radius'
                }
            ]
        }
        // var plg = new PlgButton(config);
        var plg1 = $("#test1").initPlgButton(config1);

        plg1.on("click", function(ind){
            console.log('点击第几个的时候做什么');
            console.log('ind::---' + ind);
        });

        var config2 = {
            renderer: 'test2', //注意，这里的 test1 是 ID，不用加 # 号
            items: [
                { 
                    text: '<i class="layui-icon">&#xe603;</i>',
                    type: 'warn',
                    size: 'big',
                    class: 'big',
                    radius: 'radius'
                }
            ]
        }
        // var plg = new PlgButton(config);
        var plg1 = $("#test2").initPlgButton(config2);
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

| 属性 | 说明 | 数据类型 | 默认值 |
| :--- | :--- | :--- | :--- |
| renderer | 挂载点，是id，不需要写\`\#\` |  | elem |
| type | 设置全局的按钮type，主要是改变按钮的颜色，可选参数，默认参数为空【warn】【primary】【danger】【disabled】  【normal】 | String | 设置全局按钮的颜色 |
| size | 设置全局的size可选参数【big】【small】【mini】【danger】，默认为空 | String | - |
| radius | 是否是圆角，默认值为空,可选参数【radius】 | String | - |
| items | 设置按钮的局部参数 | ArrayObject |  |
| items\[type\] | 设置局部的按钮type，主要是改变按钮的颜色，可选参数，默认参数为空【warn】【primary】【danger】【disabled】  【normal】 |  | - |
| items\[size\] | 设置局部的size可选参数【big】【small】【mini】【danger】，默认为空 | String | - |
| items\[text\] | 设置局部的值，主要用来，可以是一个dom字符串 | String | - |
| items\[class\] | 用户自定义class名称， 可选参数 | String | - |
| items\[radius\] | 按钮是否为圆角【radius】 | String | - |

> 事件

| 名称 | 方法 | 描述 | 回参 |
| :--- | :--- | :--- | :--- |
| on 方法 | on\('click', callback\(ind\)\) | 用户点击按钮后返回当前的index值，目前只支持click事件 | 返回的是当前button的index的值 |



