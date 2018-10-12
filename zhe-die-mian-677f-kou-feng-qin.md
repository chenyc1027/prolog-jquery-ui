### 折叠面板/口风琴组件

> ```
> 组件名称
> ```

```
PlgCollapse
```

> 快速使用

```
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layui-master/dist/layui.all.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../components/PlgCollapse/codebase/PlgCollapse.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

```
使用的方法::
    <h4>手风情式模式</h4>
    <div id="test"></div>
    <hr />

    <h4>折叠面板模式</h4>
    <div id="test1"></div>
    <hr />

    <h4>手风情式的折叠面板</h4>
    <div id="test2"></div>
    <hr />

    <script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../modules/layui-master/dist/layui.all.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../components/PlgCollapse/codebase/PlgCollapse.js" type="text/javascript" charset="utf-8"></script>
    <script>
        var options = {
            renderer: 'test', // 挂载点
            model: 'accordion', // 【accordion  -- 手风情模式】【codebase--折叠面板模式】
            items: [{
                    title: '面板的名称1',
                    content: '面板的名称1',
                    show: true // 【true--展示】【false--隐藏】
                },
                {
                    title: '面板的名称2',
                    content: '面板的名称2',
                    show: true // 【true--展示】【false--隐藏】
                },
                {
                    title: '面板的名称3',
                    content: '面板的名称3',
                    show: true // 【true--展示】【false--隐藏】
                }
            ]

        }
        var plg = new PlgCollapse(options);

        var options1 = {
            renderer: 'test1', // 挂载点
            model: 'codebase', // 【accordion  -- 手风情模式】【codebase--折叠面板模式】
            items: [{
                title: '面板的名称1',
                content: '面板的名称1',
                show: true // 【true--展示】【false--隐藏】
            }]
        }

        var plg1 = new PlgCollapse(options1);

        var options2 = {
            renderer: 'test2', // 挂载点
            model: 'codebase', // 【accordion  -- 手风情模式】【codebase--折叠面板模式】
            items: [{
                    title: '面板的名称1',
                    content: '面板的名称1',
                    show: true // 【true--展示】【false--隐藏】
                },
                {
                    title: '面板的名称11',
                    content: '面板的名称11',
                    show: false // 【true--展示】【false--隐藏】
                },
                {
                    title: '面板的名称111',
                    content: '面板的名称111',
                    show: false // 【true--展示】【false--隐藏】
                },
                {
                    title: '面板的名称1111',
                    content: '面板的名称1111',
                    show: false // 【true--展示】【false--隐藏】
                },
            ]
        }
        var plg2 = $('#test2').initPlgCollapse(options2);

    </script>
```

![](/assets/collapse.png)

> 配置

| 属性 | 说明 | 示例 | 默认值 |
| :--- | :--- | :--- | :--- |
| renderer | 挂载点，是id，不需要写\`\#\` | String | - |
| model | 【accordion -- 手风情模式】【codebase--折叠面板模式】 | String | 'accordion' |
| items | 设置菜单的局部参数 | ArrayObject | - |
| items\[title\] | 面板的主题 | String | - |
| items\[content\] | 面板内容 | String | - |
| items\[show\] | 模版的默认状态，是否显示【true】【false】 | Boolean | true |



