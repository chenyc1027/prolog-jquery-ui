### 导航组件

> 组件名称

```
PlgNav
```

> 快速使用

```
<
link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/
>


<
script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"
>
<
/script
>


<
script src="../../../modules/layer/layer.js" type="text/javascript" charset="utf-8"
>
<
/script
>


<
script src="../../../modules/layui-master/dist/layui.js" type="text/javascript" charset="utf-8"
>
<
/script
>


<
script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"
>
<
/script
>


<
script src="../codebase/PlgNav.js" type="text/javascript" charset="utf-8"
>
<
/script
>
```

> 构造方法

方法一：

```
var grid = new PlgNav(opts);
```

方法二：

var grid = $\("div1"\).initPlgNav\(opts\);



> 配置

| 属性 | 说明 | 示例 |
| :--- | :--- | :--- |
| elem | 挂载点，是id，不需要写\`\#\` | elem |
| data | nav的菜单\(数组格式\) | 目前仅仅支持2级的深度 |
| click | 获取用户当前点击的分页按钮的页码，是一个函数用来回掉的 | function getCurrPage\(params\){console.log\('params::' +params\)} |



  


