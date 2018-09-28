
## 树型菜单

>组件名称

```
PlgZtree
```

>快速使用

```js
 <link rel="stylesheet" type="text/css" href="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.css"/>
    <link rel="stylesheet" type="text/css" href="../../../modules/dhtmlx/grid/skins/web/dhtmlxgrid.css"/>
    <link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css"/>
    <!--全局样式-->
    <link rel="stylesheet" type="text/css" href="../../../globalCss/global_style.css"/>



    <script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../modules/layui-master/dist/layui.all.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>


    <!--PlgZtree组件 JS/css-->
    <link rel="stylesheet" type="text/css" href="../../../modules/zTree_v3/css/prolog/zTreeStyle.css">
    <script src="../../../modules/zTree_v3/js/jquery.ztree.core.min.js" type="text/javascript" charset="utf-8"></script>
    <script src="../codebase/PlgZtree.js" type="text/javascript" charset="utf-8">

    

<body style="background: #fff; ">


      <div id="app" class="ztree" style=" border: 1px solid #ddd ;padding: 20px; margin: 10px">

        </div>



       <script  type="text/javascript">

                var confing={
                url:"data2.json",
                onClick:function(event, treeId, treeNode){
                    console.log(treeNode)
                }
    }
         var tree=plgZtree(confing).renderTo("#app");

    </script>

</body>
```



##实例方法
```js
   // 配置
var confing={
        url:"data2.json",
        onClick:function(event, treeId, treeNode){
            console.log(treeNode)
        }


 var tree=plgZtree(confing).renderTo("#app");

     tree.getZtree//获得树的对象



```

##基本参数

|名称|类型|说明|
|-|-|-|
|url|string|请求url接口地址(必选)|
|onClick|function|点击菜单回调方法，参数event, treeId, treeNode|

##方法
|方法 | 说明 |
| - | - |
|renderTo("#id")|渲染节点挂载|
|getZtree|获得Ztree实例对象方法|

##plgZtree.getZtree实便方法说明 
api参考网址[http://www.treejs.cn/v3/api.php](http://www.treejs.cn/v3/api.php)

|方法 | 说明 |
| --- | --- |
| setting|zTree 对象使用的 setting 配置数据，详细请参考 “setting 配置详解”中的各个属性详细说明 | 
| addNodes (parentNode, index, newNodes, isSilent)|添加节点。 | 
| cancelEditName (newName)|取消节点的编辑名称状态，可以恢复原名称，也可以强行赋给新的名称。 | 
| cancelSelectedNode (node)| 取消节点的选中状态。| 
| checkAllNodes (checked)|勾选 或 取消勾选 全部节点。[setting.check.enable = true 且 setting.check.chkStyle = "checkbox" 时有效],此方法不会触发 beforeCheck / onCheck 事件回调函数。 | 
| checkNode (node, checked, checkTypeFlag, callbackFlag)|勾选 或 取消勾选 单个节点。[setting.check.enable = true 时有效] | 
| copyNode (targetNode, node, moveType, isSilent)| 复制节点。| 
| destroy ()| 1、用此方法可以销毁 zTreeObj 代表的 zTree。2、销毁当前页面全部的 zTree，也可以使用 $.fn.zTree.destroy() 方法。3、重新使用已经被销毁的树，必须要使用 init 方法进行初始化。| 
| editName (node)|设置某节点进入编辑名称状态。 | 
| expandAll (expandFlag)| 展开 / 折叠 全部节点| 
| expandNode (node, expandFlag, sonSign, focus, callbackFlag)| 展开 / 折叠 指定的节点| 
| getChangeCheckedNodes ()| 获取输入框勾选状态被改变的节点集合（与原始数据 checkedOld 对比）。[setting.check.enable = true 时有效]| 
| getCheckedNodes (checked)| 获取输入框被勾选 或 未勾选的节点集合。[setting.check.enable = true 时有效]| 
| getNodeByParam (key, value, parentNode)|根据节点数据的属性搜索，获取条件完全匹配的节点数据 JSON 对象 | 
| getNodeByTId (tId)| 根据 zTree 的唯一标识 tId 快速获取节点 JSON 数据对象| 
| getNodeIndex (node)| 获取某节点在同级节点中的序号（从0开始）| 
| getNodes ()|获取 zTree 的全部节点数据 | 
| getNodesByFilter (filter, isSingle, parentNode, invokeParam)|根据自定义规则搜索节点数据 JSON 对象集合 或 单个节点数据 | 
| getNodesByParam (key, value, parentNode)| 根据节点数据的属性搜索，获取条件完全匹配的节点数据 JSON 对象集合| 
| getNodesByParamFuzzy (key, value, parentNode)|根据节点数据的属性搜索，获取条件模糊匹配的节点数据 JSON 对象集合 | 
| getSelectedNodes ()|获取 zTree 当前被选中的节点数据集合| 
| hideNode (node)|隐藏某个节点。 | 
| hideNodes (nodes)|隐藏一批节点。 | 
| moveNode (targetNode, node, moveType, isSilent)|移动节点。 | 
| reAsyncChildNodes (parentNode, reloadType, isSilent, callback)|强行异步加载父节点的子节点。[setting.async.enable = true 时有效] | 
| reAsyncChildNodesPromise(parentNode, reloadType, isSilent)| 强行异步加载父节点的子节点（ES6 Promise 版）。[setting.async.enable = true 时有效]| 
| refresh ()| 刷新 zTree 。| 
| removeChildNodes (parentNode)|清空某父节点的子节点。 | 
| removeNode (node, callbackFlag)|删除节点。 | 
| selectNode (node, addFlag, isSilent)|选中指定节点 | 
| setChkDisabled (node, disabled, inheritParent, inheritChildren)|禁用 或 解禁 某个节点的 checkbox / radio [setting.check.enable = true 时有效] | 
| setEditable (editable)|设置 zTree 进入 / 取消 编辑状态。 | 
| showNode (node)| 显示某个被隐藏的节点。| 
| showNodes (nodes)| 显示一批已经被隐藏的节点。| 
| transformToArray (nodes)|将 zTree 使用的标准 JSON 嵌套格式的数据转换为简单 Array 格式。(免去用户自行编写递归遍历全部节点的麻烦) | 
| transformTozTreeNodes (simpleNodes)|将简单 Array 格式数据转换为 zTree 使用的标准 JSON 嵌套数据格式。 | 
| updateNode (node, checkTypeFlag)| 更新某节点数据，主要用于该节点显示属性的更新。| 













