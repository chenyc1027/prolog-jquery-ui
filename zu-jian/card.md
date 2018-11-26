### 卡片组件

> 组件名称

```
PlgCard
```

> 效果示意

 ![](/assets/card.png)

> 快速使用

```js
  <link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css" />
  <link rel="stylesheet" href="../../../components/PlgCard/codebase/PlgCard.css" />

  <script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>

  <script src="../../../modules/layui-master/dist/layui.all.js"></script>
  <script src="../../../modules/dhtmlx/form/codebase/dhtmlxform.js"></script>

  <script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>

  <script src="../../../components/PlgCard/codebase/PlgCard.js" type="text/javascript" charset="utf-8"></script>


<h3>此处的效果是渲染出来的</h3>
<div id="demo"></div>
<div id="demo1"></div>

    // 上传【 音频/视频】文件 
    var config = {
      renderer: 'demo',
      config: {
        style: 'one', // one. two, three, add 
        data: [{
            cardNo: 1,
            cardName: '金口仓',
            btn: [{
                text: '详情',
                fn: 'detailsFn',
              },
              {
                text: '修改',
                fn: 'updateFn',
              },
              {
                text: '删除',
                fn: 'delFn',
              }
            ]
          },
          {
            cardNo: 2,
            cardName: '金口仓',
            btn: [{
                text: '详情',
                fn: 'detailsFn',
              },
              {
                text: '修改',
                fn: 'updateFn',
              },
              {
                text: '删除',
                fn: 'delFn',
              }
            ]
          },
          {
            cardNo: 3,
            cardName: '金口仓',
            btn: [{
                text: '详情',
                fn: 'detailsFn',
              },
              {
                text: '修改',
                fn: 'updateFn',
              },
              {
                text: '删除',
                fn: 'delFn',
              }
            ]
          },
          {
            cardNo: 4,
            cardName: '金口仓',
            btn: [{
                text: '详情',
                fn: 'detailsFn',
              },
              {
                text: '修改',
                fn: 'updateFn',
              },
              {
                text: '删除',
                fn: 'delFn',
              }
            ]
          },
          {
            cardNo: 5,
            cardName: '金口仓',
            btn: [{
                text: '详情',
                fn: 'detailsFn',
              },
              {
                text: '修改',
                fn: 'updateFn',
              },
              {
                text: '删除',
                fn: 'delFn',
              }
            ]
          },
          {
            cardNo: 6,
            cardName: '金口仓',
            btn: [{
                text: '详情',
                fn: 'detailsFn',
              },
              {
                text: '修改',
                fn: 'updateFn',
              },
              {
                text: '删除',
                fn: 'delFn',
              }
            ]
          },
          {
            cardNo: 7,
            cardName: '金口仓',
            btn: [{
                text: '详情',
                fn: 'detailsFn',
              },
              {
                text: '修改',
                fn: 'updateFn',
              },
              {
                text: '删除',
                fn: 'delFn',
              }
            ]
          },
          {
            cardNo: 8,
            cardName: '金口仓',
            btn: [{
                text: '详情',
                fn: 'detailsFn',
              },
              {
                text: '修改',
                fn: 'updateFn',
              },
              {
                text: '删除',
                fn: 'delFn',
              }
            ]
          }
        ]
      }
    }


```

> 构造方法

```
方法一：
var plg1 = new PlgCard(config);

```

> 配置

| 属性 | 说明 | 数据类型 | 默认值 |
| :--- | :--- | :--- | :--- |
| renderer | 挂载点，是id，不需要写\`\#\` | 字符串 | - |
| config | 用户的记录信息 | Object | - |
| config.style | 当前组件的风格【one】【two】【three】【add】 | String | one |
| config.data | 记录的数据信息 | ArrayObject |  |
| config.data.cardNo | 当前记录的id | Number |  |
| config.data.cardName | 当前模块的名称 | String |  |
| config.data.btn | 当前模块的秒速 | ArrayObject |  |
| config.data.btn.text | 按钮名称 | Boolean | false |
| config.data.btn.fn | 按钮所对应的事件 | Number |  |



> 事件

```
/** 
* ind 当前的点击的是记录的cardNo值
* callBackFn，当前点击按钮之后做什么操作
* **/
plg1.on("click", function (ind, callBackFn) {
    console.log('ind::' + ind);
    console.log('callBackFn::' + callBackFn);
});
```



