### 富文本编辑器组件

> 组件名称

```
PlgEdit
```

> 快速使用

```
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layer/layer.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../modules/layui-master/dist/layui.js" type="text/javascript" charset="utf-8"></script>
<script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
<script src="../codebase/PlgEdit.js" type="text/javascript" charset="utf-8"></script>
```

> 使用方法

```
<div id="getContent">getContent</div>

<script>
var config = {
    renderer: 'demo',
    height: 200, // 此处只能是高度
    uploadImage: {
        url: '', //接口url
        type: '' //默认post
        }
}

var plg = new PlgEdit(config);
$('#getContent').on('click', function(){
    console.log(plg.plgEditgethander());
    console.log(plg.plgEditgetContent());
    console.log(plg.plgEditgetText());
    console.log(plg.plgEditsync());
    console.log(plg.plgEditgetSelection());
})
```

方法一：

```
var grid = new PlgEdit(config);
```

方法二：

```
var grid = $("div1").initPlgEdit(config);
```

![](/assets/edit.png)

> 配置

| 属性 | 说明 | 示例 |
| :--- | :--- | :--- |
| elem | 挂载点，是id，不需要写\`\#\` | elem |
| height | 文本框的高度，正整数，单位是px | height: 50 |
| tool | 文本框菜单栏显示的功能，主要有【·strong\`-- 加粗】【\`italic\`-- 斜体】【 \`underline\`-- 下划线】【 \`del\` -- 删除线】【\`\|\` -- 分割线】【\`left\`--左对齐】【\`center\` --居中对齐】【\`right\`--右对齐】【\`link\`--超链接】【\`unlink\`--清除链接】【\`face\`-- 表情】【\`image\`--插入图片】 【\`help\`-- 帮助】 | 是一个数组，默认这些都会显示 |
| hideTool | 参数同上，主要是在惨淡中不显示传入的参数 | |
| uploadImage | 上传图片的API | |
| uploadImage\[url\] | 上传图片的地址 | |
| uploadImages\[type\] | 默认是post | |

> 事件

| 名称 | 方法 | 描述 | 回参 |
| :--- | :--- | :--- | :--- |
| 获取当前编辑器的事件句柄 | plgEditgethander() | 触发该事件获取文编编辑器的事件句柄 | 返回当前文本编辑器的句柄index的值 |
| 获得编辑器的内容 | plgEditgetContent(index) | 用户点击按钮后返回当前的编辑器的句柄，编辑器的内容，index为空的时候表示获取当前编辑器句柄的值 | 返回的是当前的编辑器的内容 |
| 获得编辑器的纯文本内容 | plgEditgetText(index) | 用户点击按钮后返回当前的编辑器的纯文本内容 | 同上 |
| 【*不好测试*】用于同步编辑器内容到textarea（一般用于异步提交） | plgEditsync(index) | 用户点击按钮后返回当前用于同步编辑器内容到textarea（一般用于异步提交） | 同上 |
| 获取编辑器选中的文本 | plgEditgetSelection(index) | 用户点击按钮后返回当前的获取编辑器选中的文本 | 同上 |

### Tips 对上传图片返回的参数有要求

```
{
"code": 0, //0表示成功，其它失败
"msg": "", //提示信息 //一般上传失败后返回
"data": {
    "src": "图片路径",
    "title": "图片名称" //可选
    }
}
```


