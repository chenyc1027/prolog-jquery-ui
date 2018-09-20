\#\#\# 按钮组件



&gt; 组件名称



\`\`\`

PlgButton

\`\`\`



&gt; 快速使用



\`\`\`js

&lt;link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/&gt;



&lt;script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"&gt;&lt;/script&gt;

&lt;script src="../../../modules/layer/layer.js" type="text/javascript" charset="utf-8"&gt;&lt;/script&gt;

&lt;script src="../../../modules/layui-master/dist/layui.js" type="text/javascript" charset="utf-8"&gt;&lt;/script&gt;

&lt;script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"&gt;&lt;/script&gt;



&lt;script src="../codebase/PlgButton.js" type="text/javascript" charset="utf-8"&gt;&lt;/script&gt;

\`\`\`



!\[\]\(/assets/table1.png\)



&gt; 构造方法



\`\`\`

方法一：

var grid = new PlgGrid\(opts\);



方法二：

var grid = $\("div1"\).initPlgGrid\(opts\);

\`\`\`



&gt; 配置



\| 配置项 \| 说明 \|

\| :--- \| :--- \|

\| skin \| 皮肤样式 \|

\| renderer \| 渲染节点 \|

\| columns \| 数据列名称，“,”分隔的字符串，如“id,number,name” \|

\| headers \| 表头，“,”分隔的字符串，如：“id,编号,名称” \|

\| multiselect \| 是否支持多选，默认false \|

\| url \| 数据接口 \|

\| params \| 数据接口提交参数 \|

\| page \| 是否开启分页，默认true，分页参数默认为pageNum和pageSize \|

\| totalCount \| 设定总页数字段，默认为“totalCount” \|



&gt; 方法



\| 方法 \| 说明 \|

\| :--- \| :--- \|

\| renderTo\\(id\\) \| 项目目标节点进行渲染 \|

\| loadData\\(\\) \| 加载数据 \|

\| reload\\(\\) \| 刷新数据 \|

\| getElement\\(\\) \| 获取组件dom节点 \|

\| getGrid\\(\\) \| 获取grid组件 \|

\| getParams\\(\\) \| 获取接口参数 \|



&gt; 事件



\`\`\`

使用：grid.on\("eventName",function\(e\){}\);

\`\`\`



\| 事件 \| 说明 \|

\| :--- \| :--- \|

\| onRowSelect\\(id,ind\\) \| 选择行事件。id - 选择行的id，ind - 列索引 \|

\| onRightClick\\(id,ind,obj\\) \| 右键事件。id - 单击行id ，ind - 列索引，obj-事件对象 \|

\| onHeaderClick\\(ind,obj\\) \| 表头单击事件。ind - 列索引，obj - 事件对象 \|









