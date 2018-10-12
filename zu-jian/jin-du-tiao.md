### 进度条组件

> ```
> 组件名称
> ```

```
PlgProgress
```

> 快速使用

【Tips】使用了一个插件`jquery.color.animations.js`

```
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>

<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layui-master/dist/layui.all.js"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../components/PlgProgress/codebase/PlgProgress.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

```
使用的方法::
    <div id="test"></div>
    <div id="test1"></div>

    <script>
        var config = {
            renderer: 'test',
            showPercent: false,
            percent: 0.2,    // 0 -- 1 之间的小数
            thickness: 'red',
            time: 0.2    // 秒
        }

        var plg = new PlgProgress(config);

        // 用户点击完成的进度条的时候触发的事件
        plg.on("click", function(){
            // 用户点击的
            console.log('点击完成的进度条触发了该事件');

        });

        var config1 = {
            renderer: 'test1',
            showPercent: true,
            percent: 0.4,
            thickness: 'layui-progress-big',
            startBgColor: 'red',  // 设置初始背景颜色
            endBgColor: 'blue',  // 设置最后背景颜色
            time: 0.3 
        }
        var plg2 = $('#test1').initPlgProgress(config1);

        plg2.on("click", function(){
            // 用户点击的
            console.log('点击完成的进度条触发了该事件');

        });
    </script>
```

![](/assets/progress.jpg)

> 配置

| 属性 | 说明 | 类型 | 默认值 |
| :--- | :--- | :--- | :--- |
| renderer | 挂载点，是id，不需要写\`\#\` | String | - |
| showPercent | 是否显示百分比，【false --默认值，不展示】【true--展示】 | Boolean | false |
| percent | 设置菜单的局部参数 | Number（小数0-1中间的小数） | - |
| thickness | 厚度，显示进度条的大小，【默认空】可选参数【layui-progress-big】 | String | - |
| startBgColor | 初始的颜色 | String | - |
| endBgColor | 完成所有的进度之后的颜色 | String | '1E9FFF' |
| time | 速度，以秒为单位 | Number | 0.4 |

> 事件

| 属性 | 说明 | 示例 |
| :--- | :--- | :--- |
| on | 点击进度条的时候触发的事件 | function |



