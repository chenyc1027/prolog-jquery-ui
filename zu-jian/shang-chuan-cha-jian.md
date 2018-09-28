### 上传组件

> ```
> 组件名称
> ```

```
PlgUpload
```

> 快速使用

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
<div id="testdemo"></div>

<script>
layui.element.render();


var config = {
renderer: 'testdemo',
    showPercent: false,
    percent: '20%',
    thickness: '',
    bgColor: ''  // 设置背景颜色
}

var config1 = {
    renderer: 'testdemo',
    showPercent: true,
    percent: '20%',
    thickness: 'layui-progress-big',
    bgColor: 'layui-bg-blue'  // 设置背景颜色
}

// var plg = new PlgProgress(config);
var plg = new PlgProgress(config1);
```

![](/assets/progress.jpg)

> 配置

| 属性 | 说明 | 示例 |
| :--- | :--- | :--- |
| renderer | 挂载点，是id，不需要写\`\#\` | elem |
| showPercent | 是否显示百分比，【false --默认值，不展示】【true--展示】 | 布尔值 |
| percent | 设置菜单的局部参数 | 百分比 |
| thickness | 厚度，显示进度条的大小，【默认空】可选参数【layui-progress-big】 | 字符串 |
| bgColor | 背景颜色可选【layui-bg-red】【layui-bg-orange】【layui-bg-blue】【layui-bg-green】 | 字符串 |



