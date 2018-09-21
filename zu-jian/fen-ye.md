### 分页组件

> 组件名称

```
PlgPage
```

> 快速使用

```
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layer/layer.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layui-master/dist/layui.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
<script src="../codebase/PlgPage.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

方法一：

```
var grid = new PlgPage(opts);
```

方法二：

var grid = $\("div1"\).initPlgPage\(opts\);

![](/assets/fenye.png)

> 配置

| 属性 | 说明 | 示例 |
| :--- | :--- | :--- |
| elem | 挂载点，是id，不需要写\`\#\` | elem |
| count | 总的数据记录条数 | count: 50 |
| click | 获取用户当前点击的分页按钮的页码，是一个函数用来回掉的 | function getCurrPage\(params\){console.log\('params::' +params\)} |



