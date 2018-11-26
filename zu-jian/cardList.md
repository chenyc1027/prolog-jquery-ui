### 卡片组件

> 组件名称

```
PlgCardList
```

> 快速使用

```js
<link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css" />
  <link rel="stylesheet" href="../../../components/PlgCardList/codebase/PlgCardList.css" />

<script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
  <script src="../../../modules/layui-master/dist/layui.all.js"></script>
  <script src="../../../modules/dhtmlx/form/codebase/dhtmlxform.js"></script>
  <script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>
  <script src="../../../components/PlgCardList/codebase/PlgCardList.js" type="text/javascript" charset="utf-8"></script>


<h3>此处的效果是渲染出来的</h3>
<div id="demo"></div>
<div id="demo1"></div>

var config = {
      renderer: 'demo',
      data: [
        {
          id: 1,
          imgUrl: 'http://hbimg.b0.upaiyun.com/1f5e0ad05db347b65ffeca2f110491b500d1e85552088-E95HIm_fw658',
          imgAlt: '模块logo',
          title: '模块一',
          description: '当前这个模块的描述当前这个模块的描述当前这个模块的描述当前这个模块的描述当前这个模块的描述当前这个模块的描述',
          isAdd: true,
          star: 4,      // 0--5颗星星
          useNo: 3000,
          addFn: addFn,
          starFn: starFn
        },
        {
          id: 2,
          imgUrl: 'http://hbimg.b0.upaiyun.com/1f5e0ad05db347b65ffeca2f110491b500d1e85552088-E95HIm_fw658',
          imgAlt: '模块logo',
          title: '模块二',
          description: '当前这个模块的描述',
          isAdd: true,
          star: 2,      // 0--5颗星星
          useNo: 3000,
          addFn: addFn,
          starFn: starFn
        },
        {
          id: 3,
          imgUrl: 'http://hbimg.b0.upaiyun.com/1f5e0ad05db347b65ffeca2f110491b500d1e85552088-E95HIm_fw658',
          imgAlt: '模块logo',
          title: '模块三',
          description: '当前这个模块的描述',
          isAdd: true,
          star: 5,      // 0--5颗星星
          useNo: 3000,
          addFn: addFn,
          starFn: starFn
        }

      ]
    }
  
    var plgCard = new PlgCardList(config);

    function addFn(obj){
      console.log(obj);
    }

    function starFn(obj) {
      console.log(obj);
    }
```

> 构造方法

```
方法一：
var grid = new PlgCardList(opts);

```

> 配置

| 属性 | 说明 | 数据类型 | 默认值 |
| :--- | :--- | :--- | :--- |
| renderer | 挂载点，是id，不需要写\`\#\` | 字符串 | - |
| data | 用户的记录信息 | ArrayObject | - |
| id | 当前记录的id | Number |  |
| imgUrl | 当前模块的头像，一个link | String |  |
| imgAlt | 当前模块的头像的描述 | String |  |
| title | 当前模块的名称 | String |  |
| description | 当前模块的秒速 | String |  |
| isAdd | 是否有右上角的添加按钮 | Boolean | false |
| star | 当前模块用户的喜爱程度度 | Number |  |
| addFn | 点击右上角添加按钮触发的事件 | function |  |
| starFn | 点击星星触发的事件 | function |  |



> 事件

```
function addFn1(obj){
console.log(obj);
}

function starFn1(obj) {
console.log(obj);
}
```



