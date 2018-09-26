### 弹出框

>组件名称

```
PlgDialog
```

>快速使用

```js
    <link rel="stylesheet" type="text/css" href="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.css" />
    <link rel="stylesheet" type="text/css" href="../../../modules/dhtmlx/grid/skins/web/dhtmlxgrid.css" />
    <link rel="stylesheet" type="text/css" href="../../../modules/layui-master/dist/css/layui.css" />
    <!--全局样式-->
    <link rel="stylesheet" type="text/css" href="../../../globalCss/global_style.css" />

    <script src="../../../modules/jquery/jquery.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../modules/layui-master/dist/layui.all.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../modules/dhtmlx/grid/codebase/dhtmlxgrid.js" type="text/javascript" charset="utf-8"></script>
    <script src="../../../core/plgcore.js" type="text/javascript" charset="utf-8"></script>



    <!--PlgDialog组件 JS-->
    <script src="../codebase/plgDialog.js" type="text/javascript" charset="utf-8"></script>

<body style="background: #fff; ">


    <div style="padding: 20px">


        <button id="dom_01" class="layui-btn">询问框</button>
        <button id="dom_02" class="layui-btn">消息层</button>
        <button id="dom_03" class="layui-btn">自定页</button>
        <button id="dom_04" class="layui-btn">tab页</button>
        <button id="dom_05" class="layui-btn">loadn层</button>
        <button id="dom_06" class="layui-btn">tips</button>
    </div>

    <script type="text/javascript">

        plgDialog.ready(function () {
            plgDialog.msg('很高兴一开场就见到你');
        });

        //询问框
        document.querySelector("#dom_01").onclick = function () {
            console.dir(plgDialog);
            //询问框
            plgDialog.confirm(`是否删除吗？`, {
                title: '删除提示',
                btn: ['确定', '取消']
            }, function (index) {
                plgDialog.close(index)

            });

        }

        //消息层
        document.querySelector("#dom_02").onclick = function () {
            plgDialog.msg('我是消息层');

        }

        document.querySelector("#dom_03").onclick = function () {
            plgDialog.open({
                title: '自定页',
                shadeClose: true,
                area: ['640px', '480px'],
                content: `<div >这里存放HTml内容</div>`, //iframe的url
                yes: function (index, layero) {

                    plgDialog.close(index); //如果设定了yes回调，需进行手工关闭

                },
                success: function (layero, index) {
                    //当你需要在层创建完毕时即执行一些语句，可以通过该回调。success会携带两个参数，分别是当前层DOM当前层索引。如：
                    console.log(layero, index);

                }
            })

        }

        //自定页
        document.querySelector("#dom_03").onclick = function () {
            plgDialog.open({
                title: '自定页',
                shadeClose: true,
                area: ['640px', '480px'],
                content: `<div >这里存放HTml内容</div>`, //iframe的url
                yes: function (index, layero) {

                    plgDialog.close(index); //如果设定了yes回调，需进行手工关闭

                },
                success: function (layero, index) {
                    //当你需要在层创建完毕时即执行一些语句，可以通过该回调。success会携带两个参数，分别是当前层DOM当前层索引。如：
                    console.log(layero, index);

                }
            })

        }

        //tab页
        document.querySelector("#dom_04").onclick = function () {
            plgDialog.tab({
                area: ['600px', '300px'],
                tab: [{
                    title: 'TAB1',
                    content: '内容1'
                }, {
                    title: 'TAB2',
                    content: '内容2'
                }, {
                    title: 'TAB3',
                    content: '内容3'
                }]
            });

        }

        //loading加载
        document.querySelector("#dom_05").onclick = function () {

            plgDialog.loading(); //0代表加载的风格，支持0-2
            //1秒后自动关闭加载层
            setTimeout(function () {
                plgDialog.closeAll("loading")
            }, 1000)


        }
        // tips提示层
        document.querySelector("#dom_06").onclick = function () {

            plgDialog.tips('默认就是向右的', this);

        }


    </script>


</body>
```



>#对象方法

##plgDialog.ready(callback) - 初始化就绪
由于我们的plgDialog内置了轻量级加载器，所以你根本不需要单独引入css等文件。但是加载总是需要过程的。当你在页面一打开就要执行弹层时，你最好是将弹层放入ready方法中，如：
```js
//页面一打开就执行弹层
        plgDialog.ready(function(){
          plgDialog.msg('很高兴一开场就见到你');
        });      
        
```
##plgDialog.alert(content, options, yes) - 普通信息框
它的弹出似乎显得有些高调，一般用于对用户造成比较强烈的关注，类似系统alert，但却比alert更灵便。它的参数是自动向左补齐的。通过第二个参数，可以设定各种你所需要的基础参数，但如果你不需要的话，直接写回调即可。如
```js
         //eg1
        plgDialog.alert('只想简单的提示');        
        //eg2
        plgDialog.alert('加了个图标', {icon: 1}); //这时如果你也还想执行yes回调，可以放在第三个参数中。
        //eg3
        plgDialog.alert('有了回调', function(index){
          //do something
          
          plgDialog.close(index);
        });     
```

##plgDialog.confirm(content, options, yes, cancel) - 询问框
类似系统confirm，但却远胜confirm，另外它不是和系统的confirm一样阻塞你需要把交互的语句放在回调体中。同样的，它的参数也是自动补齐的。
```js
        //eg1
        plgDialog.confirm('is not?', {icon: 3, title:'提示'}, function(index){
          //do something
          
          plgDialog.close(index);
        });
        //eg2
        plgDialog.confirm('is not?', function(index){
          //do something
          
          plgDialog.close(index);
        });
```
##layer.load(icon, options) - 加载层
load并不需要你传太多的参数，但如果你不喜欢默认的加载风格，你还有选择空间。icon支持传入0-2如果是0，无需传。另外特别注意一点：load默认是不会自动关闭的，因为你一般会在ajax回调体中关闭它。
```js
//eg1
var index = layer.load();
//eg2
var index = layer.load(1); //换了种风格
//eg3
var index = layer.load(2, {time: 10*1000}); //又换了种风格，并且设定最长等待10秒 
//关闭
layer.close(index);     
        

```
























