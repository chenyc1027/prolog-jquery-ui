## 日期

> 组件名称

```
PlgDate
```

> 快速使用

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

   <!--PlgPlgDate组件 JS-->
   <script src="../codebase/PlgDate.js" type="text/javascript" charset="utf-8"></script>

<body style="background: #fff; ">


    <div style="pading:20px">
             <input type="text" class="layui-input" id="text">
               <div class="layui-form">
                <div class="layui-form-item">
                  <div class="layui-inline">
                    <input type="text2 " class="layui-input ta" id="text3">
                  </div>
                  <div class="layui-inline">

               <input type="text2 " class="layui-input " id="text2">
                  </div>
                </div>
              </div>

                <input type="text" class="layui-input test-item" placeholder="yyyy-MM-dd">

                <input type="text" class="layui-input test-item" placeholder="yyyy-MM-dd">

                <input type="text" class="layui-input test-item" placeholder="yyyy-MM-dd">


    </div>


    <script type="text/javascript">


        var date=plgDate.render({
            elem:"#text"
        })
        console.log(date)


        var config={
            value:new Date()

        }

     var date= $('.test-item').plgDateRender(config)



    </script>

</body>
```

## 实例方法

```js
方法一：
     plgDate.render({
            elem:"element"
        })


方法二：

     $(element).plgDateRender(options);
```

> # 基本参数

## elem - 绑定元素

类型：String/DOM，默认值：无  
必填项，用于绑定执行日期渲染的元素，值一般为选择器，或DOM对象

```js
        plgDate.render({ 
        elem: '#test' //或 elem: document.getElementById('test')、elem: $('#test') 等
        });

        //如果绑定多个 是多个相同元素
        $(element).each(function(){
                plgDate.render({ 
                elem: this
                });
        })
```

## type - 控件选择类型

类型：String，默认值：date  
用于单独提供不同的选择器类型，可选值如下表：

| type可选值 | 名称 | 用途 |
| --- | --- | --- |
| year | 年选择器 | 只提供年列表选择 |
| month | 年月选择器 | 只提供年、月选择 |
| date | 日期选择器 | 可选择：年、月、日。type默认值，一般可不填 |
| time | 时间选择器 | 只提供时、分、秒选择 |
| datetime | 日期时间选择器 | 可选择：年、月、日、时、分、秒 |

```js
//年选择器
plgDate.render({ 
  elem: '#test'
  ,type: 'year'
});

//年月选择器
plgDate.render({ 
  elem: '#test'
  ,type: 'month'
});

//日期选择器
plgDate.render({ 
  elem: '#test'
  //,type: 'date' //默认，可不填
});

//时间选择器
plgDate.render({ 
  elem: '#test'
  ,type: 'time'
});

//日期时间选择器
plgDate.render({ 
  elem: '#test'
  ,type: 'datetime'
});
```

## range - 开启左右面板范围选择

类型：Boolean/String，默认值：false  
如果设置 true，将默认采用 “ - ” 分割。 你也可以直接设置 分割字符。五种选择器类型均支持左右面板的范围选择。

```js
//年范围选择
plgDate.render({ 
  elem: '#test'
  ,type: 'year'
  ,range: true //或 range: '~' 来自定义分割字符
});

//年月范围选择
plgDate.render({ 
  elem: '#test'
  ,type: 'month'
  ,range: true //或 range: '~' 来自定义分割字符
});

//日期范围选择
plgDate.render({ 
  elem: '#test'
  ,range: true //或 range: '~' 来自定义分割字符
});

//时间范围选择
plgDate.render({ 
  elem: '#test'
  ,type: 'time'
  ,range: true //或 range: '~' 来自定义分割字符
});

//日期时间范围选择
plgDate.render({ 
  elem: '#test'
  ,type: 'datetime'
  ,range: true //或 range: '~' 来自定义分割字符
});
```

## format - 自定义格式

类型：String，默认值：yyyy-MM-dd  
通过日期时间各自的格式符和长度，来设定一个你所需要的日期格式。plgDate 支持的格式如下：

```js
//自定义日期格式
plgDate.render({ 
  elem: '#test'
  ,format: 'yyyy年MM月dd日' //可任意组合
});
```

## value - 初始值

类型：String，默认值：new Date\(\)  
支持传入符合format参数设定的日期格式字符，或者 new Date\(\)

```js
//传入符合format格式的字符给初始值
plgDate.render({ 
  elem: '#test'
  ,value: '2018-08-18' //必须遵循format参数设定的格式
});

//传入Date对象给初始值
plgDate.render({ 
  elem: '#test'
  ,value: new Date(1534766888000) //参数即为：2018-08-20 20:08:08 的时间戳
});
```

## isInitValue - 初始值填充

类型：Boolean，默认值：true  
用于控制是否自动向元素填充初始值（需配合 value 参数使用）

```js
plgDate.render({
  elem: '#test'
  ,value: '2017-09-10'
  ,isInitValue: false //是否允许填充初始值，默认为 true
});
```

## min/max - 最小/大范围内的日期时间值

类型：string，默认值：min: '1900-1-1'、max: '2099-12-31'

设定有限范围内的日期或时间值，不在范围内的将不可选中。这两个参数的赋值非常灵活，主要有以下几种情况：  
1.    如果值为字符类型，则：年月日必须用 -（中划线）分割、时分秒必须用 :（半角冒号）号分割。这里并非遵循 format 设定的格式  
2.    如果值为整数类型，且数字＜86400000，则数字代表天数，如：min: -7，即代表最小日期在7天前，正数代表若干天后  
3.    如果值为整数类型，且数字 ≥ 86400000，则数字代表时间戳，如：max: 4073558400000，即代表最大日期在：公元3000年1月1日

```js
//日期有效范围只限定在：2017年
plgDate.render({ 
  elem: '#test'
  ,min: '2017-1-1'
  ,max: '2017-12-31'
});

//日期有效范围限定在：过去一周到未来一周
plgDate.render({ 
  elem: '#test'
  ,min: -7 //7天前
  ,max: 7 //7天后
});

//日期时间有效范围的设定: 
plgDate.render({ 
  elem: '#test'
  ,type: 'datetime'
  ,min: '2017-8-11 12:30:00'
  ,max: '2017-8-18 12:30:00'
});

//时间有效范围设定在: 上午九点半到下午五点半
plgDate.render({ 
  elem: '#test'
  ,type: 'time'
  ,min: '09:30:00'
  ,max: '17:30:00'
});
```

## position - 定位方式

类型：String，默认值：absolute  
用于设定控件的定位方式，有以下三种可选值：

| position 可选值 | 说明 |
| --- | --- |
| abolute | 绝对定位，始终吸附在绑定元素周围。默认值 |
| fixed | 固定定位，初始吸附在绑定元素周围，不随浏览器滚动条所左右。一般用于在固定定位的弹层中使用。 |
| static | 静态定位，控件将直接嵌套在指定容器中。注意：请勿与 show 参数的概念搞混淆。show为 true 时，控件仍然是采用绝对或固定定位。而这里是直接嵌套显示 |

## zIndex - 层叠顺序

类型：Number，默认值：66666666

## showBottom - 是否显示底部栏

类型：Boolean，默认值：true

如果设置 false，将不会显示控件的底部栏区域

## btns - 工具按钮

类型：Array，默认值：\['clear', 'now', 'confirm'\]

右下角显示的按钮，会按照数组顺序排列，内置可识别的值有：clear、now、confirm

## ready - 控件初始打开的回调

控件在打开时触发，回调返回一个参数：初始的日期时间对象

```js
codelayui.code
plgDate.render({
  elem: '#test'
  ,ready: function(date){
    console.log(date); //得到初始的日期时间对象：{year: 2017, month: 8, date: 18, hours: 0, minutes: 0, seconds: 0}
  }
});
```

## change-日期时间被切换后的回调

年月日时间被切换时都会触发。回调返回三个参数，分别代表：生成的值、日期时间对象、结束的日期时间对象

```js
codelayui.code
plgDate.render({
  elem: '#test'
  ,change: function(value, date, endDate){
    console.log(value); //得到日期生成的值，如：2017-08-18
    console.log(date); //得到日期时间对象：{year: 2017, month: 8, date: 18, hours: 0, minutes: 0, seconds: 0}
    console.log(endDate); //得结束的日期时间对象，开启范围选择（range: true）才会返回。对象成员同上。
  }
});
```

## render-弹出控件提示

事实上，执行核心方法 plgDate.render\(options\) 会返回一个当前实例对象。其中包含一些成员属性和方法，比如：hint方法

```js
codelayui.code
var ins1 = plgDate.render({
  elem: '#test'
  ,change: function(value, date, endDate){
    ins1.hint(value); //在控件上弹出value值
  }
});
```



