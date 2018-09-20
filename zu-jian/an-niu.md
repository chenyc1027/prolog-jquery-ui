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
<script src="../../../modules/layui-master/dist/layui.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
<script src="../codebase/PlgButton.js" type="text/javascript" charset="utf-8"></script>
```

> 构造方法

```
方法一：
var grid = new PlgButton(opts);
方法二：
var grid = $("div1"\).initPlgButton(opts);
```

![](/assets/plgbtn.png)

> 配置

| 属性 | 说明 | 示例 |
| :--- | :--- | :--- |
| elem | 挂载点，是id，不需要写\`\#\` | elem |
| text | 标签里面的字，多个时候的时候，不需要使用空格\`\`代替 | \['测试一', '', '测试二'\] |
| color | 可选参数【primary】【normal】【warm】【danger】【disabled】，默认为空 | \['normal', ''\] |
| size | 可选参数【big】【small】【mini】【danger】，默认为空 | 同上 |
| isRadius | 【true-代表有圆角】，【false-没有圆角】 | 同上 |
| isGroup | 【true-是标签组】，【false不是】 | isGroup: true |
| disabled | 是否禁用：【true--禁用】【false--不禁用】 | 同上 |
| isIconBtn | 可选参数【add】【del】【edit】【right】，默认为空 | 同上 |



