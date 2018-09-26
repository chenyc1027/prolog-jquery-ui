### 弹出框

组件名称

```
PlgDialog
```

快速使用

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
##plgDialog.open(options) - 原始核心方法
基本上是露脸率最高的方法，不管是使用哪种方式创建层，都是走plgDialog.open()，创建任何类型的弹层都会返回一个当前层索引，上述的options即是基础参数，另外，该文档统一采用options作为基础参数的标识例子：



