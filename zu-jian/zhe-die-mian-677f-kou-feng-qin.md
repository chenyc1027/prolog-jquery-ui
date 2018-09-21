### 折叠面板/口风琴

> 组件名称

```
PlgCollapse
```

> 快速使用

```
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layer/layer.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layui-master/dist/layui.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
<script src="../codebase/PlgCollapse.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

```
方法一：
var grid = new PlgCollapse(opts);
方法二：
var grid = $("div1").initPlgCollapse(opts);
```

> 折叠面板

![](/assets/collapse.png)

> 口风琴

![](/assets/accordion.png)

| 属性 | 说明 | 示列 |
| :--- | :--- | :--- |
| elem | 挂载点,id，不需要写\# | test |
| model | 模式 【accordion  -- 手风情模式】【codebase--折叠面板模式】，默认是【codebase--折叠面板模式】 |  |
| items | 用户数据体 |  |
| items[title] | 面板的头部，主要是展示部分 |  |
| items[content] | 面板的主体，主要是现实内容的部分 |  |
| items[show] | 面板的默认状态【show--展示】【false--隐藏，默认样式】 |  |
|  |  |  |
|  |  |  |



